
# HTML

{A script is a series of instructions that a computer can follow one-by-one.
Each individual instruction or step is known as a statement.
Statements should end with a semicolon.}

Since each of these three languages serves a different purpose, web developers generally use separate files for each one. This idea is called “separation of concerns“- each file should have a different function within the site as a whole.

Although you could technically include all the code in one HTML file, that will eventually lead to repetitive code as you grow your site.

Let’s look at the code needed to create one complete house. All 3 files must be in the same directory– a folder on your computer. In this case, let’s call the folder house. In our house folder, we will have one file of each type. I will call the main HTML file index, the main CSS file styles, and the main JavaScript file scripts.

You can use this interactive image to flip between the 3 parts of a house and the file system.

Now we can cover the way that files become linked in code.

Our HTML file actually has three separate sections:

The <head>, where you can include metadata and links to services like Google Fonts
The <body>, where you include the actual HTML elements
The <script> tags, which can link to Google Analytics and JavaScript files
Right now, all three files are contained within one folder, so the file paths are pretty simple within the HTML file.

**WHAT IS A VARIABLE?**
A script will have to temporarily store the bits of information it needs to do its job. It can store this
data in variables. When you write JavaScript, you have to tell the interpreter every individual step that you want it to perform. This sometimes involves more detail than you might expect.


**CSS Introduction**
*What is CSS*
1. CSS stands for Cascading Style Sheets
2. CSS describes how HTML elements are to be displayed on screen, paper, or in other media
3. CSS saves a lot of work. It can control the layout of multiple web pages all at once
External stylesheets are stored in CSS files

*Why Use CSS?*
CSS is used to define styles for your web pages, including the design, layout and variations in display for different devices and screen sizes.

CSS Example
body {
  background-color: lightblue;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 20px;
}

CSS Solved a Big Problem
HTML was NEVER intended to contain tags for formatting a web page!

HTML was created to describe the content of a web page, like:

<h1>This is a heading</h1>

<p>This is a paragraph.</p>

When tags like <font>, and color attributes were added to the HTML 3.2 specification, it started a nightmare for web developers. Development of large websites, where fonts and color information were added to every single page, became a long and expensive process.

To solve this problem, the World Wide Web Consortium (W3C) created CSS.

CSS removed the style formatting from the HTML page!