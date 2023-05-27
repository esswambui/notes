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
Example: ul > li will match all <li> elements that are nested directly inside a <ul> element.
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

####Length
##### Absolute
Absolute length values are the simplest length values, as they are fixed to a physical measurement, such as inches, centimeters, or millimeters. The most popular absolute unit of measurement is known as the pixel and is represented by the px unit notation.
###### Pixels
The pixel is equal to 1/96th of an inch; thus there are 96 pixels in an inch. The exact measurement of a pixel, however, may vary slightly between high-density and low-density viewing devices.
Pixels have been around for quite some time and are commonly used with a handful of different properties. The code here is using pixels to set the font size of all paragraphs to 14 pixels.
##### Relative Lengths
In addition to absolute length values, there are also relative length values. Relative length values are a little more complicated, as they are not fixed units of measurement; they rely on the length of another measurement.
###### Percentages
Percentages, represented by the % unit notation, are one of the most popular relative values. Percentage lengths are defined in relation to the length of another object. For example, to set the width of an element to 50%, we have to know the width of its parent element, the element it is nested within, and then identify 50% of the parent element’s width.
  Relative Lengths
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
## Useful Resources
- Get color palette : [coolors.co](https://coolors.co/)
- CSS Gradient: [cssgradient.io](https://cssgradient.io/)
- Color Picker from Image: [image color picker](https://imagecolorpicker.com/en)
- Get complimentary color: [adobe colors](https://color.adobe.com/create/color-wheel)
