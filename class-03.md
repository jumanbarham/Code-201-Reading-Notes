# class3

HTML offers web authors three ways for specifying lists of information. All lists must contain one or more list elements. Lists may contain −

<ul> − An unordered list. This will list items using plain bullets.

<ol> − An ordered list. This will use different schemes of numbers to list your items.

<dl> − A definition list. This arranges your items in the same way as they are arranged in a dictionary.
*******

HTML Unordered Lists
An unordered list is a collection of related items that have no special order or sequence. This list is created by using HTML <ul> tag. Each item in the list is marked with a bullet.

Example
Live Demo
<!DOCTYPE html>
<html>

   <head>
      <title>HTML Unordered List</title>
   </head>
	
   <body>
      <ul>
         <li>Beetroot</li>
         <li>Ginger</li>
         <li>Potato</li>
         <li>Radish</li>
      </ul>
   </body>
   
</html>
The type Attribute
You can use type attribute for <ul> tag to specify the type of bullet you like. By default, it is a disc. Following are the possible options −

<ul type = "square">
<ul type = "disc">
<ul type = "circle">
Example
Following is an example where we used <ul type = "square">

Live Demo
<!DOCTYPE html>
<html>

   <head>
      <title>HTML Unordered List</title>
   </head>

   <body>
      <ul type = "square">
         <li>Beetroot</li>
         <li>Ginger</li>
         <li>Potato</li>
         <li>Radish</li>
      </ul>
   </body>

</html>

## In JavaScript,

 an array is a data structure that contains list of elements which store multiple values in a single variable. The strength of JavaScript arrays lies in the array methods. Array methods are functions built-in to JavaScript that we can apply to our arrays — Each method has a unique function that performs a change or calculation to our array and saves us from writing common functions from scratch.
JavaScript Array Methods
1. map( )
This method creates a new array with the results of calling a provided function on every element in this array.
Image for post
2. filter( )
This method creates a new array with only elements that passes the condition inside the provided function.
Image for post
3. sort( )
This method is used to arrange/sort array’s elements either in ascending or descending order.
Image for post
4. forEach( )
This method helps to loop over array by executing a provided callback function for each element in an array.
Image for post
5. concat( )
This method is used to merge two or more arrays and returns a new array, without changing the existing arrays.
Image for post
6. every( )
This method checks every element in the array that passes the condition, returning true or false as appropriate.
Image for post
7. some( )
This method checks if at least one element in the array that passes the condition, returning true or false as appropriate.
Image for post
8. includes( )
This method checks if an array includes the element that passes the condition, returning true or false as appropriate.
Image for post
9. join( )
This method returns a new string by concatenating all of the array’s elements separated by the specified separator.
Image for post
10. reduce( )
This method applies a function against an accumulator and each element in the array to reduce it to a single value.
Image for post
11. find( )
This method returns the value of the first element in an array that pass the test in a testing function.
Image for post
12. findIndex( )
This method returns the index of the first element in an array that pass the test in a testing function.
Image for post
13. indexOf( )
This method returns the index of the first occurrence of the specified element in the array, or -1 if it is not found.
Image for post
14. fill( )
This method fills the elements in an array with a static value and returns the modified array.
Image for post
15. slice( )
This method returns a new array with specified start to end elements.
Image for post
16. reverse( )
This method reverses an array in place. Element at last index will be first and element at 0 index will be last.
Image for post
17. push( )
This method adds one or more elements to the end of array and returns the new length of the array.
Image for post
18. pop( )
This method removes the last element from the end of array and returns that element.
Image for post
19. shift( )
This method removes the first element from an array and returns that element.
Image for post
20. unshift( )
This method adds one or more elements to the beginning of an array and returns the new length of the array.
Image for post
Conclusion
To make JavaScript array manipulation easier, we should use array methods to make our work easier and the code cleaner.

********** 
### The CSS box model
 describes the rectangular boxes that are generated for elements in the document tree and laid out according to the visual formatting model.

 **Box dimensions**
Each box has a content area (e.g., text, an image, etc.) and optional surrounding padding, border, and margin areas; the size of each area is specified by properties defined below. The following diagram shows how these areas relate and the terminology used to refer to pieces of margin, border, and padding:

Image illustrating the relationship between content, padding, borders, and margins.   [D]

The margin, border, and padding can be broken down into top, right, bottom, and left segments (e.g., in the diagram, "LM" for left margin, "RP" for right padding, "TB" for top border, etc.).

The perimeter of each of the four areas (content, padding, border, and margin) is called an "edge", so each box has four edges:

content edge or inner edge
The content edge surrounds the rectangle given by the width and height of the box, which often depend on the element's rendered content. The four content edges define the box's content box.
padding edge
The padding edge surrounds the box padding. If the padding has 0 width, the padding edge is the same as the content edge. The four padding edges define the box's padding box.
border edge
The border edge surrounds the box's border. If the border has 0 width, the border edge is the same as the padding edge. The four border edges define the box's border box.
margin edge or outer edge
The margin edge surrounds the box margin. If the margin has 0 width, the margin edge is the same as the border edge. The four margin edges define the box's margin box.
Each edge may be broken down into a top, right, bottom, and left edge.

The dimensions of the content area of a box — the content width and content height — depend on several factors: whether the element generating the box has the 'width' or 'height' property set, whether the box contains text or other boxes, whether the box is a table, etc. Box widths and heights are discussed in the chapter on visual formatting model details.

The background style of the content, padding, and border areas of a box is specified by the 'background' property of the generating element. Margin backgrounds are always transparent.

8.2 Example of margins, padding, and borders
This example illustrates how margins, padding, and borders interact. The example HTML document:

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN">
<HTML>
  <HEAD>
    <TITLE>Examples of margins, padding, and borders</TITLE>
    <STYLE type="text/css">
      UL { 
        background: yellow; 
        margin: 12px 12px 12px 12px;
        padding: 3px 3px 3px 3px;
                                     /* No borders set */
      }
      LI { 
        color: white;                /* text color is white */ 
        background: blue;            /* Content, padding will be blue */
        margin: 12px 12px 12px 12px;
        padding: 12px 0px 12px 12px; /* Note 0px padding right */
        list-style: none             /* no glyphs before a list item */
                                     /* No borders set */
      }
      LI.withborder {
        border-style: dashed;
        border-width: medium;        /* sets border width on all sides */
        border-color: lime;
      }
    </STYLE>
  </HEAD>
  <BODY>
    <UL>
      <LI>First element of list
      <LI class="withborder">Second element of list is
           a bit longer to illustrate wrapping.
    </UL>
  </BODY>
</HTML>
results in a document tree with (among other relationships) a UL element that has two LI children.

The first of the following diagrams illustrates what this example would produce. The second illustrates the relationship between the margins, padding, and borders of the UL elements and those of its children LI elements. 