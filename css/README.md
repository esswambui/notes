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
##### Grouping Selector
The grouping selector selects all the HTML elements with the same style definitions.
