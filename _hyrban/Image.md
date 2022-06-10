The Image plugin allows one to have finer control over the layout of images than just the simple in-lining of images.

!!Parameters

;__src__ = '' 'Image source' '': This can either be a full URL (http://...) or a [WikiAttachment] name. Required.
;__align__ = '' 'left|right|center' '': The image alignment.
;__height__ = '' 'integer' '': Force the height of the image.
;__width__ = '' 'integer' '': Force the width of the image.
;__alt__ = '' 'alt text' '': The alt text of an image.  This is very useful when doing pages that can be navigated with text-only browsers.
;__caption__ = '' 'caption text' '': The text that should be shown as a caption under the image.
;__link__ = '' 'hyperlink' '': A hyperlink (http://...).  In the future, you can also use [WikiPages].
;__border__ = '' 'integer' '': Size of the image border.
;__style__ = '' 'style info' '': Any style markup you would like to apply to the table surrounding the image.
;__class__ = '' 'class name' '': Redefine the default class for this image, which is "imageplugin".

!!Examples
{{{
[{Image src='SandBox/test.png' caption='Testing Image' style='font-size: 120%; color: green;'}]
}}}

Shows the attachment {{SandBox/test.png}} with the caption __Testing Image__ underneath it.  The text is 120% in height and will be rendered in green color.

{{{
[{Image src='http://opi.yahoo.com/online?u=YahooUser1234&m=g&t=2' 
link='http://edit.yahoo.com/config/send_webmesg?.target=YahooUser1234&.src=pg'}]}}}

Shows the Yahoo online / offline graphic and creates a link to Yahoo send message 

[{Image src='http://opi.yahoo.com/online?u=YahooUser1234&m=g&t=2' 
link='http://edit.yahoo.com/config/send_webmesg?.target=YahooUser1234&.src=pg'}]

While the ImagePluginWithThumbnails provides automatic creation of thumbnails from the full size image, it's also pretty complicated and not part of JSPWiki proper. But the Image plugin can do thumbnail links if you're willing to create the thumbnail images yourself, using the {{link}} attribute, e.g.,

{{{
[{Image src='images/ref/image_thumb.png' link='images/ref/image.png'}]
}}}

When you click on the image thumbnail the full size image will be displayed.


!!CSS

;__{{.imageplugin}}__: The table that encompasses the image.  It consists of two subcategories:
;:__{{img}}__ = IMG tag that gets embedded.
;:__{{caption}}__ = caption that is embedded.


----
JSPWikiCorePlugins


----

How should JSPWiki be configured so that relative file name can be used
to identify an image.  In my wiki, I need to write the full path, including the drive name, 
to get the in-line image to display.


--JohnBParker, 28-Apr-2006

----

John, you can use the [Image] plugin to do this. If you are planning to upload a bunch of
images and have access to the wiki directory on the server you can put them all in, say,
the existing 'images' directory. For myself, I wanted to keep the images used for the
wiki itself separate from those used for my reference documentation, so I created a 'ref'
subdirectory (i.e., '$JSPWIKI_HOME/images/ref/'). Then I can use relative links via the
Image plugin, e.g.:

{{{
[{Image src='images/ref/penguin.png' alt='Adelaide Penguin'}]
}}}

It's also good practice to include alternate text using the '{{alt}}' attribute (actually,
this is a validation requirement in XHTML).

Hope that helps. -- MurrayAltheim


----

I am having some problems with .png images added using the plugin. jspwiki seems to think that they are some sort of links and is putting link image on top of the attached images. 

with JPG and gif files it does not do this and does think that they are links.

i am not too experienced with this, i would really appreciate some help.

thanks
R

--Rayalu, 20-Sep-2006

----

Rayalu, in the WEB-INF/jspwiki.properties configuration file there should be a set of lines defining the image types you want to permit on your wiki. They must have distinct suffix numbers as described in the jspwiki.properties file following "Define which image types are inlined." The lines in the default are commented out, and the note states that by default JSPWiki recognizes PNG only. 

For example, if you wanted your wiki to permit gif, jpg and png files, your properties file would contain:
{{{
jspwiki.translatorReader.inlinePattern.1 = *.gif
jspwiki.translatorReader.inlinePattern.2 = *.jpg
jspwiki.translatorReader.inlinePattern.3 = *.png
}}}

Since you state that you're not having any problems with JPG or GIF you may have a problem with this part of your configuration. If it's not that, you might check with another browser to see if it's browser-related and not actually a problem with JSPWiki itself.

Hope that helps. -- MurrayAltheim



----

I am trying to use the Core Image Plugin however I keep getting "
Plugin insertion failed: Plugin failed".  I am not sure what to do from here since I am not the system admin.  
{{{[{Image src='http://pathname/NavigationEditor.png'}]}}}  \\
Any clues?\\
-Joelle

--[JoelleLam|mailto:joelle.lam@sun.com], 04-Jan-2007
