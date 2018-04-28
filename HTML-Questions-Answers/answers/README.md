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

