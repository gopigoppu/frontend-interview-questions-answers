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

```css
#div1{float:right;width:100px;height:100px; background-color:blue;}
#div2{float:left;width:100px;height:100px; background-color:green;}
#div3{float:left;width:100px;height:100px; background-color:purple;}
```
```html
<div id="container">
  <div id="div1">div1</div>
  <div id="div2">div2</div>
  <div id="div3">div3</div>
</div>
```

Solution 2 (using flexbox):
```css
.example {
    display: flex;
    flex-direction: row;
}

.example > .a {order: 3; } /* Will be displayed third  */
.example > .b {order: 1; } /* Will be displayed second */
.example > .c {order: 2; } /* Will be displayed first  */
```
```html
<div class="example">
    <div class="a">First</div>
    <div class="b">Second</div>
    <div class="c">Third</div>
</div>
```

If you want to achieve with bootstrap check for `.pull-left` and `.pull-right` for v3 or `.float-left` and `.float-right` for v4.


### 20. Place a div to corner top-right of the page. Write CSS to achieve this?

```css
.topheader {
     position: relative;
     height: 20px;
   	
}
.bio{

    position:absolute;
    top: 0;
    right: 0;
    border: 1px solid;
}
```
```html
<div class="topheader">
    <div class="bio">myname</div>
</div>
```

References : 
* [https://stackoverflow.com/questions/11492055/how-to-adjust-relative-div-height-with-respect-to-inner-absolute-height](https://stackoverflow.com/questions/11492055/how-to-adjust-relative-div-height-with-respect-to-inner-absolute-height)



### 21. What are all position properties available in css?

| Value |	Description |
| ----- | ------------- |
| static | HTML elements are positioned static by default.Static positioned elements are not affected by the top, bottom, left, and right properties. |
| relative | An element with position: relative; is positioned relative to its normal position. Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element. |
| fixed | An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element. A fixed element does not leave a gap in the page where it would normally have been located. |
| absolute | An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed). However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling. |
| sticky | An element with position: sticky; is positioned based on the user's scroll position. A sticky element toggles between relative and fixed, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed). |


References : 
* [https://www.w3schools.com/css/css_positioning.asp](https://www.w3schools.com/css/css_positioning.asp)



### 22. Explain css position `absolute` and `relative`?

* `position: absolute` :  An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed). However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.
Note: A "positioned" element is one whose position is anything except static.

* `position: relative` :  An element with position: relative; is positioned relative to its normal position.
Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element.

```css
div.relative {
    position: relative;
    width: 400px;
    height: 200px;
    border: 3px solid #73AD21;
} 

div.absolute {
    position: absolute;
    top: 80px;
    right: 0;
    width: 200px;
    height: 100px;
    border: 3px solid #73AD21;
}
```
```html
<div class="relative">This div element has position: relative;
  <div class="absolute">This div element has position: absolute;</div>
</div>
```

References : 
* [https://www.w3schools.com/css/css_positioning.asp](https://www.w3schools.com/css/css_positioning.asp)


### 23. What is media query in CSS? Explain different type of design layout for devices?

Media queries are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen), specific characteristics (such as the width of the browser viewport), or environment (such as ambient light conditions).

Media queries are used for the following:

* To conditionally apply styles with the CSS @media and @import at-rules.
* To target specific media for the <link>, <source>, and other HTML elements.
* To test and monitor media states using the Window.matchMedia() and MediaQueryList.addListener() JavaScript methods.

A media query is composed of an optional media type and any number of media feature expressions. Multiple queries can be combined in various ways by using logical operators. Media queries are case-insensitive.

@media rule to include a block of CSS properties only if a certain condition is true.

Media types : 
* all - Suitable for all devices.
* print - Intended for paged material and documents viewed on a screen in print preview mode. 
* screen - Intended primarily for screens.
* speech - Intended for speech synthesizers.

