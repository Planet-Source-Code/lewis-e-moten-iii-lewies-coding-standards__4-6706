﻿<div align="center">

## Lewies Coding Standards


</div>

### Description

Peer into the brains of a professional programmer to learn how to become a better coder and more easily maintain your code for management and easily allow others to understand.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Lewis E\. Moten III](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/lewis-e-moten-iii.md)
**Level**          |Beginner
**User Rating**    |4.6 (65 globes from 14 users)
**Compatibility**  |ASP \(Active Server Pages\), VbScript \(browser/client side\)

**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__4-33.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/lewis-e-moten-iii-lewies-coding-standards__4-6706/archive/master.zip)





### Source Code

```
<P>
First off - these are not set in stone. Every programmer has different ideas of how things sould be - and companys too. These are mearly a guide. Even I do not follow these to perfection. But they are the general ideas behind the code that I post to this site. Also, I am always updating my thoughts on how to program. I'll attempt to update this article as time progresses.
</P>
<H3>Directory Structure</H3>
<P>
The beginning of these standards doesn't deal with the code, but the directory
structure.
I am uncertain how many people here in my industry host multiple domains
(or even subdomains) on a machine. For the purpose of easier management,
Here is the structure that I use.
</P>
<PRE>
C:\InetPub\wwwRoot\DomainName\
C:\InetPub\wwwRoot\DomainName\SubDomain\
</PRE>
<P>
So, if I have a domain called "www.lewismoten.com", the site would be located
within the following directory:
</P>
<PRE>
C:\InetPub\wwwRoot\LewisMoten.com\www\
</PRE>
<P>
Domains without a sub domain (ie - lewismoten.com without the "www.") usually
point to the same content as the sub domains "www", so just simply point
"lewismoten.com" to the "Lewismoten.com\www\" directory when you setup IIS.
</P>
<P>
Ok, This little tid-bit isn't a standard, but a brief tutorial. I have only 1
IP address, yet I have multiple domains (and sub-domains) on my computer. Here
is how I do it with Windows 2000 Advanced Server.
</P>
<P>
In internet service manager, create a new web site. The wizard pops up and asks
for some info. As a standard, I type in the full domain name including sub domains.
Actually, I create two. One for www.lewismoten.com and one for lewismoten.com.
The main part
you want to pay attention to is the Host Header for the site. You can't assign
multiple host headers to a single web site (at least I havn't attempted to do it yet),
so that is why we need two web sites. In here, I would type www.lewismoten.com.
</P>
<P>
The next part asks you for a directory location.
They both point to the same directory (\Lewismoten.com\www\).
This should be enough to get you on your feet to multiple domain hosting.
Unfortunatly, windows 2000 professional doesn't support more then one website,
so your gonna have to dig deep in your pocket just to get the advanced server for
multiple domain hosting in this regard on a single IP address.
</P>
<H3>Application Structure</H3>
<P>
When creating an application, make a name that relates to the application.
For example, a website that deals with stocks may exist in a folder called
"/Stocks/" rather then "/s239123/". It is easier to identify and manage
applications in this way.
</P>
<P>
Look at the following list of the suggested directory structure for your
application:
</P>
<PRE>
/Application_Name/
/Application_Name/ClientScripts/
/Application_Name/ActiveX/
/Application_Name/ActiveX/DLLs/
/Application_Name/ActiveX/Controls/
/Application_Name/Data/
/Application_Name/Data/csv/
/Application_Name/Data/SQL/
/Application_Name/Data/tdf/
/Application_Name/Data/txt/
/Application_Name/Data/xml/
/Application_Name/Includes/
/Application_Name/Includes/Classes/
/Application_Name/Media/
/Application_Name/Media/Flash/
/Application_Name/Media/Images/
/Application_Name/StyleSheets/
/Application_Name/Content/ (optional)
</PRE>
<P>
<B>ClientScripts</B> - These are your javascript and vbScript files that you
may need to send to the client. It is always best to seperate your script
from the web pages so that the scripts are cached on the users browser and
quickly load for new pages that make use of the same script.
</P>
<P>
<B>ActiveX</B> - If your site uses DLL's, you may want to place them in the appropriate
directory along with a batch file that will register the DLL's from the command prompt.
This is primarily for easier management if you need to copy the application to another
computer. The controls directory should contain active x controls that you make available
on the web pages.
</P>
<P>
<B>Data</B> - This is the location for all your client side data - except for the
SQL folder. The sql folder should contain batch files for transact SQL to setup
your database with the appropriate schema and any data needed for a fresh install.
If you are using an access database - it is best to have them located in a directory
that web users can not access. If this is not an option, then make a sub-directory
from the data directory named "Access" and place the files in here. You should have
2 of each database. One is the "Live" database and the other is the database for a
fresh installation.
</P>
<P>
<B>Includes</B> - Include files are server-side script files that are included in other
asp pages. Others may suggest giving them an extension of ".inc" or ".txt". I always use
".asp" because Visual Interdev does not recognize the other two when it comes to object
inheritance and coloring the code for easier reading. I also incude a sub-directory called
classes. The more recent versions of vbScript allow you to create classes and I seperate these
from the other code and think of them as little black boxes.
</P>
<P>
<B>Media</B> - If your site only includes images, then you may want to go with the generalized
standard of just naming this directory "Images". I sometimes think ahead and consider the other
types of media a site may have. Flash is the primary reason. Sometimes I give it its own directory
besides images - but placing the two in a media folder makes more sense.
</P>
<P>
<B>StyleSheets</B> - If your like me, your site has style. I like to create different styles and
give them there own sub-folders off of the style folder. This way, i can tell the difference between
the Misc. style sheets accross the site and the Main Style Sheet for the sites theme. You may want
to consider placing "some" images in this folder if they relate directly to the stylesheet.
</P>
<P>
<B>Content</B> - This is completly optional. Sometimes I use it, sometimes I do not. The main reson
you may use this is in the case that you have a little too many folders off of your application root.
More often then not, I do not use this folder - but it is here mearly as an option that you may want
to consider.
</P>
<H3>File Structure</H3>
<P>
File names are important to the programmer, and can sometimes help when a visitor
calls in with a problem and needs to identify a web page. I've dealt with one project
where a programmer decided it was best to use a giant "Select Case" statement on
a query string named "Action" to determine wich include file to load. I had a tough
time explaining to him that even though the other includes were not used, they were still
compiled with the page at execution. Also, a client calling in would have to read
the query string as well as the web page. Not too much of a hassle you may think - unless
the query string is very long. Which it was.
</P>
<P>
I like to break everything appart into seperate pages. Some people even post data back
to the same page. I like to sperate that as well. Let me give you an example of the
file structure I may have in an administration directory called "Users".
</P>
<PRE>
/Users/addUser.asp       ' Displays form to add a user
/Users/addUser.Now.asp   ' Commits action to add a user
/Users/delUsers.asp      ' Confirms action to delete users with details
/Users/delUsers.Now.asp  ' Commits action to delete selected users
/Users/edtUser.asp       ' Displays form to edit specific user
/Users/edtUser.Now.asp   ' Commits action to edit the user
/Users/lstUsers.asp      ' Lists all users in directory
</PRE>
<HR>
<H3>Templates with JavaScript</H3>
<P>
I've recently begun to re-think about how I make my websites. It used to be that I included a file
of ... pretty much static HTML at the top and the bottom of the page. Todays web-browsers are comming
with javascript as a standard. What I have begun to do is convert all that HTML to javascript and place
it into a client-side script file. At first, I started running into problems. Things like - what if
something is supposed to show up in the template on one page, but not others? What if I want to display
the number of people logged into the site? And a few more. I quickly found the answer though.
</P>
<P>
In the web page, before I call the javascript file, I define a few variables. Look at the following.
</P>
<PRE>
<SCRIPT language="JavaScript" src="ClientScripts/Template.js"></SCRIPT>
<SCRIPT language="JavaScript">
	var pStrUserName = '<%=Session("UserName")%>'
	var pBlnLoggedIn = <%=LCase(CStr(IsEmpty(Session("UserID"))))%>
	var pLngVisitors = <%=Application("Visitors")%>
	if(window.templateLoaded == true){document.write(templateHeader())}
</SCRIPT>
</PRE>
<P>
Notice how I used a variable assigned to the window object to see if the javascript loaded? This helps keep errors
down so the user isn't discouraged. Now comes the next problem - what if the user does not have javascript, or better
yet - what about search engines? My friends, I present to you a real use for the <NOSCRIPT> object for your
benefit.
</P>
<PRE>
<NOSCRIPT>
	<A href="Link1.htm">Home</A> |
	<A href="Link2.htm">Feedback</A> |
	<A href="Link3.htm">Help</A>
	<HR>
</NOSCRIPT>
</PRE>
<P>
OK, we got past a hump and hopefully reduced the bandwidth of our pages by about
... 5 to 10 kb? It all depends how big your template file is to begin with.
This should also increase performance just a wee little bit since there is less
for your ASP pages to process. Remember - ASP = Glue.
Now you may be thinking that your sites template is pretty complex. I've dealt
with a lot of complex variations of templates and basically come to this thought. If you can write it in vbScript on
the serverside, then you can do it with javascript on the client side. It just depends how much time you are willing
to dedicate to solving the problem and increasing performance. I wouldn't however - suggest editing your template on
a live site. Make a local copy first. Your visitors will be happyer.
</P>
<P>
One last little problem I see with this is for a vast majority of unpopular search engines. They usually look at the
first few lines of text on the site for a description. You can always place a few lines at the beginning of the noscript
tag. If you do, then I would suggest adding an Horizonatl Rule tag to seperate it from your links.
</P>
<H3>Editing Files</H4>
<P>
Never edit a file on a live site. I've had a few people do this on me and suddenly I have visitors sending me emails
and clients calling me asking why there site is broken. Copy the file to your own hard drive and edit it. Then - after
testing the file, copy the file to the website.
</P>
<HR>
<H3>vbScript Format</H3>
<P>
This is a big one. Many programmers have many different ideas of how you can do this. These are my own personal
commitments and are by no means set in stone. I am always changing my standards when I see a better way. It is
now that I am finally documenting them.
</P>
<P>
<B>Tabs</B> - Tabulate your code for easier reading.
</P>
<PRE>
If ThisVariable = ThatVariable Then
	Do Something Cool
End If
</PRE>
<P>
Notice that the second line "Do Something Cool" has been tabbed? Any statment that requires a closing statment
such as "For", "While", "Do", "Select Case", "With", etc. Should have its contents indented.
</P>
<P>
<B>Comments</B> - comment your code so that others can understand what you are trying to do. It may seem that
the code is screaming out to you, clear as a bell, to you - but some programmers who are not so experienced, or
even clients for that matter, may need some help.
</P>
<PRE>
' Make sure the two values are equal
If ThisVariable = ThatVariable Then
	Do Something Cool
End If
</PRE>
<P>
I also like to leave a space between the comment delimiter and the comments themselves.
</P>
<P>
<B>Characters Per Line</B> - I usually like to limit my pages to no more then 80 characters in width.
This helps to prevent scrolling horizonally when reading my code on the more common screen resolutions
today.
</P>
<P>
<B>Use Line Continuations</B> - If you have a line that is just to long, don't be afraid to break your
strings and/or code apart on multiple lines using the underscore character.
</P>
<P>
<B>Procedure Seperators</B> - At the beginning and end of each procedure, I use a comment followed by a
space and 78 dashes. This helps me find the beginning/end of each procedure.
</P>
<PRE>' ------------------------------------------------------------------------------</PRE>
<P><B>Procedure Placement</B> - I place procedures at the bottom of the code. This is so that the guts of
the code can be seen first. Sometimes I place the procedures in alphabetical order, but more commonly,
I place the procedures in the order in wich they are called from the main part of the code.
</P>
<P>
<B>Main()</B> - If I can, I try to place all code in procedures. The main guts are placed in a sub called
"Main()". This mimics other programming languages because they usually require this name to begin with.
</P>
<P>
<B>Do code before sending output</B> - This is a big one. I attempt to execute every piece of functionality
that the page offers before attempting to write out the results. WHen this is done, I'll see an error rite
away if any come up rather then hunting for it in the source code if a tag isn't closed when the error occurs.
(examples - SELECT, TABLE, TEXTAREA, etc.)
</P>
<P>
<B>Variable Names</B> - This is where programmers battle it out. Even though vbScript doesn't use
types other then variants, it is helpful to understand that there are sub-types as well. A string
of "1" is not equal to the number 1.
</P>
<P>
When it comes to defining variant names, most programmers use the Hungarian Notation - or a slight
modification closly related to it. Hungarian was primarily developed for C by one of the programmers
at Microsoft, but has been adapted for many other languages over time. Here are my methods.
</P>
<PRE>
Dim StrName - String (Unicode)
Dim BinName - String (Ascii)
Dim LngName - Long
Dim IntName - Integer
Dim BytName - Byte
Dim ClsName - Class
Dim ObjName - Object
Dim DtmName - Date/Time
Dim VarName - Variant
Dim BlnName - Boolean
</PRE>
<P>
There are also a few scope variables that I prefix the variables with.
</P>
<PRE>
Dim StrName - Page Scope
Dim gStrName - Global Scope (Usually found in Include files)
Dim pStrName - Parameter (Used for arguments passed to Subs and Functions)
Dim lStrName - Local Scope (Used within the subs and functions themselves)
</PRE>
<P>
There is one last part of my naming conventions and that is to define Arrays. I add a suffix to the
end of my variables "Ary" so that if i had a List of numbers, I would call the variable "LngNameAry".
</P>
<P>
<B>Variable Declaration</B> - Always declare your variables. This means that if you use a variable anywhere on your page, then you should have it defined somewhere on the page using the Dim or Const keywords. I always place the declarations at the top of the page along with comments describing "ALL" variables. If the variable has local scope (within a procedure) then declare the variable at the beginning of the procedure before you write the code.
To hlep you make certain that all variables are declared, you may insert "Option Explicit" on the first
line of your code. It will result in raising an error any time a variable is found that hasn't been
previously declared.
</P>
<P>
Also - use names that make sense. In javascript, I often see that "<I>i</I>" represents a counter position, or an index. This is pretty common and widely known. When others begin to use single letters for other variables, It becomes very confusing to understand what the code is doing at a quick glance. I often find myself renaming variables in other peoples code just so I can comprehend the process being carried out.
</P>
<P>
If there is a common known name for a variable (Such as Conn for ADODB.Connection), Then by all means - use that name!
</P>
<P>
When creating the names, I use lower case letters except for the first letter of each word. Look at these for an example.
</P>
<PRE>
Dim StrThisIsAVariable
Dim StrAnotherOne
Dim LngLookHere
</PRE>
<P>
That shoud give you a basic idea. Some people Don't capitalize the first letter of the Variant Type (Eg - the "S" in "StrAnotherOne". This is fine by my standards. I can easily see what it is. The capitalization is primarily to help reading the variables.
</P>
<P>
Constants are sometimes treated differently. It is suggested that you use ALL UPPER CASE LETTERS seperated_by_an_underscore "_" character. Look at the following examples:
<PRE>
Const StrTHIS_IS_A_VALUE = "Lewie"
Const LngANOTHER_ONE = 3
Const LngLOOK_HERE = &h0032
</PRE>
<P>
<B>Garbage Collection</B> - Any objects that are created "MUST" be removed from memory to allow resources
to become available.
</P>
<XMP>
Set ObjName = Nothing
</XMP>
<P>
<B>Tabbing in columns</B> -
This one isn't used quite so often by others in the industry, but I find it pleasing
to the eye. If I have a few variables being assigned values, I try to tab the values
into a seperate column. Take this for example:
</P>
<PRE>
LngMemberID       = VarDataAry(0, LngIndex)
StrMemberName     = VarDataAry(1, LngIndex)
StrMemberPassword = VarDataAry(2, LngIndex)
</PRE>
<P>
Notice how everything is lined up? I also do the same thing when I declare variables.
</P>
<PRE>
Dim LngMemberID       ' Identification of member within database
Dim StrMemberName     ' Member login name
Dim StrMemberPassword ' Password for member to login with
</PRE>
<H3>Theory Behind ASP</H3>
<P>
As most of you may have heard ... ASP is supposed to be the <I>GLUE</I> to a dynamic
website. Unfortunatly, it seems that everyone places all business logic within
the ASP. And why not? It is so convienient, easily updatable, and easy to
distribute. With .Net, The original theory behind ASP will no longer apply.
</P>
<P>
When I first got into the IT industry (professionally that is), the project I
was working on consisted of a Transaction Server (Today it is known as COM+)
that contained DLL's compiled by Visual Basic. All of the main logic was located
within them and the asp page called upon them for the data. It would then format
the page according to the data returned. It didn't do any more logic other then
that. This is the guts of the original theory behind ASP.
</P>
<P>
Today, XSL follows the <I>GLUE</I> theory, in that it doesn't do too much programming.
</P>
```

