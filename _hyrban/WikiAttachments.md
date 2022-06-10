A WikiPage can have any number of attachments.  An attachment can be any file, even a file that contains WikiMarkup.  These files are handled very similarly to any email program, i.e. you "Attach a file" (see bottom of this page), etc.

The name of an attachment is of form {{~PageName/attachment name}}, where the ~PageName signifies the "owning" page.  In the future, the access rights of an attachment will be the same as the access rights of the page, and thus we need a sort of a "parent" page for each attachment.  Besides, calling them "attachments" without something to attach them to would be kinda odd, yes? The "attachment name" is the original file name. These names are case sensitive and hyphens should be removed.

You can refer to an attachment simply by putting its name in full form in brackets, just like when referring to any WikiPage.  For example, [[TestPage/testpicture.png] would refer to the "testpicture.png" that has been attached to page "~TestPage".  However, if you're on the same page, then you don't need to name the page, i.e. on this page, [[WikiAttachments/test.txt] is the same as referring to [[test.txt].  In case you happen to have a WikiPage and an attachment of the same name, the attachment takes precedence[1].

If the attachment is an image, and that particular image type has been defined for automatic inlining, then the image gets inlined.  This means that you can treat a link to an attachment just like you would treat any link that goes outside this Wiki.

Each attachment (except for inlined images) has a small paperclip icon next to it.  Clicking this icon takes you to the ~PageInfo display, which is very similar to viewing the page info of any normal WikiPage.  In fact, it is actually the same JSP file...  From there, you can download older versions, or upload new versions of that attachment.  If you upload a new version of the attachment, the file name does not need to be the same at all.

If you click on "Attach file..." -link and nothing happens, make sure you have Javascript and popups enabled.  I am experimenting with this simple popup window for uploading, and if it is a problem, then I'll replace it with something else.  However, if we want to do stuff like a upload progress indicator, we really do want them in a separate window.  Besides, if you have a popup disabler software that disables windows that open on explicit clicks, then you probably have a very faulty popup disabler :).

--[JanneJalkanen], 08-Dec-2002.

[#1] This may still change.

----
Proposed solution: the non-ascii-characters in file name of attachments
I have encountered the same problems as [dingyh] below, so that I tried to fix it.
Here is my solution: I changed the one line code in the file - AttachmentServlet.java (v 2.0.52) as below:

{{{
Line 130:
 res.setHeader( "Content-Disposition", 
                "inline; filename=" + TextUtil.urlEncodeUTF8(att.getFileName()) + ";" );
}}}

If you guys encounter the same problems with your non-ascii attachment file name, you could download the [class file|AttachmentServlet.class], replace the original one in the lib/JSPWiki.jar (don't forget put it in the same directory).

Or, you'd like to re-build the whole package with the [source code file|AttachmentServlet.java]

If you'd like to test the function I mentioned, there are some attachments with non-ascii name for download: http://134.208.20.89/wiki/Wiki.jsp?page=FilingY88

-- [Geoffrey]

----
Q:I just upload a file with no-ascii name, it shows well as "PPT箇条書きと段落番号の解析レポート.jtd",
but can not download it! because the link name is vague, such as "PPT%E7%AE%87%E6%9D%A1%E6%9B%B8%E3%81%8D%E3%81%A8%E6%AE%B5
%E8%90%BD%E7%95%AA%E5%8F%B7%E3%81%AE%E8%A7%A3%E6
%9E%90%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88.jtd".\\
-- [dingyh]

Don't know about the content but I managed to download that attachment just fine... has it been fixed or do you have encoding problems in your browser?\\
-- [ErkWriter]

----

Nice, me likes. Especially since it retains the image inlining feature, something I'd consider essential
in intranet use. 

One question: is anything in brackets with a dot in the name considered an attachment name?

--[ebu]

Nope.  We make as little assumptions as possible about the attachment name.  We use a slash as a separator, but we always search through the attachment name space first, then the wikipage space.  If the link cannot be found from either, it's assumed to be a standard WikiName.  For example: [[sampledocument.rtf] is assumed to be a WikiPage, since it does not exist as an attachment of this page.

-- JanneJalkanen

----

Any way to remove attachments once they've been attached?  --[IanT]

At the moment: no. You need to delete the attachment directory in the file system. API hooks for attachment and version deletion are in there, and a management page will appear RSN. --[ebu]

The directory name for the attachments is the name of the page the file is attached to followed by the suffix hyphen "att". E.g. for Main the directory would be "Main-att". You can rename the directory back and forth to make the attachments appear and disappear on the page.

Too bad... it doesn't seem like a particularly difficult thing to do either, so long as you can accept the destructive consequences. Seems like ~PageInfo could provide an extra link per version of the attachment to delete that version, and perhaps one to delete the entire attachment directory. Also, perhaps renaming an attachment might be useful instead of having to delete one, then reload it as a different name. --[RobSeegel]  

It's coming; I just checked in a bunch of code on this very subject. --JanneJalkanen

I think a better user interface would be to amend the link at the bottom of the page from "{{Attach file...}}" to "{{Manage Attachments...}}". And within the pop-up window from this link, add a "{{Delete}}" button beside each of the listed, existing attachments for the current page. Clicking a button will delete the associated attachment. You could also add another single button at the top of the pop-up window to "{{Delete all attachments}}". -- S5b

----

Q: Problem: After pressing ''upload'' nothing happens. No error message, no change on the page. A 'find / -name "<the file name>"' on the server does not find the file. On the server I'm just using tomcat4, no apache. \\--[Rsc]

''Please check the logs (see jspwiki.properties for the log level and its location).  My first guess would be that you have a) not enabled attachments at all, or b) the attachments directory does not exist or that you have problems accessing it. --JanneJalkanen''

oki - found an example on [http://www.ecyrd.com/JSPWiki/Wiki.jsp?page=FixedBugs], wonder where those things are documented. --[Rsc]

----

I have a [page|http://153.106.130.19/JSPWiki/Wiki.jsp?page=KalsQuest] with attachment version1.jpg.  This works fine.  But on the [UndefinedPages|http://153.106.130.19/JSPWiki/Wiki.jsp?page=UndefinedPages] page, it lists version1.jpg.  How can I make it not show up as undefined? --[DaveBrondsema]

;:''There is a bug in JSPWiki in which if you don't precede the attachment name with the page name (KalsQuest/version1.jpg, in your case), it shows up as an undefined page.  I fixed it for you.  --MichaelGentry''

----

Must the attach function really use java-script? 
The way the attachments are saved are really complicated. Also, see [AttachDirNotFound].

--SebastianPetzelberger

;:''The javascript is only used to pop up a separate attachment window. This is a conscious usability decision. The easy way to get rid of it is to edit the file ~PageContent.jsp and remove the javascript from around the {{<wiki:UploadLink format="url" />}} tag.'' --[ebu]

----
!Help !!!!!
Q:Is there a way to edit and save an uploaded file???
--New User

A:Yes, there is. Click on the big Attachment icon at the bottom of your page. You'll 
get an overview of the available versions of the attachment and be given the
possibility to upload a new version.
--DirkFrederickx

-------
!Can I inline an WikiMarkup attachment

I think it could be useful to show an WikiMarkup attachment inlined (embed) with a link.
As an example: [MyLargeTable.txt] could show here and I could easily update the table in any spreadsheet program while saving as .csv with | as separator. As an excersise I made this simple plugin to do the job: [InsertAttachment plugin|http://revontuli.zapto.org:8080/rtWiki/Wiki.jsp?page=PluginInsertAttachment]

-[Petes|http://revontuli.zapto.org:8080/rtWiki/Wiki.jsp?page=Petes]
----
!Can I hide/disable paperclip icon next to attachment link?

As much as I understand, authorization doesn't refer to attachments but to WikiPages only (at least I can not find any information about that). Page authorization does not apply to attachment pages on the page - an user that is not authorized to edit WikiPage is in fact authorized to change its attachments (by clicking on the paperclip icon next to a link on that or some other page). This means that if I publish a document as an atachment and have a link on that attachment somewhere else, __any__ user can replace the document (using ~PageInfo). Help??

--[MTosic]
----
Question: JSPWiki.org has a delete page and delete attachment feature.  How do I get that in my wiki?  Downloaded the newest v2.1.164 and the code isn't in there.  What am I missing?

Answer: Yes, it is there (it is certainly here).  Note that you will need to install the relevant portions of the default template (esp. ~InfoContent.jsp), if you want the page deletion to actually have an user interface...

Better Answer: add delete permission to users via the jspwiki.policy file.  For example, for authenticated users you may want to have the following line:

permission com.ecyrd.jspwiki.auth.permissions.PagePermission "*:*", "modify,rename,delete";

----
!How to make the attachment downloadable?
I'm running jspwiki on Netscape Enterprise Server, for some reason all the attachments (including binary files) I uploaded opens it in a browser rather than prompting me to download it.  Can anyone help me? Thanks! 

----

%%(border: 1px solid inset black; padding: 4px; color: red;)
If you want to test attachments, please go to [The Sandbox|http://sandbox.jspwiki.org]!
%%


----

----
[RAF] - Hi!  I have the problems that the attachments are being saved in the correct directory - I can see the attachment and the description.  However, when I try to refer to the attachments from the page it seems to look in the wrong place:\\

\\{{{/wiki_VVV/attach/SandBox/logo_v2.gif}}}\\

I understand that the attach dir is a pointer to a servlet, but for some reason it ain't working.

R!

--AnonymousCoward, 12-Jan-2006

----
! Question about attachment limitations

Question: Is there a limit to the number of attachments a wiki page may have?  Am I limited by the number of files allowed in a Windows directory?  I may have as many as 50,000 attachments.  Also, what if I had 100,000 or 200,000 attachments in the whole system (not all would exist in the same directory)?  
\\ 
--Patty, 01/18/06

There is no limit to the number of attachments from JSPWiki side.  However, it may be that underlying operating system has limits.

-- JanneJalkanen

it's a bad idea to not enable people to remove attachments from pages. if used in a company environment, you simply can't ask an admin any time you attached soething wrong.


[RefactorMe], this page contains obsolete information.  Deleting attachments is quite possible in new versions.


----

Question about size of attachments

Is there a limit to the size of an attachment?  Can limits be set?

--AnonymousCoward, 31-Jul-2006

----
__Question__

Just installed and put some pages in. I cannot see any Attach File link on any of may pages.
Installed onto windows.
09AUG2006

----


----

!How to forbid attaching file types like .html?

I try to block some stupid hacker kiddies (maybe you know this little tyrkish hacker) from uploading .html, .jsp, .exe or .php files. And by the way, I would like to stop normal users from uploading .doc files, because they should use .pdf instead or write a wiki page. Not that those files would be a real danger - ok, this tyrkish kid was lucky enough to shoot my server down without knowing anything, but that is a different story. 

When I take a look at the JSPWiki code, I don't see how to make it. Can I use the permission system? What I want is a real simple solution like a properties entry in the jspwiki.properties. I tried to make it by my own with a servlet filter like it is suggested in the javadoc, but it is a real ugly task because of this multipart stuff (as far as I see it could be easily done by refactoring the AttachmentServlet and get the multipart stuff out of the servlet and into a filter, see [Filter code with Servlet 2-3 model|http://www.javaworld.com/javaworld/jw-06-2001/jw-0622-filters-p4.html]).

Any help would be greatly appreciated


--SebastianBaltes, 12-Sep-2006

JSPWiki 2.4.86 includes such a system.  Just define e.g.
{{{
jspwiki.attachment.forbid=.html .htm .php .asp .exe
}}}

in your jspwiki.properties.

-- JanneJalkanen, 28-Mar-2007

----

!On deleting attachments
Actually, it would be nice to allow by default to delete attachments uploaded by the same user that wants to delete it. (Perhaps, I just do not know how to turn such a feature on.)

--_, 25-Jan-2007

Well, you can control all the attachments of a single page by adding an ACL to that page.  But you can't control the attachment ownership directly.

-- JanneJalkanen, 28-Mar-2007

[ANSWER ME]
!Is there a faster way of uploading hundreds of files into my new installed wiki
!than to do it manually one at a time?


I have successfully loaded a few files and I can see that when I attach these files to my Main page that jspWiki places them under the expected folder but it would be nice to be able to import more than one at a time. Is this possible?

Claudia Frers, June 11, 2007
--------------------------
!!Please Help!
I have jspwiki, how I can delete sides there? Sorry for me bad english, i am from germany.
Thank
Sebastian
