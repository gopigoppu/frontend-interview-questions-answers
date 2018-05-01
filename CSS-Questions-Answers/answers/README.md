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
| initial |	Sets this property to its default value. 	|
| inherit |	Inherits this property from its parent element.  |

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
    Flexbox
    Grid Layout
    REM Values
    Shadows


References: 
* [CSS Advanced](https://www.w3schools.com/css/css3_borders.asp)
* [https://tutorialzine.com/2013/10/12-awesome-css3-features-you-can-finally-use](https://tutorialzine.com/2013/10/12-awesome-css3-features-you-can-finally-use)
* [https://www.htmlgoodies.com/html5/css/whats-new-in-css3.html](https://www.htmlgoodies.com/html5/css/whats-new-in-css3.html)


### 7. Explain Cross browser CSS coding?

Internet Explorer, Mozilla and Google Chrome all use different rendering engines. Particularly, CSS and HTML are not displayed identically across all browsers. As a result, a website may appear slightly off, or sometimes very off, when viewed in different browsers. There is still no definitive, ideal solution to problems such as different screen sizes, restricted bandwidth (in cases of mobile browsing), performance on high-resolution (“retina”) displays, and so on. Websites need cross browser compatibility but maybe not to every single web browser out there.

Efficient crossbrowser CSS development starts with techniques and good practices listed few of them below.

* JavaScript solutions that can help us serve responsive websites to older browsers lacking CSS3 support: **Respond.js, Modernizr**, and **adaptive.960.js**.
    * respond.js - which enables the older browser versions to understand and execute CSS3 media queries
    * Modernizr  - it is a small JavaScript library that detects the availability of native implementations for next-generation web technologies, i.e. features that stem from the HTML5 and CSS3 specifications
* Use Internet Explorer First - sites should be developed in “modern” web-browsers, with standards first and then be tweaked for buggy versions of Internet Explorer.
* Use a CSS Reset or NORMALIZE - Every browser has different default CSS rules that they follow. This is why you use CSS reset stylesheet to make sure your browsers follow the same basic rules and behave consistently. You want to add one of these as the first stylesheet in order to reset unless you use a framework which will already have one.
* Conditional Comments – Conditional comments allow you to link style sheets for different browsers, which is especially helpful when it comes to design challenges that are common with Internet Explorer.
* CrossBrowserTesting - gives you access to do this in over 1,500 browsers, so you never have to wonder what users are seeing when they visit your page from a different machine
* Use Vendor Prefixes and Fallbacks
The following is a list of vendor prefixes for each of the popular browsers.

    * -webkit- (Chrome, Safari, newer versions of Opera)
    * -moz- (Firefox)
    * -o- (Old versions of Opera)
    * -ms- (Internet Explorer))
* Clear Floats
* Check CSS Display Types
* Validate Your CSS
* Use Cross-Browser Plugins
* Use Testing Tools

References : 
* [https://speckyboy.com/cross-browser-css-styling-tips/](https://speckyboy.com/cross-browser-css-styling-tips/)
* [https://www.smashingmagazine.com/2010/06/the-principles-of-cross-browser-css-coding/](https://www.smashingmagazine.com/2010/06/the-principles-of-cross-browser-css-coding/)
* [https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Introduction](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Introduction)
* [https://www.catswhocode.com/blog/15-techniques-and-tools-for-cross-browser-css-coding](https://www.catswhocode.com/blog/15-techniques-and-tools-for-cross-browser-css-coding)



### 8. Write css to display div with size of 200px and place it to center of the browser?

**Solution 1 :**
```html
<div class="centered">center</div>
```
```css
.centered {
  position: fixed;
  top: 50%;
  left: 50%;
  margin-top: -100px;
  margin-left: -100px;
  background-color: green;
  width: 200px;
  height: 200px;
}
```
or
```css
.centered {
    position: absolute;
    width: 200px;
    height: 200px;
    margin: 50% 50%;
    left: -100px;
    top: -100px;
    background-color: green;
}
```

**solution 2 :** (using flexbox)
```html
<div class="flex-container">
  <div></div>
</div>
```
```css
.flex-container {
  display: flex;
  justify-content: center; /* aligns the flex items at the center of the container */
  align-items: center; /*  align the flex items vertically. */
  height: 300px;
  background-color: DodgerBlue;
}

.flex-container>div {
  background-color: #f1f1f1;
  color: white;
  width: 100px;
  height: 100px;
}
```


### 9. What is mixin in SASS? How do you use it? Also, How do you pass variable into mixin?

A mixin lets you make groups of CSS declarations that you want to reuse throughout your site. You can even pass in values to make your mixin more flexible

```css
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { 
    @include border-radius(10px); 
}
```

References : 
* [https://sass-lang.com/guide](https://sass-lang.com/guide)
* [https://scotch.io/tutorials/how-to-use-sass-mixins](https://scotch.io/tutorials/how-to-use-sass-mixins)


### 10. What are all selectors available in CSS?

* Simple selectors
    * Type selector - Selects all elements that match the given node name. E.g. `div` 
    * Class selector -  Selects all elements that have the given class attribute. E.g. `.classname`
    * ID selector - Selects an element based on the value of its id attribute. There should be only one element with a given ID in a document. E.g. #idname
    * Universal selector - Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces. E.g. ` * { //code }`
    * Attribute selector - Selects elements based on the value of the given attribute. E.g. `[attr]`

* Combinators
    * Adjacent sibling combinator - The + combinator selects adjacent siblings. This means that the second element directly follows the first, and both share the same parent. E.g. `h2 + p`
    * General sibling combinator - The ~ combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent. E.g. `p ~ span`
    * Child combinator - The > combinator selects nodes that are direct children of the first element. E.g. `ul > li`
    * Descendant combinator - The `(space) ` combinator selects nodes that are descendants of the first element. E.g. div span

* Pseudo-classes - allow the selection of elements based on state information that is not contained in the document tree. E.g. `a:visited`
* Pseudo-elements - represent entities that are not included in HTML. E.g. `p::first-line`


References : 
* [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* [https://www.w3schools.com/cssref/css_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp)
* [https://www.w3schools.com/css/css_combinators.asp](https://www.w3schools.com/css/css_combinators.asp)
* [https://www.w3schools.com/css/css_attribute_selectors.asp](https://www.w3schools.com/css/css_attribute_selectors.asp)


### 11. What is universal selector and what does it do in CSS?

The CSS universal selector (*) matches elements of any type. Optionally, it may be restricted to a specific namespace or to all namespaces.

Syntax : 
```css
* {
  /* style properties */
}
```
E.g 
```css
.floating {
  float: left
}
/* automatically clear the next sibling after a floating element */
.floating + * {
  clear: left;
}
```

References : 
* [https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)

### 12. What is the difference between `visibility:hidden` and `display:none` in CSS?

* `display:none` means that the tag in question will not appear on the page at all (although you can still interact with it through the dom). There will be no space allocated for it between the other tags.

* `visibility:hidden` means that unlike `display:none`, the tag is not visible, but space is allocated for it on the page. The tag is rendered, it just isn't seen on the page.

Note : Take a look at `opacity: 0;`

References :
* [https://stackoverflow.com/a/133064/3421966](https://stackoverflow.com/a/133064/3421966)
* [https://stackoverflow.com/a/1511884/3421966](https://stackoverflow.com/a/1511884/3421966)



### 13. While element having `display:none` style properties, will it be available in DOM tree or not?

Yes, It will be available in DOM tree. `display:none` means that the tag in question will not appear on the page at all (although you can still interact with it through the dom). There will be no space allocated for it between the other tags.

### 14. What is the meaning of `"Normal Flow"` and `“Out of Flow”` in CSS?

* "Normal Flow" is the typical way the browser renders, with consideration of the elements around it and other elements considerations for it. 

* "Out of Flow" means the element is "ignored" or the behavior "changed" by elements around it. 

If the element has a float then it becomes "out of flow" because it does not follow either a normal inline standard of one element after another in a line or a normal block standard of elements stacking on each other down the page.

If we give `position:relative` to parent element and `position:absolute` in elements inside parent. then child element will only out of flow inside parent only not from whole page 

References : 
* [https://www.w3.org/TR/CSS2/visuren.html](https://www.w3.org/TR/CSS2/visuren.html)
* [https://stackoverflow.com/questions/3293340/what-is-the-meaning-of-the-terms-normal-flow-and-out-of-flow-in-terms-of-ht/3293451](https://stackoverflow.com/questions/3293340/what-is-the-meaning-of-the-terms-normal-flow-and-out-of-flow-in-terms-of-ht/3293451)



### 15. What is static binding and dynamic binding in CSS?

The css binding adds or removes one or more named CSS classes to the associated DOM element.  This question was faced during knockout.js So, adding examples from knockout officials. Simply answer is, If we mutate DOM CSS during execution time, it goes to dynamic binding.

**Static binding** -  is a binding in which the class association is made during compile time. This is also called as Early binding.

```html
<div data-bind="css: { profitWarning: currentProfit() < 0 }">
   Profit Information
</div>
```
This will apply the CSS class profitWarning whenever the currentProfit value dips below zero, and remove that class whenever it goes above zero.


**Dynamic binding**  - is a binding in which the class association is not made until the object is created at execution time. It is also called as Late binding.
```html
<div data-bind="css: profitStatus">
   Profit Information
</div>
```
```javascript
viewModel.profitStatus = ko.pureComputed(function() {
        return this.currentProfit() < 0 ? "profitWarning" : "profitPositive";
    }, viewModel);
```
This will apply the CSS class profitPositive when the currentProfit value is positive, otherwise it will apply the profitWarning CSS class.


References : 
* [http://knockoutjs.com/documentation/css-binding.html](http://knockoutjs.com/documentation/css-binding.html)


### 16. Difference between css `pseudo-elements` and `pseudo-classes`?

* A pseudo-class is used to define a special state of an element.

For example, it can be used to:
Style an element when a user mouses over it
Style visited and unvisited links differently
Style an element when it gets focus
```css
selector:pseudo-class {
    property:value;
}
```

E.g
```css
a:visited {
    color: #00FF00;
}

```

* A CSS pseudo-element is used to style specified parts of an element.

For example, it can be used to: Style the first letter, or line, of an element
Insert content before, or after, the content of an element

```css
selector::pseudo-element {
    property:value;
}
```

E.g
```css
p::first-line {
    color: #ff0000;
    font-variant: small-caps;
}

```

References :
* [https://www.w3schools.com/css/css_pseudo_classes.asp](https://www.w3schools.com/css/css_pseudo_classes.asp)
* [https://www.w3schools.com/css/css_pseudo_elements.asp](https://www.w3schools.com/css/css_pseudo_elements.asp)
* [http://www.growingwiththeweb.com/2012/08/pseudo-classes-vs-pseudo-elements.html](http://www.growingwiththeweb.com/2012/08/pseudo-classes-vs-pseudo-elements.html)


### 17. What `pseudo-class` indicates the link is visited and link is not-visited?

* The :link selector is used to select unvisited links.
* The :visited selector is used to select visited links.
```css
a:link { 
    background-color: yellow;
}
a:visited { 
    color: pink;
}
```

References : 
* [https://www.w3schools.com/cssref/sel_link.asp](https://www.w3schools.com/cssref/sel_link.asp)
* [https://www.w3schools.com/cssref/sel_visited.asp](https://www.w3schools.com/cssref/sel_visited.asp)


### 18. What is box-model in css?

The CSS box model is essentially a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content.

Explanation of the different parts:

* Content - The content of the box, where text and images appear
* Padding - Clears an area around the content. The padding is transparent
* Border - A border that goes around the padding and content
* Margin - Clears an area outside the border. The margin is transparent

**Note:** When you set the width and height properties of an element with CSS, you just set the width and height of the content area. To calculate the full size of an element, you must also add padding, borders and margins.

Total element width = width + left padding + right padding + left border + right border + left margin + right margin

Total element height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin

References : 
* [https://www.w3schools.com/css/css_boxmodel.asp](https://www.w3schools.com/css/css_boxmodel.asp)


### 19. You have 3 div's. You have to align first div in right side and other 2 div's in left side. Write CSS to achieve this?

