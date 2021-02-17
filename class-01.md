#html
Introduction to the structure of an HTML document
An HTML 4 document is composed of three parts:

1. a line containing HTML version information,
2. a declarative header section (delimited by the HEAD element),
3. a body, which contains the document's actual content. The body m3. ay be implemented by the BODY element or the FRAMESET element.
****** 

White space (spaces, newlines, tabs, and comments) may appear before or after each section. Sections 2 and 3 should be delimited by the HTML element.

Here's an example of a simple HTML document:

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"
   "http://www.w3.org/TR/html4/strict.dtd">
<HTML>
   <HEAD>
      <TITLE>My first HTML document</TITLE>
   </HEAD>
   <BODY>
      <P>Hello world!
   </BODY>
</HTML>




**HyperText Markup Language – HTML**

{What Is HyperText Markup Language (HTML)?
HyperText Markup Language (HTML) is the set of markup symbols or codes inserted into a file intended for display on the Internet. The markup tells web browsers how to display a web page's words and images.}


Each individual piece markup code (which would fall between "<" and ">" characters) is referred to as an element, though many people also refer to it as a tag. Some elements come in pairs that indicate when some display effect is to begin and when it is to end.


*KEY TAKEAWAYS*
1. HyperText Markup Language (HTML) is the basic scripting language used by web browsers to render pages on the world wide web.
2. HyperText allows a user to click a link and be redirected to a new page referenced by that link.
Early versions of HTML were static (Web 1.0), while newer iterations feature a great deal of dynamic 3. flexibility (Web 2.0, 3.0).
Markup is the text that appears between two pointed brackets (e.g., <footnote>), and content is everything else.
*HTML Explained*
{HyperText Markup Language is the computer language that facilitates website creation. The language, which has code words and syntax just like any other language, is relatively easy to comprehend and, as time goes on, increasingly powerful in what it allows someone to create. HTML continues to evolve to meet the demands and requirements of the Internet under the guise of the World Wide Web Consortium, the organization that designs and maintains the language; for instance, with the transition to Web 2.0.}

HyperText is the method by which Internet users navigate the web. By clicking on special text called hyperlinks, users are brought to new pages. The use of hyper means it is not linear, so users can go anywhere on the Internet simply by clicking on the available links. Markup is what HTML tags do to the text inside of them; they mark it as a specific type of text. For example, markup text could come in the form of boldface or italicized type to draw specific attention to a word or phrase.

*******

**HTML Layout Elements and Techniques**
*HTML Layout Elements*
HTML has several semantic elements that define the different parts of a web page:

HTML5 Semantic Elements	
<header> - Defines a header for a document or a section
<nav> - Defines a set of navigation links
<section> - Defines a section in a document
<article> - Defines an independent, self-contained content
<aside> - Defines content aside from the content (like a sidebar)
<footer> - Defines a footer for a document or a section
<details> - Defines additional details that the user can open and close on demand
<summary> - Defines a heading for the <details> element
You can read more about semantic elements in our HTML Semantics chapter.

*HTML Layout Techniques*
There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

1. CSS framework
2. CSS float property
3. CSS flexbox
4. CSS grid

**PROCESS & DESIGN**
*steps to design a website requires 7 steps:*

1. Goal identification: Where I work with the client to determine what goals the new website needs to fulfill. I.e., what its purpose is.
2. Scope definition: Once we know the site's goals, we can define the scope of the project. I.e., what web pages and features the site requires to fulfill the goal, and the timeline for building those out.
3. Sitemap and wireframe creation: With the scope well-defined, we can start digging into the sitemap, defining how the content and features we defined in scope definition will interrelate.
4. Content creation: Now that we have a bigger picture of the site in mind, we can start creating content for the individual pages, always keeping search engine optimization (SEO) in mind to help keep pages focused on a single topic. It's vital that you have real content to work with for our next stage:
5. Visual elements: With the site architecture and some content in place, we can start working on the visual brand. Depending on the client, this may already be well-defined, but you might also be defining the visual style from the ground up. Tools like style tiles, moodboards, and element collages can help with this process.
6. Testing: By now, you've got all your pages and defined how they display to the site visitor, so it's time to make sure it all works. Combine manual browsing of the site on a variety of devices with automated site crawlers to identify everything from user experience issues to simple broken links.
7. Launch: Once everything's working beautifully, it's time to plan and execute your site launch! This should include planning both launch timing and communication strategies — i.e., when will you launch and how will you let the world know? After that, it's time to break out the bubbly.

## javasicript

{JavaScript was developed by Brendan Eich in 1995, which appeared in Netscape, a popular browser of that time. The language was initially called LiveScript and was later renamed JavaScript. There are many programmers who think that JavaScript and Java are the same. In fact, JavaScript and Java are very much unrelated.}

*The ABC of Programming*:
ABC is an interactive programming language and environment for personal computing, originally intended as a good replacement for BASIC. It was designed by first doing a task analysis of the programming task.

ABC is easy to learn (an hour or so for someone who has already programmed), and yet easy to use. Originally intended as a language for beginners, it has evolved into a powerful tool for beginners and experts alike.

Here is an example function words to collect the set of all words in a document:

   HOW TO RETURN words document:
      PUT {} IN collection
      FOR line IN document:
         FOR word IN split line:
            IF word not.in collection:
               INSERT word IN collection
      RETURN collection
Some features of the language:

a powerful collection of only 5 data types that can easily be combined
strong typing, yet without declarations
no limitations (such as max int), apart from sheer exhaustion of memory
refinements to support top-down programming
nesting by indentation
programs typically one fourth or one fifth the size of the equivalent Pascal or C.
Some features of the environment:

no need for files: procedures and functions and global variables remain after logging out
one consistent face is shown to the user at all times, whether executing commands, editing, or entering input to a program
generalized undo mechanism.