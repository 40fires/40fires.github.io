JSPWiki has many variables that can be embedded in pages on the fly.  See [Text Formatting Rules] for how to do it. Quick example:

{{{
[{$jspwikiversion}]
}}}

!applicationname

This is the name of this Wiki.  It has been set by the administrator in "jspwiki.properties". This Wiki is called ''[{$applicationname}]''.

!baseurl

The base URL address for this wiki.  Example: ''[{$baseurl}]''.
* Strange, here it seems to work with the trailing slash, in our setup (Windows 2000, Apache 2, Tomcat 5.5, JSPWiki 2.2.28 the trainling slash is removed, even though defined in the property file! -- G. Hagedorn, 10-2005

!encoding

Describes the character encoding used in this Wiki. An encoding of "UTF-8" means that the Wiki accepts any character, including Chinese, Japanese, etc.  Encoding "ISO-8859-1" means that only western languages are supported.  This wiki uses the ''[{$encoding}]'' encoding.

!inlinedimages

Lets you know which image types are being inlined. Example: ''[{$inlinedimages}]''.

!interwikilinks

Writes HTML code for supported InterWiki links. Example:\\ ''[{$interwikilinks}]''.

!jspwikiversion

Inserts the version number of the JSPWiki engine.  For example, this version is ''[{$jspwikiversion}]''.

!uptime

Inserts the amount of time since this Wiki has been last restarted.  This wiki has been up for ''[{$uptime}]''.

!pagename

Inserts the current page name.  Example: This page is called ''[{$pagename}]''.

!pageprovider

The current PageProvider. Example: ''[{$pageprovider}]''.

!pageproviderdescription

A verbose, HTML description about the currently used page provider. Example: ''[{$pageproviderdescription}]''.

!totalpages

The total number of pages available in this Wiki. Example: ''[{$totalpages}]''.

!Inserting JSPWiki properties

You can also access some of the JSPWiki properties (that have been defined by the site maintainer) by using their property names directly.  See [SystemInfo] for an example.
Note that some properties might not be accessible due to security reasons.
