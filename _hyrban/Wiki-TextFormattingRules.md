[{ALLOW delete Roland}]
[{ALLOW view Anonymous}]
[{ALLOW view ALL}]

When you've figured out how the editor works, then you should read [Wiki-Etiquette] so that you would know how to use your newly acquired skills...

[{TableOfContents}]

!!Quick reference

{{{
----       = Make a horizontal ruler. Extra '-' is ignored.
\\         = force a line break, \\\=force line break and clear.

[link]     = creates a hyperlink to an internal WikiPage called 'Link'.
[this is also a link] = creates a hyperlink to an internal WikiPage called
'ThisIsAlsoALink'.
[click here|link] = creates a hyperlink to an internal WikiPage called
'Link', but displays the text 'click here' to the
user instead of 'Link'.
[1]        = Makes a reference to a footnote numbered 1.
[#1]       = Marks the footnote number 1.
[[link]    = creates text '[link]'.

!heading   = small heading with text 'heading'
!!heading  = medium heading with text 'heading'
!!!heading = large heading with text 'heading'

''text''   = prints 'text' in italic.
__text__   = prints 'text' in bold.
{{text}}   = prints 'text' in monospaced font.

* text     = makes a bulleted list item with 'text'
# text     = makes a numbered list item with 'text'
;term:ex   = makes a definition for 'term' with the explanation 'ex'
}}}

!!Writing text

You don't need to know anything about the Wiki text formatting rules to use Wiki.  Just write normal text, and then use an empty line to mark a paragraph.
It's just like writing an email.

You can always Edit this page (look at the left sidebar) to see how the different
effects on this page are used.

!Adding pictures

You can embed any image in the wiki code by putting the image available somewhere on the web in one of the allowed formats, and then just linking to it.
For example, this is an inlined [PNG] image: [http://www.ecyrd.com/~jalkanen/test.png].

If you specify a link text ([[this one here|http://example.com/example.png]) it becomes
the ALT text for those who either can't or don't want to view images.

You can also attach an image, and refer to it as if it were any other page.  See [WikiAttachments] for more information.

If you need more layout control (or things like captions), check out the [Image] -plugin.  It can do oodles more than just simple embedding.

The list of accepted image types depends on the Wiki.  See the [SystemInfo]
page for a list of the different image types.

!Headings

JSPWiki gives you three kinds of headings: A small one (denoted by starting a line with a single exclamation mark '!'), a medium-sized one (two exclamation marks), or a large one (three marks).

All headings also generate a "named anchor", so that you can refer from other wikipages to this wikipage.  See [Named Headings] for more information.

!Bulleted lists
Use an asterisk (*) in the first column to make bulleted lists. Use more asterisks for deeper indentation. For example:
{{{
* One
* Two
* Three
** Three.One}}}

creates
* One
* Two
* Three
** Three.One

!Numbered lists
Just like with bulleted lists, but use a hash (#) instead of the asterisk. Like this:
{{{
# One
# Two
# Three
## Three.One
}}}

creates
# One
# Two
# Three
## Three.One

If you want to write the list item on multiple lines, just add one or more spaces on the next line and the line will be automatically added to the
previous item.  If this sounds complicated, edit this page for an example, below.

* This is a single-line item.
* This is actually a multi-line item.
  We continue the second sentence on a line on a line of its own.
  We might as well do a third line while we're at it...
  Notice, however, as all these sentences get put inside a single item!
* The third line is again a single-line item for your convinience.

__Alphabetical lists__\\
To get the list display with an alphabetical numbering, insert the stylesheet "alphalist" outside the hash (#) lists like this
{{{
%%alphalist
# one
# two
# three
/%
}}}

creates

%%alphalist
# one
# two
# three
/%


!Definition lists and comments

A simple way to make definition lists is to use the ';:' -construct:

;__Construct__:''Something you use to do something with''

Another nice use for the ';:' is that you can use it to comment shortly on other people's text, by having an empty 'term' in the definition, like this:
{{{
;:''Comment here.''
}}}
Which would be seen as
;:''Comment here.''

!Text effects

You may use __bold__ text or ''italic'' text, by using two underscores (_) and two single quotes ('), respectively. If you're on a Windows computer, make sure that you are using the correct quote sign, as there is one that looks the same, but really isn't.


!Preformatted text

If you want to add preformatted text (like code) just use three consecutive braces ({) to open a block, and three consecutive braces (}) to close a block. Edit this page for an example.

!Pretty preformatted text

If you want code colouring (based on [Google's code prettifier|http://google-code-prettify.googlecode.com/svn/trunk/README.html]) then use prettify:

{{{
%%prettify
{{{
your prettified code snippet
<triple } } } to close the code block>
/%
}}}

for example:

%%prettify
{{{
#!/bin/bash

# Fibonacci numbers
# Writes an infinite series to stdout, one entry per line
function fib() {
  local a=1
  local b=1
  while true ; do
    echo $a
    local tmp=$a
    a=$(( $a + $b ))
    b=$tmp
  done
}

# output the 10th element of the series and halt
fib | head -10 | tail -1
}}} /%


!!Linking around

Links are an integral part of Wikis.

!Linking to a WikiPage

Just type the name of the page within brackets: [[Like this].  This will create automatically a link to a page.

Note also that this Wiki can be configured to support standard CamelCase linking (if it's supported, the word CamelCase should be a link).  It's off by default, but if your friendly administrator has turned it on, then well, CamelCase all you want =).

!Linking to an anchor within the same page

Every header on the page automcatically generates an anchor. Therefore to link to that anchor simply create a link like this [[link text | PageName#HeaderTitle"]] thus this link should link you to the style heading [below|WIki-TextFormattingRules#Styles].

!Linking to external sites

The link can also be a direct URL starting with http:, ftp:, mailto:, https:, or news:, in which case the link points to an external entity. For example, to point at the java.sun.com home page, use [[http://java.sun.com], which becomes [http://java.sun.com/] or [[Java home page|http://java.sun.com], which becomes [Java home page|http://java.sun.com].

!Footnotes

These are a special kind of hyperlink.  By using nothing but a number inside
a hyperlink you create a reference to a footnote, like this [[1], which 
creates a footnote[1].  To make the actual footnote, you just put a [[#1]
where you want that footnote to point at.  Look below to find the footnote.

You can also make a named footnote, just as if you were doing a normal hyperlink.  For example, this refers to the same footnote[Footnote number 1|1] as the footnote above, but this refers to another footnote[2].

!InterWiki links

You can also do links between different Wikis without knowing the URL.  Just use a link in the form [[Wiki:WikiPage] and JSPWiki will create a link for you.  For example, this link points to the [JSPWiki TextFormatting rules|JSPWiki:TextFormattingRules]. Check the [SystemInfo] page for more information on which Wiki links are available.

If an InterWiki link is not supported, you'll get a notification of it on the page when
you save your page.

!!Tables

You can do simple tables by using using pipe signs ('|').  Use double pipe
signs to start the heading of a table, and single pipe signs to then
write the rows of the table.  End with a line that is not a table.

For example:

{{{
|| Heading 1 || Heading 2
| ''Gobble'' | Bar
| [Main]     | [SandBox]
}}}

gives you the following table.  Note how you can use links also inside tables.

|| Heading 1 || Heading 2
| ''Gobble'' | Bar
| [Main]     | [SandBox]

!!! Special table effects

To have a table with no borders shown, add the borderless tag:

{{{
%%borderless
|| Heading 1 || Heading 2
| ''Gobble'' | Bar
| [Main]     | [SandBox]
}}}

produces

%%borderless
|| Heading 1 || Heading 2
| ''Gobble'' | Bar
| [Main]     | [SandBox]

The noBorders tag does something similar


To have sortable tables, add the sortable tag

{{{%%sortable
|| Heading 1 || Heading 2
| ''Gobble'' | Bar
| [Main]     | [SandBox]
/%
}}}

%%sortable
|| Heading 1 || Heading 2
| 10 | Bar
| 20 | Table
| 30 | Napkin
/%


Within a table cell:
noWrap will prevent a cell from wrapping

{{{%%noWrap Time (mins)/%}}}

tdRight will force a cell's contents to be right aligned (also tdCenter)

{{{%%tdRight Right align this text/%}}}

! The table plug-in
Note that this wiki has the Table plug-in installed which lets you do all sorts of fancy thing like spanning columns and row, conditional formatting and so forth. For more details please see the page on [the table plug-in|TablePlugin].

!!Styles

%%commentbox
__Hi there!__\\
It's actually quite possible to do things like put comment boxes like this directly on your WikiPage.  This sample comment box uses the "commentbox" style, as defined in the included "jspwiki.css" style sheet. To make a box like this, just use {{{%%commentbox <text> %%}}} but note that it won't appear in a PDF produce via Wiki2PDF.
%%
In addition to the simple styles represented by the WikiMarkup, we also allow you to put in your own styles.  For example:
{{{
%%small
This is small text
%%
}}}
uses the defined CSS style called "small", as defined in the jspwiki.css file.  These may vary from site to site, and it is up to the site administrator to define a style.

You can also define almost any CSS style command:
{{{
%%( font-size: 150%; color: red; )
Hello, world!
%%
}}}
would render as:
%%( font-size: 150%; color: red; )
Hello, world!
%%

__NOTE__ You have to mark the end of the text you want to finish being styled using {{{%%}}}! 

!!Managing your Wiki

!Conflicts

If someone happens to edit the same page as you at the same time, JSPWiki will prevent you from doing changes and show a conflict page instead. Sorry to say, but the first one to make changes wins...

__A word of warning:__ If you use the Back button of your browser to go into the Edit page, you will almost certainly get a conflict. This is because the browser thinks its still editing an earlier copy of the page.

!Deleting pages

Every page has a "More Info..." link on the bottom.  If you click on it, you arrive on a page which allows you to, among other things, restore old versions and delete pages.  Note that your administrator may have prevented deleting pages arbitrarily.

!Adding new pages

Create a link that points to a new (not existing) page using its [WikiName].
Click that new link, which should now have a question mark (?) suffix and
you will get an editor for the new page.

!Attaching files

If the administrator of the wiki has configured it, there is a "Attach file..." link at the bottom of every page.  Clicking it allows you to attach files into pages.  For more information, please see [WikiAttachments].

!!Variables, plugins, forms and other special functions

!Inserting variables

There are many possible variables you can insert on a page.  The basic form is:

{{ [[{$variablename}], }}

where ''variablename'' is the name of the variable you want to insert.  Note that variable names are case-insensitive - that is, "pagename" is the same as "paGeNamE" and "PageName".

You can see the list of available of variables at [WikiVariables].

!Inserting plugins

The basic incantation to insert a plugin looks like this:

[[{INSERT <plugin class> WHERE param1=value, param2=value, ...}]

There is more information in [JSPWikiPlugins].

!Inserting forms

Please see [WikiForms].

!!Tabbed Pages

If you want to add in tabs on a page then insert

{{{
%%tabbedSection

%%tab-Name-1
Some text
/%

%%tab-Name-2
Some more text
/%

}}}

etc.

!!Table of Contents

This is automatically added when you save a page.

To include a TOC simply insert

{{{[{TableOfContents}]}}}

in your document

!!Images
There is information on images in the [image formatting|ImageFormattingRules] page.

!! Bushed template typography
The Quru skin is on the top of the brushed template. For this there is some interesting [typographic enhancements| Brushed-Template-Typography ]

!! Security
There used to be some easy ways to implement security but not currently.

To add ACLs to each document add the following lines:

{{{ [{ALLOW <access class> <Name>[<Name>]}] }}}

So that, for example

{{{ [{ALLOW view Bonhams, Jim }]
[{ALLOW delete Quru }] }}}

wold allow people in the Bonhams group and Jim to view the document and people in the Quru group to amend, update or delete the document (and add attachments).

Other access classes include

|| Title || Rights
| rename |  implies "modify"
| modify | implies "edit" and "upload"
| edit | User can edit the document; implies "view" and "comment"
| upload | User can add attachments; implies "view"
| delete | User can add, modify, delete and attach; implies "edit"
| view | User can read only.

----

[#1] Here's the footnote I mentioned.

[The other footnote|#2] The other footnote.  Note how it's name is different?

!! CSS Styles

There are all sorts of other styles that you should look at [here|JSPWikiStyles].

!! Chaining together pages

It is possible to chain two wiki pages together thereby creating a large page. Follow these [instructions|Wiki-HowToInsertAPage] to find out how.