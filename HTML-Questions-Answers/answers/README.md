# HTML Question Answers.


### 1. Is HTML case sensitive?

HTML is case insenstivie. But it is good practice to keep HTML markup lowercase. 

XHTML, that is being XML is case sensitive. 

References :
* [http://www.w3.org/TR/html5/syntax.html](http://www.w3.org/TR/html5/syntax.html)

* [https://www.w3.org/TR/xhtml1/#h-4.2](https://www.w3.org/TR/xhtml1/#h-4.2)

### 2. What is doctype in HTML?

 DOCTYPE describes the HTML that will be used in your page. Browsers also use the DOCTYPE to determine how to render a page. Not including a DOCTYPE or including an incorrect DOCTYPE can trigger quirks mode. 

 ```html
 <!DOCTYPE html>
 ```
 Above declaration indicates that the page is HTML5 document type. 

 References : 

 * [https://www.w3schools.com/tags/tag_doctype.asp](https://www.w3schools.com/tags/tag_doctype.asp)
 * [https://stackoverflow.com/questions/414891/what-is-doctype](https://stackoverflow.com/questions/414891/what-is-doctype)

 ### 3. What does lang attribute do?

The HTML lang attribute is used to identify the language of text content on the web or a portion of a web page. This is meant to assist search engine spiders, page formatting and screen reader technology.

References : 
* [https://developer.paciellogroup.com/blog/2016/06/using-the-html-lang-attribute/](https://developer.paciellogroup.com/blog/2016/06/using-the-html-lang-attribute/)

* [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)

### 4. How do you serve page with content in multiple languages?

This means you need to serve page content available in multiple languages. `lang` atribute defines language of text content in web page. So,The content within the page should be displayed only in one consistent language

[To serve a page with content in multiple languages](http://www.pro-tekconsulting.com/blog/how-do-you-serve-a-page-with-content-in-multiple-languages/), there are four steps:

1. You must have translated/localized pages on the server for each language you intend to support.
2. Your server must recognize the browser’s language request.
3. You must carefully name the files for the localized pages, so the server has a systematic way of locating them.
4. You need a method for serving a generic page when you don’t have the requested language.

Also, `Content-Language` is from the server, and lets the client know what language(s) are present on the requested page. `Accept-Language` is from the client, and lets the server know the user's preferred language(s). There can be multiple languages, each with an optional weight or 'quality' value. 

The browser writes a value for the Accept-Language request header field that it sends to the web server. The server then dynamically generates the HTML page with content in that particular language and sends it to client. Client side framework will render the content and displays to user.

References : 
* [https://stackoverflow.com/a/6157546](https://stackoverflow.com/a/6157546)
* [https://stackoverflow.com/questions/12150369/define-multiple-languages-in-html](https://stackoverflow.com/questions/12150369/define-multiple-languages-in-html)
* [https://stackoverflow.com/a/7076990](https://stackoverflow.com/a/7076990)

### 5. What are all list of inline and block level elements?

![alt text](https://i.stack.imgur.com/mGTYI.png "Differences")


* Inline Elements

    An inline element does not start on a new line and only takes up as much width as necessary.

```html
<a> <abbr>  <acronym>   <b> <bdo>   <big>   <br>    <button>    <cite>  <code>  <dfn>   <em>    <i> <img>   <input> <kbd>   <label> <map>   <object>    <q> <samp>  <script>    <select>    <small> <span>  <strong>    <sub>   <sup>   <textarea>  <time>  <tt>    <var>
```

* Block-level Elements

    A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).
    

Block level elements in HTML:

```html
<address>   <article>    <aside> <blockquote>    <canvas>    <dd>    <div>   <dl>    <dt>    <fieldset>  <figcaption>    <figure>    <footer>    <form>  <h1>-<h6>   <header>    <hr>    <li>    <main>  <nav>   <noscript>  <ol>    <output>    <p> <pre>   <section>   <table> <tfoot> <ul>    <video>
```

* Inline-block elements:

    * Compared to display: inline, the major difference is that display: inline-block allows to set a width and height on the element.

    * Also, with display: inline-block, the top and bottom margins/paddings are respected, but with display: inline they are not.

    * Compared to display: block, the major difference is that display: inline-block does not add a line-break after the element, so the element can sit next to other elements.
```html
<button>    <select>    <meter>     <progress>  <marquee>   <textarea>  <input>
```

References:

* [https://stackoverflow.com/questions/21614938/html-element-which-defaults-to-displayinline-block](https://stackoverflow.com/questions/21614938/html-element-which-defaults-to-displayinline-block)
* [https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
* [https://www.w3schools.com/html/html_blocks.asp](https://www.w3schools.com/html/html_blocks.asp)
* [https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
* [https://stackoverflow.com/questions/9189810/css-display-inline-vs-inline-block](https://stackoverflow.com/questions/9189810/css-display-inline-vs-inline-block)


### 6. What is empty tag and why do we need it?

HTML elements with no content are called empty elements. Empty elements do not have an end tag. The representation of an empty element is either a start-tag immediately followed by an end-tag, or an empty-element tag
E.g. `<br>` or `<br />`


**Note** : A container tag has two ends (an opening and a closing) whereas an empty tag doesn't. The paragraph tag `<p></p>` is an example of a container tag. 


### 7. What is async and defer in HTML? What does it do and how it defers?

async and defer are attributes, which is added in script tag to define script execution during HTML parsing.

* `<script>` - 
 The HTML file will be parsed until the script file is hit, at that point parsing will stop and a request will be made to fetch the file (if it’s external). The script will then be executed before parsing is resumed.

* `<script async>` - 
async downloads the file during HTML parsing and will pause the HTML parser to execute it when it has finished downloading. async scripts execute at the first opportunity after they finish downloading and before the window’s load event.

* `<script defer>` - 
defer downloads the file during HTML parsing and will only execute it after the parser has completed. defer scripts are also guaranteed to execute in the order that they appear in the document. Its execution starts after parsing is completely finished, but before the DOMContentLoaded event.

**Note :** While doing speculative parsing, the browser does not execute inline JavaScript blocks. This means that it won’t discover any script-injected resources, and those will likely be last in line in the fetching queue. Also, If there are external style sheets placed before scripts in the document, the construction of DOM and CSSOM objects can interfere with each other. When the parser gets to a script tag, DOM construction cannot proceed until the JavaScript finishes executing, and the JavaScript cannot be executed until the CSS is downloaded, parsed, and the CSSOM is available. 

For important resources you can now use <link rel="preload"> to communicate to the browser that you want to load them as soon as possible.
```html
<link rel="preload" href="very_important.js" as="script">
```

References : 

* [http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)
* [https://stackoverflow.com/questions/10808109/script-tag-async-defer](https://stackoverflow.com/questions/10808109/script-tag-async-defer)
* [https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/](https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/)


### 8. How to refresh a page in HTML without using javascript?

We can use meta refresh tag. The http-equiv attribute provides an HTTP header for the information/value of the content attribute. `refresh` defines a time interval for the document to refresh itself.


Following refreshes page every 30 seconds.

```html
<head>
<meta http-equiv="refresh" content="30" />
</head>
```

**Note:** The value "refresh" should be used carefully, as it takes the control of a page away from the user. Using "refresh" will cause a failure in W3C's Web Content Accessibility Guidelines.


### 9. What is URL Encoding?

URL encoding converts characters into a format that can be transmitted over the Internet.

E.g.
```
Hello Günter ==> Hello%20G%C3%BCnter
```

Refrences : 

* [https://www.w3schools.com/tags/ref_urlencode.asp](https://www.w3schools.com/tags/ref_urlencode.asp)


### 10. What will happen in below code? Whether page will navigate first or function call triggers first?

 ```html
  <a href="www.google.com" onclick="myFunction()">
  ```

  The default behavior of the `<a>` tag's `onclick` and `href` properties is to execute the onclick, then follow the href as long as the onclick doesn't return false, canceling the event (or the event hasn't been prevented ( event.preventDefault() ) 

References :

* [https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable](https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable)
* [https://quirksmode.org/js/events_order.html](https://quirksmode.org/js/events_order.html)

### 11. What is meta tag? Why do we need it?

Metadata is data (information) about data. The `<meta>` tag provides metadata about the HTML document. Metadata will not be displayed on the page, but will be machine parsable.

Meta elements are typically used to specify page description, keywords, author of the document, last modified, and other metadata.The metadata can be used by browsers (how to display content or reload page), search engines (keywords), or other web services.HTML5 introduced a method to let web designers take control over the viewport (the user's visible area of a web page), through the `<meta>` tag

```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Free Web tutorials">
  <meta name="keywords" content="HTML,CSS,XML,JavaScript">
  <meta name="author" content="John Doe">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

References : 

* [https://www.w3schools.com/tags/tag_meta.asp](https://www.w3schools.com/tags/tag_meta.asp)

### 12. Explain audio and video tags. How to embed files with size attributes? 

* `<audio>` -  element specifies a standard way to embed audio in a web page.

    ```html
    <audio controls>
        <source src="horse.ogg" type="audio/ogg">
        <source src="horse.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    ```

    The controls attribute adds audio controls, like play, pause, and volume. `<source>` element allows you to specify alternative audio files which the browser may choose from.

* `<video>` - element specifies a standard way to embed a video in a web page

    ```html
        <video width="320" height="240" controls>
            <source src="movie.mp4" type="video/mp4">
            <source src="movie.ogg" type="video/ogg">
            Your browser does not support the video tag.
        </video>
    ```

References: 

* [https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
* [https://www.w3schools.com/html/html5_video.asp](https://www.w3schools.com/html/html5_video.asp)
* [https://www.w3schools.com/html/html5_audio.asp](https://www.w3schools.com/html/html5_audio.asp)


### 13. Write basic structure of page HTML Layout elements?


![alt text](https://www.w3schools.com/html/img_sem_elements.gif "HTML Layout ") 

    <header> - Defines a header for a document or a section
    <nav> - Defines a container for navigation links
    <section> - Defines a section in a document
    <article> - Defines an independent self-contained article
    <aside> - Defines content aside from the content (like a sidebar)
    <footer> - Defines a footer for a document or a section
    <details> - Defines additional details
    <summary> - Defines a heading for the <details> element

References : 

* [https://www.w3schools.com/html/html_layout.asp](https://www.w3schools.com/html/html_layout.asp)

### 14. What is viewport meta tag? Explain how it works?

A `<meta> viewport` element gives the browser instructions on how to control the page's dimensions and scaling.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* The `width=device-width` part sets the width of the page to follow the `screen-width` of the device (which will vary depending on the device).

* The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser

References : 

* [https://www.w3schools.com/css/css_rwd_viewport.asp](https://www.w3schools.com/css/css_rwd_viewport.asp)
* [https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)


### 15. What are all available HTML Form elements?  

    <form>	        Defines an HTML form for user input
    <input> 	Defines an input control
    <textarea>	Defines a multiline input control (text area)
    <label>	        Defines a label for an <input> element
    <fieldset>	Groups related elements in a form
    <legend>	Defines a caption for a <fieldset> element
    <select>	Defines a drop-down list
    <optgroup>	Defines a group of related options in a drop-down list
    <option>	Defines an option in a drop-down list
    <button>	Defines a clickable button
    <datalist>	Specifies a list of pre-defined options for input controls
    <output>	Defines the result of a calculation
    <object>        element represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.

References :

* [https://www.w3schools.com/html/html_form_elements.asp](https://www.w3schools.com/html/html_form_elements.asp)
* [https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)


### 16. What are all available HTML Input types?

    button:         A push button with no default behavior.
    checkbox:       A check box allowing single values to be selected/deselected.
    color:          HTML5 A control for specifying a color. A color picker's UI has no required features other than accepting simple colors as text (more info).
    date:           HTML5 A control for entering a date (year, month, and day, with no time).
    datetime-local: HTML5 A control for entering a date and time, with no time zone.
    email:          HTML5 A field for editing an e-mail address.
    file:           A control that lets the user select a file. Use the accept attribute to define the types of files that the control can select.
    hidden:         A control that is not displayed but whose value is submitted to the server.
    image:          A graphical submit button. You must use the src attribute to define the source of the image and the alt attribute to define alternative text. You can use the height and width attributes to define the size of the image in pixels.
    month:          HTML5 A control for entering a month and year, with no time zone.
    number:         HTML5 A control for entering a number.
    password:       A single-line text field whose value is obscured. Use the maxlength and minlength attributes to specify the maximum length of the value that can be entered.
    radio:          A radio button, allowing a single value to be selected out of multiple choices.
    range:          HTML5 A control for entering a number whose exact value is not important.
    reset:          A button that resets the contents of the form to default values.
    search:         HTML5 A single-line text field for entering search strings. Line-breaks are automatically removed from the input value.
    submit:         A button that submits the form.
    tel:            HTML5 A control for entering a telephone number.
    text:           A single-line text field. Line-breaks are automatically removed from the input value.
    time:           HTML5 A control for entering a time value with no time zone.
    url:            HTML5 A field for entering a URL.
    week:           HTML5 A control for entering a date consisting of a week-year number and a week number with no time zone.

References : 

* [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
* [https://www.w3schools.com/html/html_form_input_types.asp](https://www.w3schools.com/html/html_form_input_types.asp)


### 17. What are all available HTML Input attributes?

HTML5 added the following attributes for `<input>`:

    type
    accept
    capture
    checked
    disabled
    autocomplete
    autofocus
    form
    formaction
    formenctype
    formmethod
    formnovalidate
    formtarget
    height and width
    list
    min and max
    minlength and maxlength
    multiple
    pattern (regexp)
    placeholder
    readonly
    size
    src
    required
    step

References :

* [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Attributes)
* [https://www.w3schools.com/html/html_form_attributes.asp](https://www.w3schools.com/html/html_form_attributes.asp)

### 18. What are all new elements in HTML5?

There are plenty of new elements are introduced in HTML5. Please refer this link for detailed explanation.

References :

* [https://www.w3schools.com/html/html5_new_elements.asp](https://www.w3schools.com/html/html5_new_elements.asp)

### 19. What are semantic elements and Why we need it? What are all new semantic elements in HTML5?

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.

Examples of semantic elements: `<form>, <table>, <article>` - Clearly defines its content.

New Semantic Elements in HTML5 : 

    <article>
    <aside>
    <details>
    <figcaption>
    <figure>
    <footer>
    <header>
    <main>
    <mark>
    <nav>
    <section>
    <summary>
    <time>

References : 

* [https://www.w3schools.com/html/html5_semantic_elements.asp](https://www.w3schools.com/html/html5_semantic_elements.asp)
* [https://stackoverflow.com/questions/17272019/why-to-use-html5-semantic-tag-instead-of-div](https://stackoverflow.com/questions/17272019/why-to-use-html5-semantic-tag-instead-of-div)

### 20. What is contenteditable attribute? What does it do?

contenteditable - global attribute is an enumerated attribute indicating if the element should be editable by the user. If so, the browser modifies its widget to allow editing. The attribute must take one of the following values:

`true` or the empty string, which indicates that the element must be editable;
`false`, which indicates that the element must not be editable.

```html
<p contenteditable="true">This is an editable paragraph.</p>
```

References : 

* [https://www.w3schools.com/tags/att_global_contenteditable.asp](https://www.w3schools.com/tags/att_global_contenteditable.asp)
* [https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable)

### 21. What is canvas and svg ? How it differs?

* The HTML `<svg>` element is a container for SVG graphics. SVG has several methods for drawing paths, boxes, circles, text, and graphic images.

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
```
* `<canvas>` element is used to draw graphics, on the fly, via JavaScript. The `<canvas>` element is only a container for graphics. You must use JavaScript to actually draw the graphics.

```html
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #d3d3d3;">
Your browser does not support the HTML5 canvas tag.</canvas>

<script>
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
// Create gradient
var grd = ctx.createLinearGradient(0,0,200,0);
grd.addColorStop(0,"red");
grd.addColorStop(1,"white");
// Fill with gradient
ctx.fillStyle = grd;
ctx.fillRect(10,10,150,80);
</script>
```


| SVG | Canvas |
| ---- | ----- |
|Here’s it’s like draw and remember. In other words any shape drawn by using SVG can be remembered and manipulated and browser can render it again. | Canvas is like draw and forget. Once something is drawn you cannot access that pixel and manipulate it.|
|SVG is good for creating graphics like CAD software’s where once something is drawn the user wants to manipulate it. | Canvas is good for draw and forget scenarios like animation and games. |
| This is slow as it needs to remember the co-ordinates for later manipulations. | This is faster as there is no intention of remembering things later. |
| We can have event handler associated with the drawing object. | Here we cannot associate event handlers with drawing objects as we do not have reference of them. |
| Resolution independent. | Resolution dependent. |


References : 

* [https://www.w3schools.com/html/html5_svg.asp](https://www.w3schools.com/html/html5_svg.asp)
* [https://www.w3schools.com/html/html5_canvas.asp](https://www.w3schools.com/html/html5_canvas.asp)
* [http://www.xpode.com/ShowArticle.aspx?ArticleId=690](http://www.xpode.com/ShowArticle.aspx?ArticleId=690)

### 22. What is HTML Plug-ins? What does option and embed elements do?

Helper applications (plug-ins) are computer programs that extend the standard functionality of a web browser. Plug-ins can be used for many purposes: display maps, scan for viruses, verify your bank id, etc.

Plug-ins can be added to web pages with the `<object>` tag or the `<embed>` tag. 

The `<object>` element defines an embedded object within an HTML document. It is used to embed plug-ins (like Java applets, PDF readers, Flash Players) in web pages.

```html
<object width="400" height="50" data="bookmark.swf"></object>
```

The `<embed>` element also defines an embedded object within an HTML document. web browsers have supported the `<embed>` element for a long time. However, it has not been a part of the HTML specification before HTML5.

```html
<embed width="400" height="50" src="bookmark.swf">
```

References :

* [https://www.w3schools.com/html/html_object.asp](https://www.w3schools.com/html/html_object.asp)


### 23. What are all available HTML APIs?

Application Programming Interfaces (APIs) are constructs made available in programming languages to allow developers to create complex functionality more easily.

Client-side JavaScript, in particular, has many APIs available to it — these are not part of the JavaScript language itself, rather they are built on top of the core JavaScript language, providing you with extra superpowers to use in your JavaScript code. They generally fall into two categories:

1. Browser APIs are built into your web browser and are able to expose data from the browser and surrounding computer environment and do useful complex things with it. For example, the Geolocation API provides some simple JavaScript constructs for retrieving location data so you can say, plot your location on a Google Map.

2. Third party APIs are not built into the browser by default, and you generally have to grab their code and information from somewhere on the Web. For example, the Twitter API allows you to do things like displaying your latest tweets on your website.

Common browser APIs : 
* DOM (Document Object Model) API,
* XMLHttpRequest,
* Fetch API,
* Canvas and WebGL,
* Audio and Video APIs,
* Notifications API,
* Vibration API,
* Web Storage API
* IndexedDB API 

Common third-party APIs
* Twitter API,
* Google Maps API ,
* Facebook suite of APIs,
* YouTube API,
* Twilio API

References :

* [https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)
* [https://developer.mozilla.org/en-US/docs/Web/API](https://developer.mozilla.org/en-US/docs/Web/API)


### 24. Is summary tag is inline or block level element?

The HTML Disclosure Summary element (`<summary>`) element specifies a summary, caption, or legend for a `<details>` element's disclosure box. Clicking the `<summary>` element toggles the state of the parent `<details>` element open and closed.

default style for `<summary>` elements includes `display: list-item`. This makes it possible to change or remove the icon displayed as the disclosure widget next to the label from the default, which is typically a triangle.

You can also change the style to `display: block` to remove the disclosure triangle.

References :

* [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)

### 25. Explain drag & drop with available attributes?

HTML drag and drop uses the DOM event model and drag events inherited from mouse events. A typical drag operation begins when a user selects a draggable element with a mouse, moves the mouse to a droppable element and then releases the mouse. During the operations, several event types are fired and some event types might be fired many times (for example the drag and dragover event types).

All of the drag event types have an associated global event handler. Each drag event type and drag global attribute has a reference document that describes the event.

```html
<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)">
  <img src="img_w3slogo.gif" draggable="true" ondragstart="drag(event)" id="drag1" width="88" height="31">
</div>

<div id="div2" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

```
```javascript

function allowDrop(ev) {
    ev.preventDefault();
}

function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}

```

References : 

* [https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)
* [https://www.w3schools.com/html/html5_draganddrop.asp](https://www.w3schools.com/html/html5_draganddrop.asp)


### 26. Explain HTML5 webstorage?

The Web Storage API provides mechanisms by which browsers can store key/value pairs, in a much more intuitive fashion than using cookies

The two mechanisms within Web Storage are as follows:

* `sessionStorage` maintains a separate storage area for each given origin that's available for the duration of the page session (as long as the browser is open, including page reloads and restores)
    ```javascript
    window.sessionStorage - stores data for one session (data is lost when the browser tab is closed)
    ```

* `localStorage` does the same thing, but persists even when the browser is closed and reopened.
    ```javascript
    window.localStorage - stores data with no expiration date
    ```
References :
* [https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
* [https://www.w3schools.com/html/html5_webstorage.asp](https://www.w3schools.com/html/html5_webstorage.asp)


### 27. Difference between jwt and cookies? How it will be handled using webstorage?

Cookies and local storage serve different purposes. Cookies are primarily for reading server-side, local storage can only be read by the client-side.

The biggest difference between bearer tokens and cookies is that the browser will automatically send cookies, where bearer tokens need to be added explicitly to the HTTP request.

![jwt  vs cookie](https://image.slidesharecdn.com/authentication-cookiesvsjwtandwhyyouredoingitwrong-140703141348-phpapp01/95/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong-15-638.jpg?cb=1404397117 "jwt vs cookie ") 
![jwt  vs cookie](https://image.slidesharecdn.com/authentication-cookiesvsjwtandwhyyouredoingitwrong-140703141348-phpapp01/95/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong-17-638.jpg?cb=1404397117 "jwt vs cookie ") 
![jwt  vs cookie](https://image.slidesharecdn.com/authentication-cookiesvsjwtandwhyyouredoingitwrong-140703141348-phpapp01/95/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong-19-638.jpg?cb=1404397117 "jwt vs cookie ") 
![jwt  vs cookie](https://image.slidesharecdn.com/authentication-cookiesvsjwtandwhyyouredoingitwrong-140703141348-phpapp01/95/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong-21-638.jpg?cb=1404397117 "jwt vs cookie ") 
![jwt  vs cookie](https://image.slidesharecdn.com/authentication-cookiesvsjwtandwhyyouredoingitwrong-140703141348-phpapp01/95/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong-23-638.jpg?cb=1404397117 "jwt vs cookie ") 


References : 
* [https://auth0.com/blog/cookies-vs-tokens-definitive-guide/](https://auth0.com/blog/cookies-vs-tokens-definitive-guide/)
* [https://www.w3schools.com/js/js_cookies.asp](https://www.w3schools.com/js/js_cookies.asp)
* [https://www.slideshare.net/derekperkins/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong](https://www.slideshare.net/derekperkins/authentication-cookies-vs-jwts-and-why-youre-doing-it-wrong)

### 28. What is Web Workers?

Web Workers makes it possible to run a script operation in background thread separate from the main execution thread of a web application. The advantage of this is that laborious processing can be performed in a separate thread, allowing the main (usually the UI) thread to run without being blocked/slowed down.

workers run in another global context that is different from the current window. This context is represented by either a `DedicatedWorkerGlobalScope` object (in the case of dedicated workers - workers that are utilized by a single script), or a `SharedWorkerGlobalScope` (in the case of shared workers - workers that are shared between multiple scripts).

In addition to dedicated workers, there are other types of worker:

* Shared workers are workers that can be utilized by multiple scripts running in different windows, IFrames, etc., as long as they are in the same domain as the worker. They are a little more complex than dedicated workers — scripts must communicate via an active port. 
* ServiceWorkers essentially act as proxy servers that sit between web applications, the browser, and the network (when available). They are intended, among other things, to enable the creation of effective offline experiences, intercept network requests and take appropriate action based on whether the network is available, and update assets residing on the server. They will also allow access to push notifications and background sync APIs.
* Chrome Workers are a Firefox-only type of worker that you can use if you are developing add-ons and want to use workers in extensions and have access to js-ctypes in your worker. See ChromeWorker for more details. 
* Audio Workers provide the ability for direct scripted audio processing to be done inside a web worker context.

References : 
* [https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
* [https://www.w3schools.com/html/html5_webworkers.asp](https://www.w3schools.com/html/html5_webworkers.asp)


### 29. What is Server-Sent Events(SSE)?

A server-sent event is when a web page automatically gets updates from a server.

This was also possible before, but the web page would have to ask if any updates were available. With server-sent events, the updates come automatically.

Examples: Facebook/Twitter updates, stock price updates, news feeds, sport results, etc.

```javascript
var source = new EventSource("demo_sse.php");
source.onmessage = function(event) {
    document.getElementById("result").innerHTML += event.data + "<br>";
};
```

References : 
* [https://www.w3schools.com/html/html5_serversentevents.asp](https://www.w3schools.com/html/html5_serversentevents.asp)
* [https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)
* [https://www.html5rocks.com/en/tutorials/eventsource/basics/](https://www.html5rocks.com/en/tutorials/eventsource/basics/)

### 30. What does charset do?

To display an HTML page correctly, a web browser must know which character set (character encoding) to use.

 UTF-8 (U from Universal Character Set + Transformation Format—8-bit) is a character encoding capable of encoding all possible characters (called code points) in Unicode. The encoding is variable-length and uses 8-bit code units.

 This is specified in the `<meta>` tag:
```html
 <meta charset="UTF-8">
```
 The user agent looks for the Content-Type response HTTP header sent from the server:
```
Content-Type: text/html; charset=utf-8
```
And if the Content-Type header doesn't specify a charset the depending on the User Agent different things might happen. Some user agents might try to use heuristics to guess the correct charset by analyzing some of the bytes from the response stream looking for known encodings. And if this fails you might end up with a couple of question marks or weird symbols in your web page at the place where you used characters outside of the ASCII range.

References : 
* [https://www.w3schools.com/html/html_charset.asp](https://www.w3schools.com/html/html_charset.asp)
* [https://stackoverflow.com/a/16505406/3421966](https://stackoverflow.com/a/16505406/3421966)


### 31. Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

While building DOM, If there are style sheets placed before scripts in the document, the construction of DOM and CSSOM objects can interfere with each other. When the parser gets to a script tag, DOM construction cannot proceed until the JavaScript finishes executing, and the JavaScript cannot be executed until the CSS is downloaded, parsed, and the CSSOM is available.

So, it is good practice to place style sheets in `<head>` section and `<script>` a just before `</body>` tag.

![css js render](https://2r4s9p1yi1fa2jd7j43zph8r-wpengine.netdna-ssl.com/files/2017/09/blocking-bold@2x-1.png)

References : 
* [https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/](https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/)


### 32. What is progressive rendering?

Progressive rendering is the name given to techniques used to render content for display as quickly as possible.

In Short, page begins to appear and the text can be read even before all of the text and/or images have been completely downloaded.

Progressive rendering is a rendering mode in which the program gradually updates small parts of the entire image refining it from low quality to final result rather than focusing on one small part of the image at a time. The goal of progressive rendering is to always be able to see the process of refining the rendered image as a whole, pretty much like a painter sees his work evolve from a sketch by looking at the whole canvas after he adds more and more details.

References : 
* [https://jmperezperez.com/medium-image-progressive-loading-placeholder/](https://jmperezperez.com/medium-image-progressive-loading-placeholder/)
* [https://coronarenderer.freshdesk.com/support/solutions/articles/5000516260-what-is-progressive-rendering-](https://coronarenderer.freshdesk.com/support/solutions/articles/5000516260-what-is-progressive-rendering-)


### 33. Why you would use a srcset attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.

The srcset attribute specifies the URL of the image to use in different situations. It allows you to declare a set of images to be displayed on different viewport sizes.

```html
<img alt="my awesome image"
  src="banner.jpeg"
  srcset="banner-HD.jpeg 2x, banner-phone.jpeg 640w, banner-phone-HD.jpeg 640w 2x">
  ```
The above would serve banner-phone.jpeg to devices with viewport width under 640px, banner-phone-HD.jpeg to small screen high DPI devices, banner-HD.jpeg to high DPI devices with screens greater than 640px, and banner.jpeg to everything else.

  ```html
  <picture>
  <source media="(min-width: 650px)" srcset="img_pink_flowers.jpg">
  <source media="(min-width: 465px)" srcset="img_white_flower.jpg">
  <img src="img_orange_flowers.jpg" alt="Flowers" style="width:auto;">
</picture>
```

References :

* [https://www.html5rocks.com/en/mobile/high-dpi/#toc-srcset](https://www.html5rocks.com/en/mobile/high-dpi/#toc-srcset)
* [https://www.w3schools.com/tags/att_source_srcset.asp](https://www.w3schools.com/tags/att_source_srcset.asp)


### 34. Have you used different HTML templating languages before?

To update your HTML when values update(for dynamic binding), you can use templates, which cleans up your code hugely. There are plenty of templating libraries available like Mustache, Handlebars, Jade etc.