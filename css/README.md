# Learning CSS
## Getting to Know CSS
It allows us to add layout and design to our pages, and it allows us to share those styles from element to element and page to page. 
Before we can unlock all of its features, though, there are a few aspects of the language we must fully understand.       
First, it’s crucial to know exactly how styles are rendered. Specifically, we’ll need to know how different types of selectors work 
and how the order of those selectors can affect how our styles are rendered.
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