Logical operators : 
* and - used for combining multiple media features together into a single media query, requiring each chained feature to return true in order for the query to be true. It is also used for joining media features with media types.
* not - used to negate a media query, returning true if the query would otherwise return false. If present in a comma-separated list of queries, it will only negate the specific query to which it is applied. If you use the not operator, you must also specify a media type.
* only - used to apply a style only if an entire query matches, and is useful for preventing older browsers from applying selected styles. If you use the only operator, you must also specify a media type.
* , (comma) - used to combine multiple media queries into a single rule.  Each query in a comma-separated list is treated separately from the others. Thus, if any of the queries in a list is true, the entire media statement returns true. In other words, lists behave like a logical or operator.

```css
@media only screen and (max-width: 600px) { ... } 
@media (min-height: 680px), screen and (orientation: portrait) { ... }
@media not screen and (color), print and (color) { ... }
```

References : 
* [https://www.w3schools.com/css/css_rwd_mediaqueries.asp](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)
* [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)


### 24. What are all different mediatypes available for media query?

* all - Suitable for all devices.
* print - Intended for paged material and documents viewed on a screen in print preview mode. 
* screen - Intended primarily for screens.
* speech - Intended for speech synthesizers.


### 25. What is viewport in RWD(Responsive Web Design)?

The viewport is the user's visible area of a web page. The viewport varies with the device, and will be smaller on a mobile phone than on a computer screen.

Narrow screen devices (e.g. mobiles) render pages in a virtual window or viewport, which is usually wider than the screen, and then shrink the rendered result down so it can all be seen at once. Users can then pan and zoom to see different areas of the page. So, Pages to be optimized. 

Pages optimized for a variety of devices must include a meta viewport tag in the head of the document. A meta viewport tag gives the browser instructions on how to control the page's dimensions and scaling.

* Use the meta viewport tag to control the width and scaling of the browser's viewport.
* Include `width=device-width` to match the screen's width in device-independent pixels.
* Include `initial-scale=1` to establish a 1:1 relationship between CSS pixels and device-independent pixels.
* Ensure your page is accessible by not disabling user scaling.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

References : 
* [https://www.w3schools.com/css/css_rwd_viewport.asp](https://www.w3schools.com/css/css_rwd_viewport.asp)
* [https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)
* [https://developers.google.com/web/fundamentals/design-and-ux/responsive/](https://developers.google.com/web/fundamentals/design-and-ux/responsive/)


### 26. What is the difference between border-box and content-box?

* content-box	- Default box-sizing property. The width and height properties (and min/max properties) includes only the content. Border and padding are not included
* border-box	- The width and height properties (and min/max properties) includes content, padding and border.

![border-box vs content-box](https://i.stack.imgur.com/C7oir.png)


### 27. What is CSS selector specificity and how does it work?

Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied. Specificity is based on the matching rules which are composed of different sorts of CSS selectors.

**Specificity Hierarchy :**

Every selector has its place in the specificity hierarchy. There are four categories which define the specificity level of a selector:

* **Inline styles** - An inline style is attached directly to the element to be styled. Example: `<h1 style="color: #ffffff;">`.

* **IDs** - An ID is a unique identifier for the page elements, such as #navbar.

* **Classes, attributes and pseudo-classes** - This category includes .classes, [attributes] and pseudo-classes such as :hover, :focus etc.

* **Elements and pseudo-elements** - This category includes element names and pseudo-elements, such as h1, div, :before and :after.

```html
<div id="test">
  <span>Text</span>
</div>
```
```css
div#test span { color: green; }
div span { color: blue; }
span { color: red; }
```
No matter the order, text will be green because that rule is most specific. (Also, the rule for blue overwrites the rule for red, notwithstanding the order of the rules)

References : 
* [https://www.w3schools.com/css/css_specificity.asp](https://www.w3schools.com/css/css_specificity.asp)
* [https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
* [https://medium.com/@dte/understanding-css-selector-specificity-a02238a02a59](https://medium.com/@dte/understanding-css-selector-specificity-a02238a02a59)


### 28. What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?

CSS resets aim to remove all built-in browser styling. Standard elements like H1-6, p, strong, em, et cetera end up looking exactly alike, having no decoration at all. You're then supposed to add all decoration yourself.

Normalize CSS aims to make built-in browser styling consistent across browsers. Elements like H1-6 will appear bold, larger et cetera in a consistent way across browsers. You're then supposed to add only the difference in decoration your design needs.

References : 
* [https://stackoverflow.com/questions/6887336/what-is-the-difference-between-normalize-css-and-reset-css](https://stackoverflow.com/questions/6887336/what-is-the-difference-between-normalize-css-and-reset-css)
* [http://necolas.github.io/normalize.css/](http://necolas.github.io/normalize.css/)
* [https://meyerweb.com/eric/tools/css/reset/](https://meyerweb.com/eric/tools/css/reset/)


### 29. Describe floats and how they work?

The float property is used for positioning and layout on web pages. Floats can be used to create entire web layouts.

*  A floated element is "invisible" to its parent
* A left/right floated element will try to be as close to the top and left/right of its parent element as possible
* Previously defined elements will push a floated element down
* A previously declared floated element will be given a more preferable position
* A position closer to the top of the parent element is preferred to a position closer to the left/right of the parent element
* A floated element should not extend outside its parent element

The float property can have one of the following values:

* left - The element floats to the left of its container
* right- The element floats to the right of its container
* none - The element does not float (will be displayed just where it occurs in the text). This is default
* inherit - The element inherits the float value of its parent

In its simplest use, the float property can be used to wrap text around images.


The clear property specifies what elements can float beside the cleared element and on which side.

The clear property can have one of the following values:

* none - Allows floating elements on both sides. This is default
* left - No floating elements allowed on the left side
* right- No floating elements allowed on the right side
* both - No floating elements allowed on either the left or the right side
* inherit - The element inherits the clear value of its parent

The most common way to use the clear property is after you have used a float property on an element.

If an element is taller than the element containing it, and it is floated, it will overflow outside of its container. 
Then we can add `overflow: auto;` to the containing element to fix this problem.

References : 
* [https://css-tricks.com/all-about-floats/](https://css-tricks.com/all-about-floats/)
* [https://www.w3schools.com/css/css_float.asp](https://www.w3schools.com/css/css_float.asp)
* [https://bitsofco.de/how-floating-works/](https://bitsofco.de/how-floating-works/)


### 30. Describe z-index and how stacking context is formed?

CSS style rules allow you to position boxes on layers in addition to the normal rendering layer (layer 0). The Z position of each layer is expressed as an integer representing the stacking order for rendering. Greater numbers mean closer to the observer. Z position can be controlled with the CSS z-index property.

The z-index property in CSS controls the vertical stacking order of elements that overlap. As in, which one appears as if it is physically closer to you. z-index only effects elements that have a position value other than static (the default).

```css
div {
  z-index: 1; /* integer */
}
```

**stacking context :**

The stacking context is a three-dimensional conceptualization of HTML elements along an imaginary z-axis relative to the user, who is assumed to be facing the viewport or the webpage. HTML elements occupy this space in priority order based on element attributes.

![z index](https://i.stack.imgur.com/wmy0R.png) ![z index](https://mdn.mozillademos.org/files/790/understanding_zindex_04.png)

A stacking context is formed, anywhere in the document, by any element in the following scenarios:

* Root element of document (HTML).
* Element with a position value "absolute" or "relative" and z-index value other than "auto".
* Element with a position value "fixed" or "sticky" (sticky for all mobile browsers, but not older desktop).
* Element that is a child of a flex (flexbox) container, with z-index value other than "auto".
* Element with a opacity value less than 1 (See the specification for opacity).
* Element with a mix-blend-mode value other than "normal".
* Element with any of the following properties with value other than "none":
    * transform
    * filter
    * perspective
    * clip-path
    * mask / mask-image / mask-border
* Element with a isolation value "isolate".
* Element with a -webkit-overflow-scrolling value "touch".
* Element with a will-change value specifying any property that would create a stacking context on non-initial value (see this post).

Within a stacking context, child elements are stacked according to the same rules previously explained. Importantly, the z-index values of its child stacking contexts only have meaning in this parent. Stacking contexts are treated atomically as a single unit in the parent stacking context.

References :
* [https://philipwalton.com/articles/what-no-one-told-you-about-z-index/](https://philipwalton.com/articles/what-no-one-told-you-about-z-index/)
* [https://stackoverflow.com/questions/32513540/understanding-z-index-stacking-order](https://stackoverflow.com/questions/32513540/understanding-z-index-stacking-order)
* [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)


### 31. Describe BFC (Block Formatting Context) and how it works?

A block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with other elements.

According to W3C:

    Floats, absolutely positioned elements, inline-blocks, table-cells, table-captions, and elements with ‘overflow’ other than ‘visible’ (except when that value has been propagated to the viewport) establish new block formatting contexts.

A BFC is an HTML box that satisfies at least one of the following conditions:

* The value of float is not none.
* The value of position is neither static nor relative.
* The value of display is table-cell, table-caption, inline-block, flex, or inline-flex.
* The value of overflow is not visible.

References : 
* [https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
* [https://www.sitepoint.com/understanding-block-formatting-contexts-in-css/](https://www.sitepoint.com/understanding-block-formatting-contexts-in-css/)
* [https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)



### 32. What are the various clearing techniques and which is appropriate for what context?

The clear property specifies what elements can float beside the cleared element and on which side.

overflow - Specifies what happens if content overflows an element's box.

The clear property can have one of the following values:

* none - Allows floating elements on both sides. This is default
* left - No floating elements allowed on the left side
* right- No floating elements allowed on the right side
* both - No floating elements allowed on either the left or the right side
* inherit - The element inherits the clear value of its parent

Techniques for Clearing Floats

* **The Empty Div Method** is, quite literally, an empty div. `<div style="clear: both;"></div>`. Sometimes you'll see a `<br>` element or some other random element used, but div is the most common because it has no browser default styling, doesn't have any special function, and is unlikely to be generically styled with CSS. This method is scorned by semantic purists since its presence has no contextual meaning at all to the page and is there purely for presentation. Of course in the strictest sense they are right, but it gets the job done right and doesn't hurt anybody.
* **The Overflow Method** relies on setting the overflow CSS property on a parent element. If this property is set to `auto` or `hidden` on the parent element, the parent will expand to contain the floats, effectively clearing it for succeeding elements. This method can be beautifully semantic as it may not require an additional elements. However if you find yourself adding a new div just to apply this, it is equally as non-semantic as the empty div method and less adaptable. Also bear in mind that the overflow property isn't specifically for clearing floats. Be careful not to hide content or trigger unwanted scrollbars.
* **The Easy Clearing Method** uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like "clearfix" to it. Then apply this CSS:

```css
.clearfix::after {
    content: "";
    clear: both;
    display: table;
}
```

```css
.clearfix {
    overflow: auto;
}
```
References : 
* [https://www.w3schools.com/css/css_float.asp](https://www.w3schools.com/css/css_float.asp)
* [http://www.dave-woods.co.uk/float-and-clear-a-comparison-of-css-clearing-techniques/](http://www.dave-woods.co.uk/float-and-clear-a-comparison-of-css-clearing-techniques/)
* [https://css-tricks.com/all-about-floats/](https://css-tricks.com/all-about-floats/)

### 33. Explain CSS sprites, and how you would implement them on a page or site.

An image sprite is a collection of images put into a single image. Image sprites are used in numerous web apps where multiple images are used. Rather than include each image as a separate image file, it is much more memory- and bandwidth-friendly to send them as a single image, so the number of HTTP requests is reduced.

```css
.toolbtn {
  background: url(myfile.png);
  display: inline-block;
  height: 20px;
  width: 20px;
}
```
A background position can be added either as two x, y values after the url() in the background, or as background-position.
```css
#btn1 {
  background-position: -20px 0px;
}

#btn2 {
  background-position: -40px 0px;
}
```

Note : Use a sprite generator that packs multiple images into one and generate the appropriate CSS for it.

References :
* [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Implementing_image_sprites_in_CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Implementing_image_sprites_in_CSS)
* [https://www.w3schools.com/css/css_image_sprites.asp](https://www.w3schools.com/css/css_image_sprites.asp)



### 34. How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?

* Graceful degradation — The practice of building an application for modern browsers while ensuring it remains functional in older browsers.
* Progressive enhancement — The practice of building an application for a base level of user experience, but adding functional enhancements when a browser supports it.
* Use caniuse.com to check for feature support.
* Autoprefixer for automatic vendor prefix insertion.
* Feature detection using Modernizr.

References :
* [https://codeburst.io/clearing-your-front-end-job-interview-css-95bdd82871f2](https://codeburst.io/clearing-your-front-end-job-interview-css-95bdd82871f2)

### 35. What are the different ways to visually hide content (and make it available only for screen readers)?

These techniques are related to accessibility (a11y).

* visibility: hidden. However the element is still in the flow of the page, and still takes up space.
* width: 0; height: 0. Make the element not take up any space on the screen at all, resulting in not showing it.
* position; absolute; left: -99999px. Position it outside of the screen.
* text-indent: -9999px. This only works on text within the block elements.

References :
* [https://codeburst.io/clearing-your-front-end-job-interview-css-95bdd82871f2](https://codeburst.io/clearing-your-front-end-job-interview-css-95bdd82871f2)


36. What are the advantages/disadvantages of using CSS preprocessors?

Advantages:

* CSS is made more maintainable.
* Easy to write nested selectors.
* Variables for consistent theming. Can share theme files across different projects.
* Mixins to generate repeated CSS.
* Splitting your code into multiple files. CSS files can be split up too but doing so will require a HTTP request to download each CSS file.

Disadvantages :
* The developer must have enough time to learn new features present in this preprocessor before using it.
* Using preprocessors may cause of losing benefits of browser's built-in element inspector.
* Requires tools for preprocessing. Re-compilation time can be slow.

References :
* [https://lovenoodles.cn/qsCenter/front_end/css/2018/03/01/115](https://lovenoodles.cn/qsCenter/front_end/css/2018/03/01/115)
* [http://techaffinity.com/blog/advantages-of-css-preprocessors/](http://techaffinity.com/blog/advantages-of-css-preprocessors/)


### 37. How would you implement a web design comp that uses non-standard fonts?

* using `@font-face`
```css
@font-face {
    font-family: myFirstFont;
    src: url(sansation_light.woff);
}
```
* using font service link
```html
<link href='http://fonts.googleapis.com/css?family=Lato' rel='stylesheet' type='text/css'>
```

References : 
* [https://www.w3schools.com/cssref/css3_pr_font-face_rule.asp](https://www.w3schools.com/cssref/css3_pr_font-face_rule.asp)


### 38. Explain how a browser determines what elements match a CSS selector.

One of the important things to understand about how browsers read your CSS selectors, is that they read them from right to left. That means that in the selector `ul > li a[title=”home”]` the first thing thing interpreted is `a[title=”home”]`. This first part is also referred to as the “key selector” in that ultimately, it is the element being selected.
```css
#main-nav > li {   }  /* Slower than it might seem */
```
Even though that feels weirdly counter-intuitive… Since ID’s are so efficient we would think the browser could just find that ID quickly and then find the li children quickly. But in reality, the relatively slow li tag selector is run first.

If the browser can determine the element you are looking for using just one selector and you’ve used more, you have inefficient code on your hands.

So you have to be very careful on how you are choosing your selector. Give unique IDs to fetch the single element Or give class name properly to identify group of elements based on your requirement.

On the other hand, if you start by matching the leftmost part of the selector… what do you match it against? You have to start walking the DOM, looking for nodes that might match it. Just discovering that there’s nothing matching that leftmost part might take a while.So browsers match from the right; it gives an obvious starting point and lets you get rid of most of the candidate selectors very quickly.

References : 
* [https://programmerinnervoice.wordpress.com/2013/12/18/how-does-browser-read-css-selector/](https://programmerinnervoice.wordpress.com/2013/12/18/how-does-browser-read-css-selector/)
* [https://stackoverflow.com/a/5813672](https://stackoverflow.com/a/5813672)


### 39. Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?

 ‘mobile-first’ is an approach to responsive design, where you make a design for mobile screens, or smaller screens first and then add added features and content for larger screens.

 ‘Responsive’ website design takes into consideration the users’ environment and screen size while making the design. It includes mixing layouts and employing flexible grids and images. Responsive design also uses CSS media queries.

 Knowing exactly who makes up a company’s audience is critical. Once it is understood who a company’s customers are and what devices they use to access the site, it will be possibly to develop a design that will satisfy customers and enhance their user experience.

 References : 
 * [https://codeburst.io/mobile-first-adaptive-or-responsive-design-which-to-choose-for-the-website-so-customers-want-to-aafc86443222](https://codeburst.io/mobile-first-adaptive-or-responsive-design-which-to-choose-for-the-website-so-customers-want-to-aafc86443222)
 * [https://codeburst.io/mobile-first-adaptive-or-responsive-design-which-to-choose-for-the-website-so-customers-want-to-aafc86443222](https://codeburst.io/mobile-first-adaptive-or-responsive-design-which-to-choose-for-the-website-so-customers-want-to-aafc86443222)
 * [https://www.quora.com/What-is-the-difference-between-mobile-first-website-design-and-responsive-website-design-Are-they-mutually-exclusive](https://www.quora.com/What-is-the-difference-between-mobile-first-website-design-and-responsive-website-design-Are-they-mutually-exclusive)


 ### 40. What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

`Bootstrap, Foundation, Bulma and Semantic UI`


### 41. Have you ever worked with retina graphics? If so, when and what techniques did you use?

On retina devices the websites are not broken. They just look vague and pixels start appearing as low resolution images. So the only way to correct is to resize the images by following one of the techniques below:

* Using alternate high resolution pixels :

Suppose we have an image of 200px by 400px (CSS pixels) and we want to display it properly in a retina display, we can upload an alternate image of size 400px by 800px in our server and render them whenever the webpage is opened in a retina device.

```css
/* for low resolution display */

.image {

    background-image: url(/path/to/my/lowreslogo.png);

    background-size: 200px 300px;

    height: 300px;

    width: 200px;

}

/* for high resolution display */

@media only screen and (min--moz-device-pixel-ratio: 2),

only screen and (-o-min-device-pixel-ratio: 2/1),

only screen and (-webkit-min-device-pixel-ratio: 2),

only screen and (min-device-pixel-ratio: 2) {

.image {

    background: url(/path/to/my/highreslogo.png) no-repeat;

    background-size: 200px 400px;

/* rest of your styles... */

}

}
```

* Using @face-fonts instead of images icon :

Image fonts will automatically resize themselves on the high resolution devices just like normal fonts do. Using @face-fonts is an alternate solution to Bitmap icons.

* Using SVG images instead of Bitmap images :

Bitmap images are images that multiply their pixels in retina displays. But they come with a limitation of getting multiplied infinite number of times. This is where SVG images come into role. They also solve our problem of uploading alternate images of double resolution plus they solve the bandwidth problem too.

* Using JavaScript to replace all the images with double sized image :

We can use JavaScript to replace all images in a webpage but it will be a difficult task replacing each one of them by writing individual code.

```javascript
 if (window.devicePixelRatio > 1)
 ```

References :
* https://www.sitepoint.com/css-techniques-for-retina-displays/


### 42. Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?

Yes, translate do not cause the browser to trigger repaint and layout and instead only acts on the compositor. I tend to only ever use translate/transform nowadays, and only using absolute positioning for an elements initial position. I'll then translate it from that initial position for better performance.

When using translate instead of positioning, you don't have to worry about breaking page flow. You won't have to mess with margins and paddings regardless of elements initial positioning (static, relative).

Also browser support looks pretty good (except IE8), just remember that transitions are supposed to enhance user experience while content stays the same. Older browsers will still render all elements properly, but simply ignore fancy animations so no harm done.

References :
* [https://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/](https://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/)



### 43. How to align 3 divs (left/center/right) inside another div?
```css
#container{width:100%;}
#div1{float:left;width:100px;height:100px; background-color:blue;}
#div2{float:right;width:100px;height:100px; background-color:green;}
#div3{margin:0 auto;width:100px;height:100px; background-color:purple;}
```
```html
<div id="container">
  <div id="div1">div1</div>
  <div id="div2">div2</div>
  <div id="div3">div3</div>
</div>
```

