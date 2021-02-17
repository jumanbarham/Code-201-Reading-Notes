# html links

The HTML External Resource Link element (<link>) specifies relationships between the current document and an external resource. This element is most commonly used to link to stylesheets, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.
**************

To link an external stylesheet, you'd include a <link> element inside your <head> like this:

<link href="main.css" rel="stylesheet">
This simple example provides the path to the stylesheet inside an href attribute, and a rel attribute with a value of stylesheet. The rel stands for "relationship", and is probably one of the key features of the <link> element — the value denotes how the item being linked to is related to the containing document. As you'll see from our Link types reference, there are many different kinds of relationship.
***************
There are a number of other common types you'll come across. For example, a link to the site's favicon:

<link rel="icon" href="favicon.ico">
There are a number of other icon rel values, mainly used to indicate special icon types for use on various mobile platforms, e.g.:

<link rel="apple-touch-icon-precomposed" sizes="114x114"
      href="apple-icon-114.png" type="image/png">
The sizes attribute indicates the icon size, while the type contains the MIME type of the resource being linked. These provide useful hints to allow the browser to choose the most appropriate icon available.

You can also provide a media type or query inside a media attribute; this resource will then only be loaded if the media condition is true. For example:

<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="screen and (max-width: 600px)">
Some interesting new performance and security features have been added to the <link> element too. Take this example:

<link rel="preload" href="myFont.woff2" as="font"
      type="font/woff2" crossorigin="anonymous">
A rel value of preload indicates that the browser should preload this resource (see Preloading content with rel="preload" for more details), with the as attribute indicating the specific class of content being fetched. The crossorigin attribute indicates whether the resource should be fetched with a CORS request.

Other usage notes:

A <link> element can occur either in the <head> or <body> element, depending on whether it has a link type that is body-ok. For example, the stylesheet link type is body-ok, and therefore <link rel="stylesheet"> is permitted in the body. However, this isn't a good practice to follow; it makes more sense to separate your <link> elements from your body content, putting them in the <head>.
When using <link> to establish a favicon for a site, and your site uses a Content Security Policy (CSP) to enhance its security, the policy applies to the favicon. If you encounter problems with the favicon not loading, verify that the Content-Security-Policy header's img-src directive is not preventing access to it.
The HTML and XHTML specifications define event handlers for the <link> element, but it is unclear how they would be used.
Under XHTML 1.0, empty elements such as <link> require a trailing slash: <link />.
WebTV supports the use of the value next for rel to preload the next page in a document series.
*******************
## html layout
Page layout is the part of graphic design that deals with the arrangement of visual elements on a page. Page layout is used to make the web pages look better. It establishes the overall appearance, relative importance, and relationships between the graphic elements to achieve a smooth flow of information and eye movement for maximum effectiveness or impact.

page layout

Page Layout Information:

Header: The part of a front end which is used at the top of the page. <header> tag is used to add header section in web pages.
Navigation bar: The navigation bar is same as menu list. It is used to display the content information using hyperlink.
Index / Sidebar: It holds additional information or advertisements and is not always necessary to be added into the page.
Content Section: The content section is the main part where content is displayed.
Footer: The footer section contains the contact information and other query related to web pages. The footer section always put on the bottom of the web pages. The <footer> tag is used to set the footer in web pages.
Example:

filter_none
edit
play_arrow

brightness_4
<!DOCTYPE html> 
<html> 
<head> 
    <title>Page Layout</title> 
    <style> 
        .head1 { 
            font-size:40px; 
            color:#009900; 
            font-weight:bold; 
        } 
        .head2 { 
            font-size:17px; 
            margin-left:10px; 
            margin-bottom:15px; 
        } 
        body { 
            margin: 0 auto; 
            background-position:center; 
            background-size: contain; 
        } 
      
        .menu {    
            position: sticky; 
            top: 0; 
            background-color: #009900; 
            padding:10px 0px 10px 0px; 
            color:white; 
            margin: 0 auto; 
            overflow: hidden; 
        } 
        .menu a { 
            float: left; 
            color: white; 
            text-align: center; 
            padding: 14px 16px; 
            text-decoration: none; 
            font-size: 20px; 
        } 
        .menu-log { 
            right: auto; 
            float: right; 
        } 
        footer { 
            width: 100%; 
            bottom: 0px; 
            background-color: #000; 
            color: #fff; 
            position: absolute; 
            padding-top:20px; 
            padding-bottom:50px; 
            text-align:center; 
            font-size:30px; 
            font-weight:bold; 
        } 
        .body_sec { 
            margin-left:20px; 
        } 
    </style> 
