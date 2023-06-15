# Learning CSS
## Getting to Know CSS
It allows us to add layout and design to our pages, and it allows us to share those styles from element to element and page to page. Before we can unlock all of its features, though, there are a few aspects of the language we must fully understand. First, it’s crucial to know exactly how styles are rendered. Specifically, we’ll need to know how different types of selectors work and how the order of those selectors can affect how our styles are rendered.
### The Cascade
Within CSS, all styles cascade from the top of a style sheet to the bottom, allowing different styles to be added or overwritten as the style sheet progresses.
For example in the code below:
```css
p {
  background: orange;
  background: green;
}
```
The background color will be green.

---

When there is more than one style specified for an HTML element, the styles will be implemented in the following order:
1. Inline style
1. Internal  style sheets
1. External style sheets (in the head section)
1. Browser default

**An inline style has the highest priority and will override external and internal styles and browser defaults.**

Most HTML elements will inherit many style properties from their parent elements by default.

### CSS Selectors
CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:

- Simple selectors ==> (select elements based on name, id, class)
- Combinator selectors ==> (select elements based on a specific relationship between them)
- Pseudo-class selectors ==> (select elements based on a certain state)
- Pseudo-elements selectors ==> (select and style a part of an element)
- Attribute selectors ==> (select elements based on an attribute or attribute value)

