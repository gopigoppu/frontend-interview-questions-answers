# CSS Question Answers

 **Note : Pull requests for suggestions and corrections are welcome!**

 ### 1. What is the difference between display `inline` and `block` and `inline-block` in CSS?


![alt text](https://i.stack.imgur.com/mGTYI.png "Differences")


* Inline Elements

    An inline element does not start on a new line and only takes up as much width as necessary.

* Block-level Elements

    A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).

* Inline-block elements:

    * Compared to `display: inline`, the major difference is that `display: inline-block` allows to set a width and height on the element.

    * Also, with `display: inline-block`, the top and bottom margins/paddings are respected, but with `display: inline` they are not.

    * Compared to `display: block`, the major difference is that `display: inline-block` does not add a line-break after the element, so the element can sit next to other elements.

References:

* [https://stackoverflow.com/questions/21614938/html-element-which-defaults-to-displayinline-block](https://stackoverflow.com/questions/21614938/html-element-which-defaults-to-displayinline-block)
* [https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
* [https://www.w3schools.com/html/html_blocks.asp](https://www.w3schools.com/html/html_blocks.asp)
* [https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
* [https://stackoverflow.com/questions/9189810/css-display-inline-vs-inline-block](https://stackoverflow.com/questions/9189810/css-display-inline-vs-inline-block)



### 2. What is flexbox and explain about it?

The Flexible Box Layout Module, makes it easier to design flexible responsive layout structure without using float or positioning.

A Flexible Layout must have a parent element with the display property set to flex.

Direct child elements(s) of the flexible container automatically becomes flexible items.

```html
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
</div>
```
```css
.flex-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  /* flex-flow: row wrap; */
  justify-content: center;
  align-items: center;
  align-content: space-between;
  background-color: DodgerBlue;
}

.flex-container > div {
  background-color: #f1f1f1;
  margin: 10px;
  padding: 20px;
  font-size: 30px;
}
```
The flex container properties are:

    flex-direction - property defines in which direction the container wants to stack the flex items.
    flex-wrap - property specifies whether the flex items should wrap or not.
    flex-flow - property is a shorthand property for setting both the flex-direction and flex-wrap properties.
    justify-content - property is used to align the flex items
    align-items -  property is used to align the flex items vertically.
    align-content - property is used to align the flex lines.

References : 

* [https://www.w3schools.com/css/css3_flexbox.asp](https://www.w3schools.com/css/css3_flexbox.asp)
* [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### 3. What is "grid and explain about it?

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

A Grid Layout must have a parent element with the display property set to grid or inline-grid.

Direct child element(s) of the grid container automatically becomes grid items.

    grid - Set the display property to grid to make a block-level grid container.
    inline-grid - Set the display property to inline-grid to make an inline grid container.
    grid-template-columns - property defines the number of columns in your grid layout, and it can define the width of each column.
    grid-template-rows - property defines the height of each row.
    grid-area - property can also be used to assign names to grid items. The syntax is: 
        " grid-row-start / grid-column-start / grid-row-end / grid-column-end "
    Named grid items can be referred to by the grid-template-areas property of the grid container.
    
```css
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto auto auto;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}
.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
.item8 {
  grid-area: 1 / 2 / 5 / 6;
}
```

References : 
* [https://www.w3schools.com/css/css_grid.asp](https://www.w3schools.com/css/css_grid.asp)
* [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

### 4. What are all the different types of display methods available?

| Value	 | Description |
|------- | ---------- | 
| inline	| Displays an element as an inline element (like <span>). Any height and width properties will have no effect	|
| block	| Displays an element as a block element (like <p>). It starts on a new line, and takes up the whole width |	
| contents	| Makes the container disappear, making the child elements children of the element the next level up in the DOM	|
| flex	| Displays an element as a block-level flex container	|
| grid	| Displays an element as a block-level grid container	|
| inline-block |	Displays an element as an inline-level block container. The element itself is formatted as an inline element, but you can apply height and width values	|
| inline-flex |	Displays an element as an inline-level flex container	|
| inline-grid |	Displays an element as an inline-level grid container	|
| inline-table |	The element is displayed as an inline-level table	|
| list-item | 	Let the element behave like a `<li>` element	|
| run-in |	Displays an element as either block or inline, depending on context	|
| table |	Let the element behave like a `<table>` element	|
| table-caption |	Let the element behave like a `<caption>` element	|
| table-column-group |	Let the element behave like a `<colgroup`> element	|
| table-header-group |	Let the element behave like a `<thead>` element	|
| table-footer-group |	Let the element behave like a `<tfoot>` element	|
| table-row-group	| Let the element behave like a `<tbody>` element	|
| table-cell |	Let the element behave like a `<td>` element	|
| table-column |	Let the element behave like a `<col>` element	|
| table-row |	Let the element behave like a `<tr>` element	|
| none	| The element is completely removed	|
| initial |	Sets this property to its default value. Read about initial	|
| inherit |	Inherits this property from its parent element. Read about inherit |

References : 
* [https://www.w3schools.com/cssref/pr_class_display.asp](https://www.w3schools.com/cssref/pr_class_display.asp)


### 5. Explain CSS3 Animations, Transistions and Transforms?

It's an huge topic. Please refer following links for detailed explanation.

References : 
* [https://www.w3schools.com/css/css3_animations.asp](https://www.w3schools.com/css/css3_animations.asp)
* [https://www.w3schools.com/css/css3_transitions.asp](https://www.w3schools.com/css/css3_transitions.asp)
* [https://www.w3schools.com/css/css3_2dtransforms.asp](https://www.w3schools.com/css/css3_2dtransforms.asp)
* [https://www.w3schools.com/css/css3_3dtransforms.asp](https://www.w3schools.com/css/css3_3dtransforms.asp)
* [https://medium.com/@kswanie21/css3-animations-with-transitions-transforms-5a9c01e5efb5](https://medium.com/@kswanie21/css3-animations-with-transitions-transforms-5a9c01e5efb5)
* [http://webdesignerwall.com/tutorials/easy-css-animation-transition-transforms](http://webdesignerwall.com/tutorials/easy-css-animation-transition-transforms)


### 6. What are all new in CSS3?

Lot of new features were introduced in CSS3. I'll list out few commonly used. 

    CSS Animations and Transitions
    Calculating Values With calc()
    Advanced Selectors
    Generated Content and Counters
    Gradients
    Webfonts
    Box Sizing
    Border Images
    Media Queries
    Multiple Backgrounds
    CSS Columns
    CSS 3D Transforms


References: 
* [CSS Advanced](https://www.w3schools.com/css/css3_borders.asp)
* [https://tutorialzine.com/2013/10/12-awesome-css3-features-you-can-finally-use](https://tutorialzine.com/2013/10/12-awesome-css3-features-you-can-finally-use)
* [https://www.htmlgoodies.com/html5/css/whats-new-in-css3.html](https://www.htmlgoodies.com/html5/css/whats-new-in-css3.html)


### 7. Explain Cross browser CSS coding?