</head> 
  
<body> 
      
    <!-- Header Section -->
    <header> 
        <div class="head1">GeeksforGeeks</div> 
        <div class="head2">A computer science portal for geeks</div> 
    </header> 
      
    <!-- Menu Navigation Bar -->
    <div class="menu"> 
        <a href="#home">HOME</a> 
        <a href="#news">NEWS</a> 
        <a href="#notification">NOTIFICATIONS</a> 
        <div class="menu-log"> 
            <a href="#login">LOGIN</a> 
        </div> 
    </div> 
      
    <!-- Body section -->
    <div class = "body_sec"> 
        <section id="Content"> 
            <h3>Content section</h3> 
        </section> 
    </div> 
      
    <!-- Footer Section -->
    <footer>Footer Section</footer> 
</body> 
</html>                 

### Functions, Methods, and Objects
JavaScript is designed on a simple object-based paradigm. An object is a collection of properties, and a property is an association between a name (or key) and a value. A property's value can be a function, in which case the property is known as a method. In addition to objects that are predefined in the browser, you can define your own objects. This chapter describes how to use objects, properties, functions, and methods, and how to create your own objects.

Objects overview
Objects in JavaScript, just as in many other programming languages, can be compared to objects in real life. The concept of objects in JavaScript can be understood with real life, tangible objects.

In JavaScript, an object is a standalone entity, with properties and type. Compare it with a cup, for example. A cup is an object, with properties. A cup has a color, a design, weight, a material it is made of, etc. The same way, JavaScript objects can have properties, which define their characteristics.

Objects and properties
A JavaScript object has properties associated with it. A property of an object can be explained as a variable that is attached to the object. Object properties are basically the same as ordinary JavaScript variables, except for the attachment to objects. The properties of an object define the characteristics of the object. You access the properties of an object with a simple dot-notation:

objectName.propertyName
Like all JavaScript variables, both the object name (which could be a normal variable) and property name are case sensitive. You can define a property by assigning it a value. For example, let's create an object named myCar and give it properties named make, model, and year as follows:

var myCar = new Object();
myCar.make = 'Ford';
myCar.model = 'Mustang';
myCar.year = 1969;
The above example could also be written using an object initializer, which is a comma-delimited list of zero or more pairs of property names and associated values of an object, enclosed in curly braces ({}):

var myCar = {
    make: 'Ford',
    model: 'Mustang',
    year: 1969
};
Unassigned properties of an object are undefined (and not null).

myCar.color; // undefined
Properties of JavaScript objects can also be accessed or set using a bracket notation (for more details see property accessors). Objects are sometimes called associative arrays, since each property is associated with a string value that can be used to access it. So, for example, you could access the properties of the myCar object as follows:

myCar['make'] = 'Ford';
myCar['model'] = 'Mustang';
myCar['year'] = 1969;
An object property name can be any valid JavaScript string, or anything that can be converted to a string, including the empty string. However, any property name that is not a valid JavaScript identifier (for example, a property name that has a space or a hyphen, or that starts with a number) can only be accessed using the square bracket notation. This notation is also very useful when property names are to be dynamically determined (when the property name is not determined until runtime). Examples are as follows:

// four variables are created and assigned in a single go,
// separated by commas
var myObj = new Object(),
    str = 'myString',
    rand = Math.random(),
    obj = new Object();

myObj.type              = 'Dot syntax';
myObj['date created']   = 'String with space';
myObj[str]              = 'String value';
myObj[rand]             = 'Random Number';
myObj[obj]              = 'Object';
myObj['']               = 'Even an empty string';

