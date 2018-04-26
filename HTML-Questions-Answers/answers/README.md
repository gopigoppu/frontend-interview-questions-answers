# HTML Question Answers.


#### 1. Is HTML case sensitive?

HTML is case insenstivie. But it is good practice to keep HTML markup lowercase. 

XHTML, that is being XML is case sensitive. 

References :
* [http://www.w3.org/TR/html5/syntax.html](http://www.w3.org/TR/html5/syntax.html)

* [https://www.w3.org/TR/xhtml1/#h-4.2](https://www.w3.org/TR/xhtml1/#h-4.2)

#### 2. What is doctype in HTML?

 DOCTYPE describes the HTML that will be used in your page. Browsers also use the DOCTYPE to determine how to render a page. Not including a DOCTYPE or including an incorrect DOCTYPE can trigger quirks mode. 

 ```html
 <!DOCTYPE html>
 ```
 Above declaration indicates that the page is HTML5 document type. 

 References : 

 * [https://www.w3schools.com/tags/tag_doctype.asp](https://www.w3schools.com/tags/tag_doctype.asp)
 * [https://stackoverflow.com/questions/414891/what-is-doctype](https://stackoverflow.com/questions/414891/what-is-doctype)

 #### 3. What does lang attribute do?

The HTML lang attribute is used to identify the language of text content on the web or a portion of a web page. This is meant to assist search engine spiders, page formatting and screen reader technology.

References : 
* [https://developer.paciellogroup.com/blog/2016/06/using-the-html-lang-attribute/](https://developer.paciellogroup.com/blog/2016/06/using-the-html-lang-attribute/)

* [https://www.w3.org/International/questions/qa-lang-why](https://www.w3.org/International/questions/qa-lang-why)

#### 4. How do you serve page with content in multiple languages?

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

#### 5. What are all list of inline and block level elements?

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


#### 6. What is empty tag and why do we need it?

HTML elements with no content are called empty elements. Empty elements do not have an end tag. The representation of an empty element is either a start-tag immediately followed by an end-tag, or an empty-element tag
E.g. `<br>` or `<br />`


**Note** : A container tag has two ends (an opening and a closing) whereas an empty tag doesn't. The paragraph tag `<p></p>` is an example of a container tag. 


#### 7. What is async and defer in HTML? What does it do and how it defers?

async and defer are attributes, which is added in script tag to define script execution during HTML parsing.

* `<script>` - 
 The HTML file will be parsed until the script file is hit, at that point parsing will stop and a request will be made to fetch the file (if it’s external). The script will then be executed before parsing is resumed.

* `<script async>` - 
async downloads the file during HTML parsing and will pause the HTML parser to execute it when it has finished downloading.

* `<script defer>` - 
defer downloads the file during HTML parsing and will only execute it after the parser has completed. defer scripts are also guaranteed to execute in the order that they appear in the document.


References : 

* [http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html](http://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)
* [https://stackoverflow.com/questions/10808109/script-tag-async-defer](https://stackoverflow.com/questions/10808109/script-tag-async-defer)
* [https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/](https://hacks.mozilla.org/2017/09/building-the-dom-faster-speculative-parsing-async-defer-and-preload/)











