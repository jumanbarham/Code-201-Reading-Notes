# HTML Forms 
are required, when you want to collect some data from the site visitor. For example, during user registration you would like to collect information such as name, email address, credit card, etc.

A form will take input from the site visitor and then will post it to a back-end application such as CGI, ASP Script or PHP script etc. The back-end application will perform required processing on the passed data based on defined business logic inside the application.

There are various form elements available like text fields, textarea fields, drop-down menus, radio buttons, checkboxes, etc.

The HTML <form> tag is used to create an HTML form and it has following syntax −

<form action = "Script URL" method = "GET|POST">
   form elements like input, textarea etc.
</form>
Form Attributes
Apart from common attributes, following is a list of the most frequently used form attributes −

Sr.No	Attribute & Description
1	
action

Backend script ready to process your passed data.

2	
method

Method to be used to upload data. The most frequently used are GET and POST methods.

3	
target

Specify the target window or frame where the result of the script will be displayed. It takes values like _blank, _self, _parent etc.

4	
enctype

You can use the enctype attribute to specify how the browser encodes the data before it sends it to the server. Possible values are −

application/x-www-form-urlencoded − This is the standard method most forms use in simple scenarios.

mutlipart/form-data − This is used when you want to upload binary data in the form of files like image, word file etc.

Note − You can refer to Perl & CGI for a detail on how form data upload works.

HTML Form Controls
There are different types of form controls that you can use to collect data using HTML form −

Text Input Controls
Checkboxes Controls
Radio Box Controls
Select Box Controls
File Select boxes
Hidden Controls
Clickable Buttons
Submit and Reset Button
Text Input Controls
There are three types of text input used on forms −

Single-line text input controls − This control is used for items that require only one line of user input, such as search boxes or names. They are created using HTML <input> tag.

Password input controls − This is also a single-line text input but it masks the character as soon as a user enters it. They are also created using HTMl <input> tag.

Multi-line text input controls − This is used when the user is required to give details that may be longer than a single sentence. Multi-line input controls are created using HTML <textarea> tag.

Single-line text input controls
This control is used for items that require only one line of user input, such as search boxes or names. They are created using HTML <input> tag.

Example
Here is a basic example of a single-line text input used to take first name and last name −

Live Demo
<!DOCTYPE html>
<html>

   <head>
      <title>Text Input Control</title>
   </head>
	
   <body>
      <form >
         First name: <input type = "text" name = "first_name" />
         <br>
         Last name: <input type = "text" name = "last_name" />
      </form>
   </body>
	
</html>
This will produce the following result −


Attributes
Following is the list of attributes for <input> tag for creating text field.

Sr.No	Attribute & Description
1	
type

Indicates the type of input control and for text input control it will be set to text.

2	
name

Used to give a name to the control which is sent to the server to be recognized and get the value.

3	
value

This can be used to provide an initial value inside the control.

4	
size

Allows to specify the width of the text-input control in terms of characters.

5	
maxlength

Allows to specify the maximum number of characters a user can enter into the text box.

Password input controls
This is also a single-line text input but it masks the character as soon as a user enters it. They are also created using HTML <input>tag but type attribute is set to password.

Organizing information
As stated, HTML is basically a way of organizing informational content, and as such provides a few helper tags to do that. Two of the primary tags are sets of types to create and define lists and tables.

Lists
The strength of using native list code within HTML is that the numbering and/or bullet points are automatically applied.

<ol>

Defines an *ordered* list. During viewing your browser will automatically generate a number for each entry in the list.

<ul>

Defines an *unordered* list. Typically lists of this type are drawn on screen with simple bullet points instead of nubmers.

<li>

The actual list entry. This tag should be used for each point in the list and resides within either "ol" or "ul".

Let's look at some code for lists on the left and their result on the right. Note how the main difference is just the use of "ol" and "ul".
Tables
Tables within HTML have been in a state of limbo for a while. They were initially concieved as a way to hold tabular data but it wasn't long before web designers started using them for stylistic purposes as well. For instance wrapping an object in a table was a quick and easy way to center an entire element.
Table related tags
css-tricks.com has an in-depth look at how tables work.

There are several layers to defining a table.

<table>

Defines the table start

<tr>

Table row

<th>

Table header for top and side cells (optional).

<td>

Actual table data, an individual cell.

Many older examples will reference styles like “width” or border” within the element itself. Each of these tags can be used as normal with CSS so those properties are best defined there. The only attribute that will remain acceptable for the immediate future is “align”. Though technically deprecated (older code whose use is discouraged in place of something newer and/or better) it still remains, and when used with tables is the easiest way to align an element to the screen center.

Note that you don’t really have a choice to define columns first, then rows, you will always define your information rows first.