#### Simple Selectors
##### element Selector
The element selector selects HTML elements based on the element name.
```css
p {
  text-align: center;
  color: red;
}

```
##### id selector
The id selector uses the id attribute of an HTML element to select a specific element.
The id of an element is unique within a page, so the id selector is used to select one unique element!
To select an element with a specific id, write a hash (#) character, followed by the id of the element.
```css
#first-paragraph {
  text-align: center;
  color: red;
}

```
##### class Selector
The class selector selects HTML elements with a specific class attribute.
To select elements with a specific class, write a period (.) character, followed by the class name.
```css
.center {
  text-align: center;
}
```
You can also specify that only specific HTML elements should be affected by a class.
```css
p.center {
  text-align: center;
  color: red;
}
```
##### Universal Selector
The universal selector (*) selects all HTML elements on the page.
#### Grouping Selector
The grouping selector selects all the HTML elements with the same style definitions.
#### Combinator Selector
##### Descendant combinator
The " " (space) combinator selects nodes that are descendants of the first element.
Syntax: A B
Example: div span will match all <span> elements that are inside a <div> element.
##### Child combinator
The > combinator selects nodes that are direct children of the first element.
Syntax: A > B
Example: section > p will match all <p> elements that are nested directly inside a <section> element.
##### General sibling combinator
The ~ combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.
Syntax: A ~ B
Example: p ~ span will match all <span> elements that follow a <p>, immediately or not.

##### Adjacent sibling combinator
The + combinator matches the second element only if it immediately follows the first element.
Syntax: A + B
Example: h2 + p will match the first <p> element that immediately follows an h2 element.
[Learn more details in MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
### Calculating Specificity
Every selector in CSS has a specificity weight. A selector’s specificity weight, along with its placement in the cascade, identifies how its styles will be rendered.

- element selector ==> 1 point
- class selector ==> 10 points
- id selector ==> 100 points
- inline style ==> 1000 points
- !important ==> 10000 points
### Common CSS Properties
#### Color
  - Key words
  - Hexadecimal
  - RGB/RGBa
  - HSL/HSLa
 ##### Common CSS Colours
![image](https://github.com/esswambui/notes/assets/76427693/8a3e5f93-646d-4830-b09d-a2987681f753)
![image](https://github.com/esswambui/notes/assets/76427693/3e6f38e4-0e00-4500-ac4c-41154f9bb667)

#### Length
##### Absolute
Absolute length values are the simplest length values, as they are fixed to a physical measurement, such as inches, centimeters, or millimeters. The most popular absolute unit of measurement is known as the pixel and is represented by the px unit notation.
###### Pixels
The pixel is equal to 1/96th of an inch; thus there are 96 pixels in an inch. The exact measurement of a pixel, however, may vary slightly between high-density and low-density viewing devices.
Pixels have been around for quite some time and are commonly used with a handful of different properties. The code here is using pixels to set the font size of all paragraphs to 14 pixels.
##### Relative Lengths
In addition to absolute length values, there are also relative length values. Relative length values are a little more complicated, as they are not fixed units of measurement; they rely on the length of another measurement.
###### Percentages
Percentages, represented by the % unit notation, are one of the most popular relative values. Percentage lengths are defined in relation to the length of another object. For example, to set the width of an element to 50%, we have to know the width of its parent element, the element it is nested within, and then identify 50% of the parent element’s width.
Percentages are extremely helpful for setting the height and width of elements and building out a web page’s layout. We’re going to rely on them often to help us out in these areas.
###### Em
The em unit is also a very popular relative value. The em unit is represented by the em unit notation, and its length is calculated based on an element’s font size.
A single em unit is equivalent to an element’s font size. So, for example, if an element has a font size of 14 pixels and a width set to 5em, the width would equal 70 pixels (14 pixels multiplied by 5).
When a font size is not explicitly stated for an element, the em unit will be relative to the font size of the closest parent element with a stated font size.
###### rem
rem (short for “root-em”) units dictate an element’s font size relative to the size of the root element. By default, most browsers use a font size value of 16px. So, if the root element is 16px, an element with the value 1rem will also equal 16px. Therefore, rem units are useful for scaling CSS elements in relation to the size of the root element — even if you don’t know what the default font size will be.

---
	
## Box Model
### Display
Exactly how elements are displayed—as block-level elements, inline elements, or something else—is determined by the display property. Every element has a default display property value; however, as with all other property values, that value may be overwritten. There are quite a few values for the display property, but the most common are 
  - block
  - inline
  - inline-block
  - none.
We can change an element’s display property value by selecting that element within CSS and declaring a new display property value. A value of block will make that element a block-level element.
### What Is the Box Model?#what-is-the-box-model
According to the box model concept, every element on a page is a rectangular box and may have width, height, padding, borders, and margins.
### Working with the Box Model
Every element is a rectangular box, and there are several properties that determine the size of that box. The core of the box is defined by the width and height of an element, which may be determined by the display property, by the contents of the element, or by specified width and height properties. padding and then border expand the dimensions of the box outward from the element’s width and height. Lastly, any margin we have specified will follow the border.
Each part of the box model corresponds to a CSS property: width, height, padding, border, and margin.
### Width & Height
Every element has default width and height. That width and height may be 0 pixels, but browsers, by default, will render every element with size. Depending on how an element is displayed, the default width and height may be adequate. If an element is key to the layout of a page, it may require specified width and height property values. In this case, the property values for non-inline elements may be specified.
#### Width
The default width of an element depends on its display value. Block-level elements have a default width of 100%, consuming the entire horizontal space available. Inline and inline-block elements expand and contract horizontally to accommodate their content. Inline-level elements cannot have a fixed size, thus the width and height properties are only relevant to non-inline elements. 
#### Height
The default height of an element is determined by its content. An element will expand and contract vertically as necessary to accommodate its content
	
---
	
## Positioning with Floats
One way to position elements on a page is with the float property. The float property is pretty versatile and can be used in a number of different ways.

Essentially, the float property allows us to take an element, remove it from the normal flow of a page, and position it to the left or right of its parent element. All other elements on the page will then flow around the floated element. An <img> element floated to the side of a few paragraphs of text, for example, will allow the paragraphs to wrap around the image as necessary.

When the float property is used on multiple elements at the same time, it provides the ability to create a layout by floating elements directly next to or opposite each other, as seen in multiple-column layouts.

The float property accepts a few values; the two most popular values are left and right, which allow elements to be floated to the left or right of their parent element.
```css
img {
  float: left;
}
```
### Floats in Practice
Let’s create a common page layout with a header at the top, two columns in the center, and a footer at the bottom. Ideally this page would be marked up using the <header>, <section>, <aside>, and <footer> elements. The HTML may look like this:
```html
<header>...</header>
<section>...</section>
<aside>...</aside>
<footer>...</footer>
```
Here the <section> and <aside> elements, as block-level elements, will be stacked on top of one another by default. However, we want these elements to sit side by side. By floating the <section> to the left and the <aside> to the right, we can position them as two columns sitting opposite one another. Our CSS should look like this:
```css
section {
  float: left;
}
aside {
  float: right;
}
```
For reference, when an element is floated, it will float all the way to the edge of its parent element. If there isn’t a parent element, the floated element will then float all the way to the edge of the page.

When we float an element, we take it out of the normal flow of the HTML document. This causes the width of that element to default to the width of the content within it. Sometimes, such as when we’re creating columns for a reusable layout, this behavior is not desired. It can be corrected by adding a fixed width property value to each column. Additionally, to prevent floated elements from touching one another, causing the content of one to sit directly next to the content of the other, we can use the margin property to create space between elements.

Here, we are extending the previous code block, adding a margin and width to each column to better shape our desired outcome.
```css
section {
  float: left;
  margin: 0 1.5%;
  width: 63%;
}
aside {
  float: right;
  margin: 0 1.5%;
  width: 30%;
}
```
With two columns we can float one column to the left and another to the right, but with more columns we must change our approach. Say, for example, we’d like to have a row of three columns between our <header> and <footer> elements. If we drop our <aside> element and use three <section> elements, our HTML might look like this:
```html
<header>...</header>
<section>...</section>
<section>...</section>
<section>...</section>
<footer>...</footer>
```
To position these three <section> elements in a three-column row, instead of floating one column to the left and one column to the right, we’ll float all three <section> elements to the left. We’ll also need to adjust the width of the <section> elements to account for the additional columns and to get them to sit one next to the other.
```css
section {
  float: left;
  margin: 0 1.5%;
  width: 30%;
}
```
### Clearing & Containing Floats
The float property was originally designed to allow content to wrap around images. An image could be floated, and all of the content surrounding that image could then naturally flow around it. Although this works great for images, the float property was never actually intended to be used for layout and positioning purposes, and thus it comes with a few pitfalls.

One of those pitfalls is that occasionally the proper styles will not render on an element that it is sitting next to or is a parent element of a floated element. When an element is floated, it is taken out of the normal flow of the page, and, as a result, the styles of elements around that floated element can be negatively impacted.

Often margin and padding property values aren’t interpreted correctly, causing them to blend into the floated element; other properties can be affected, too.

Another pitfall is that sometimes unwanted content begins to wrap around a floated element. Removing an element from the flow of the document allows all the elements around the floated element to wrap and consume any available space around the floated element, which is often undesired.

With our previous two-column example, after we floated the <section> and <aside> elements, and before we set a width property value on either of them, the content within the <footer> element would have wrapped in between the two floated elements above it, filling in any available space. Consequently, the <footer> element would have sat in the gutter between the <section> and <aside> elements, consuming the available space.
	
To prevent content from wrapping around floated elements, we need to clear, or contain, those floats and return the page to its normal flow. We’ll proceed by looking at how to clear floats, and then we’ll take a look at how to contain floats.

Clearing Floats
Clearing floats is accomplished using the clear property, which accepts a few different values: the most commonly used values being *left, right, and both.*
The left value will clear left floats, while the right value will clear right floats. The both value, however, will clear both left and right floats and is often the most ideal value.
```css
footer {
  clear: both;
}
```

##### CODE FOR FLOATS CLEAR FIX
  ```css
  .clearfix:after {
     content: ".";
     display: block;
     clear: both;
     visibility: hidden;
     line-height: 0;
     height: 0;
}

.clear {
	clear: both;
}
  ```
	
---
	
### Uniquely Positioning Elements
Every now and then we’ll want to precisely position an element. For these situations we can use the position property in connection with box offset properties.

The position property identifies how an element is positioned on a page and whether or not it will appear within the normal flow of a document. This is used in conjunction with the box offset properties—top, right, bottom, and left—which identify exactly where an element will be positioned by moving elements in a number of different directions.

#### Position Static
By default every element has a position value of **static**, which means that it exists in the normal flow of a document and it doesn’t accept any box offset properties. The static value is most commonly overwritten with a relative or absolute value.
#### Position Relative
The **relative** value for the position property allows elements to appear within the normal flow a page, leaving space for an element as intended while not allowing other elements to flow around it; however, it also allows an element’s display position to be modified with the box offset properties. 
	
With relatively positioned elements, it’s important to know that the box offset properties identify where an element will be moved from given its original position. When we position the element using the box offset properties, the element overlaps the element below it rather than moving that element down as the margin or padding properties would.
	
#### Position Absolute
The **absolute** value for the position property is different from the relative value in that an element with a position value of absolute will not appear within the normal flow of a document, and the original space and position of the absolutely positioned element will not be preserved.

Additionally, absolutely positioned elements are moved in relation to their closest relatively positioned parent element. Should a relatively positioned parent element not exist, the absolutely positioned element will be positioned in relation to the <body> element. 

#### Position Fixed
An element with **position: fixed;** is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.
A fixed element does not leave a gap in the page where it would normally have been located.
	
#### Position Sticky
An element with **position: sticky;** is positioned based on the user's scroll position.
A sticky element toggles between relative and fixed, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).

---
	
## Flex Box
### The Basics
The Flexbox Layout (Flexible Box) module aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word “flex”).

The main idea behind the flex layout is to give the container the ability to alter its items’ width/height (and order) to best fill the available space (mostly to accommodate to all kind of display devices and screen sizes). A flex container expands items to fill available free space or shrinks them to prevent overflow.

Most importantly, the flexbox layout is direction-agnostic as opposed to the regular layouts (block which is vertically-based and inline which is horizontally-based). While those work well for pages, they lack flexibility to support large or complex applications (especially when it comes to orientation changing, resizing, stretching, shrinking, etc.).

*Note: Flexbox layout is most appropriate to the components of an application, and small-scale layouts, while the ***Grid*** layout is intended for larger scale layouts.*
	
### Terminology
Flex-box involves a lot of things including its whole set of *properties*. Some of them are meant to be set on the container **(parent element, known as “flex container”)** whereas the others are meant to be set on the **children (said “flex items”)**. If “regular” layout is based on both block and inline flow directions, the flex layout is based on “flex-flow directions”. 
Have a look at this figure from the specification, explaining the main idea behind the flex layout.
![image](https://github.com/esswambui/notes/assets/76427693/baa95264-d56e-4d76-ad79-9f38cdf67cdf)
Items will be laid out following either the main axis (from main-start to main-end) or the cross axis (from cross-start to cross-end).
- **main axis** – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the ``flex-direction property````
- **main-start | main-end** – The flex items are placed within the container starting from main-start and going to main-end.
- **main size** – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
- **cross axis** – The croos-axis perpendicular to the main axis. Its direction depends on the main axis direction.
- **cross-start | cross-end** – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
- **cross size** – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.

### Flex-box Properties
#### Properties for the Parent (flex container)
##### display
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.
#### flex-direction
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.
- row (default): left to right in ltr; right to left in rtl
- row-reverse: right to left in ltr; left to right in rtl
- column: same as row but top to bottom
- column-reverse: same as row-reverse but bottom to top
#### flex-wrap
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.
- nowrap (default): all flex items will be on one line
- wrap: flex items will wrap onto multiple lines, from top to bottom.
- wrap-reverse: flex items will wrap onto multiple lines from bottom to top.
#### flex-flow
This is a shorthand for the **flex-direction** and **flex-wrap** properties, which together define the flex container’s main and cross axes. The default value is ```row nowrap.```
#### justify-content
This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.
- flex-start (default): items are packed toward the start of the flex-direction.
- flex-end: items are packed toward the end of the flex-direction.
- center: items are centered along the line
- space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line
- space-around: items are evenly distributed in the line with equal space around them. Note that visually the spaces     aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against   the container edge, but two units of space between the next item because that next item has its own spacing that applies.
- space-evenly: items are distributed so that the spacing between any two items (and the space to the edges) is equal.
#### align-items
This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis.
- stretch (default): stretch to fill the container (still respect min-width/max-width)
- flex-start: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
- flex-end: items are placed at the end of the cross axis. The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
- center: items are centered in the cross-axis
baseline: items are aligned such as their baselines align
#### align-content
This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

## CSS Grid
### Introduction
CSS Grid Layout (aka “Grid” or “CSS Grid”), is a two-dimensional grid-based layout system.
To get started you have to define a container element as a grid with display: grid, set the column and row sizes with grid-template-columns and grid-template-rows, and then place its child elements into the grid with grid-column and grid-row. 
### Terminology
#### Grid Container
The element on which display: grid is applied. It’s the direct parent of all the grid items.
#### Grid Item
The children (i.e. direct descendants) of the grid container. 
#### Grid Line
The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. Here the yellow line is an example of a column grid line.
![image](https://github.com/esswambui/notes/assets/76427693/98720596-d430-4f71-a238-58ec32a12521)

#### Grid Cell
The space between two adjacent row and two adjacent column grid lines. It’s a single “unit” of the grid. Here’s the grid cell between row grid lines 1 and 2, and column grid lines 2 and 3.
![image](https://github.com/esswambui/notes/assets/76427693/c37cc7f6-506b-4c52-a067-2d2bcb0c14df)

#### Grid Track
The space between two adjacent grid lines. You can think of them as the columns or rows of the grid. Here’s the grid track between the second and third-row grid lines.
![image](https://github.com/esswambui/notes/assets/76427693/97cadbd7-bb26-4a4f-840b-167e01ec762f)

#### Grid Area
The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells. Here’s the grid area between row grid lines 1 and 3, and column grid lines 1 and 3.
![image](https://github.com/esswambui/notes/assets/76427693/4a4fca9b-a2e5-45ad-8348-750290dfd91c)

 
---
	
## Useful Resources
- Get color palette : [coolors.co](https://coolors.co/)
- CSS Gradient: [cssgradient.io](https://cssgradient.io/)
- Color Picker from Image: [image color picker](https://imagecolorpicker.com/en)
- Get complimentary color: [adobe colors](https://color.adobe.com/create/color-wheel)
- Get icons: [Font Awesome](https://fontawesome.com/icons) and [cdn link to add to HTML](https://cdnjs.com/libraries/font-awesome) *choose the first link*
- Game to learn flex-box: [Flexbox Froggy](https://flexboxfroggy.com/)
- Game to learn CSS Grid: [CSS Grid Garden](https://cssgridgarden.com/)