console.log(myObj);
Please note that all keys in the square bracket notation are converted to string unless they're Symbols, since JavaScript object property names (keys) can only be strings or Symbols (at some point, private names will also be added as the class fields proposal progresses, but you won't use them with [] form). For example, in the above code, when the key obj is added to the myObj, JavaScript will call the obj.toString() method, and use this result string as the new key.

You can also access properties by using a string value that is stored in a variable:

var propertyName = 'make';
myCar[propertyName] = 'Ford';

propertyName = 'model';
myCar[propertyName] = 'Mustang';
You can use the bracket notation with for...in to iterate over all the enumerable properties of an object. To illustrate how this works, the following function displays the properties of the object when you pass the object and the object's name as arguments to the function:

function showProps(obj, objName) {
  var result = ``;
  for (var i in obj) {
    // obj.hasOwnProperty() is used to filter out properties from the object's prototype chain
    if (obj.hasOwnProperty(i)) {
      result += `${objName}.${i} = ${obj[i]}\n`;
    }
  }
  return result;
}
So, the function call showProps(myCar, "myCar") would return the following:

myCar.make = Ford
myCar.model = Mustang
myCar.year = 1969
Enumerate the properties of an object
Starting with ECMAScript 5, there are three native ways to list/traverse object properties:

for...in loops
This method traverses all enumerable properties of an object and its prototype chain.
Object.keys(o)
This method returns an array with all the own (not in the prototype chain) enumerable properties' names ("keys") of an object o.
Object.getOwnPropertyNames(o)
This method returns an array containing all own properties' names (enumerable or not) of an object o.
Before ECMAScript 5, there was no native way to list all properties of an object. However, this can be achieved with the following function:

function listAllProperties(o) {
	var objectToInspect;
	var result = [];

	for(objectToInspect = o; objectToInspect !== null;
           objectToInspect = Object.getPrototypeOf(objectToInspect)) {
        result = result.concat(
            Object.getOwnPropertyNames(objectToInspect)
        );
    }

	return result;
}
This can be useful to reveal "hidden" properties (properties in the prototype chain which are not accessible through the object, because another property has the same name earlier in the prototype chain). Listing accessible properties only can easily be done by removing duplicates in the array.

Creating new objects
JavaScript has a number of predefined objects. In addition, you can create your own objects. You can create an object using an object initializer. Alternatively, you can first create a constructor function and then instantiate an object invoking that function in conjunction with the new operator.

Using object initializers
In addition to creating objects using a constructor function, you can create objects using an object initializer. Using object initializers is sometimes referred to as creating objects with literal notation. "Object initializer" is consistent with the terminology used by C++.

The syntax for an object using an object initializer is:

var obj = { property_1:   value_1,   // property_# may be an identifier...
            2:            value_2,   // or a number...
            // ...,
            'property n': value_n }; // or a string
where obj is the name of the new object, each property_i is an identifier (either a name, a number, or a string literal), and each value_i is an expression whose value is assigned to the property_i. The obj and assignment is optional; if you do not need to refer to this object elsewhere, you do not need to assign it to a variable. (Note that you may need to wrap the object literal in parentheses if the object appears where a statement is expected, so as not to have the literal be confused with a block statement.)

Object initializers are expressions, and each object initializer results in a new object being created whenever the statement in which it appears is executed. Identical object initializers create distinct objects that will not compare to each other as equal. Objects are created as if a call to new Object() were made; that is, objects made from object literal expressions are instances of Object.

The following statement creates an object and assigns it to the variable x if and only if the expression cond is true:

if (cond) var x = {greeting: 'hi there'};
The following example creates myHonda with three properties. Note that the engine property is also an object with its own properties.

var myHonda = {color: 'red', wheels: 4, engine: {cylinders: 4, size: 2.2}};
You can also use object initializers to create arrays. See array literals.

Using a constructor function
Alternatively, you can create an object with these two steps:

Define the object type by writing a constructor function. There is a strong convention, with good reason, to use a capital initial letter.
Create an instance of the object with new.
To define an object type, create a function for the object type that specifies its name, properties, and methods. For example, suppose you want to create an object type for cars. You want this type of object to be called Car, and you want it to have properties for make, model, and year. To do this, you would write the following function:

function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
Notice the use of this to assign values to the object's properties based on the values passed to the function.
