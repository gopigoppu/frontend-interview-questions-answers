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










