---
title: Foundations
created: '2024-05-14T20:20:10.270Z'
modified: '2024-05-15T19:28:39.633Z'
---

# Foundations

### Introduction to HTML and CSS
* HTML is the raw data that a webpage is built out of. All the text, links, cards, lists, and buttons are created in HTML.
* CSS positions the information, gives it color, and changes the font.
* HTML and CSS do not program any logic.

### Elements and Tags
* Almost all elements on an HTML page are just pieces of content wrapped in opening and closing HTML tags.
* Opening tags tell the browser where the start of the element is, enclosed in angle brackets '<>'.
* Closing tags tell the browser where an element ends. They have a forward slash before the keyword in the brackets '</>'.
* HTML documents are encapsulated with an HTML element ```<html> </html>```.
* Some HTML elements do not have a closing tag (void elements). They are void of content, and cannot wrap content like other tags do. 
  * These look like the ```<img />``` element, where the forward slash is put behind the element name. 
    * In HTML5, the forward slash at the end of the ```<img>``` tag is optional. 
* All HTML tags are predefined. There is a list of elements [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

### HTML Boilerplate
* All HTML documents have the same basic structure that needs to be in place before anything useful can be done.
* You should always name the HTML file that will contain the homepage of the website 'index.html'.
  * Web servers will by default look for this page when users land on a website.
* Every HTML page starts with a doctype declaration. It tells the browser what version of HTML it should use to render the document. 
  * The latest version is HTML5, which can be accomplished with ```<!DOCTYPE html>```.
* After declaring the doctype, you must provide an ```<html>``` element. This is the root element.
  * You must close this as well.
  * You can specify the english language with ```<html lang="en">```.
    * 'lang' is an attribute associated with the HTML tag.
* The ```<head>``` element contains important meta-information about our webpages along with stuff required to make the webpages render correctly in the browser.
  * The head element contains a ```<meta>``` tag with the charset encoding of the webpage. For UTF-8, use ```<meta charset="utf-8">```.
  * The head element also contains the ```<title>``` element. This is the title of the webpage that is put at the top of the browser where tabs are.
* The ```<body>``` element contains content that will be displayed to users. It goes within the ```<html>``` element but is always below the ```<head>``` element.
* The [W3 HTML Validator](https://validator.w3.org/) ensures your markup is correct.

### Working with Text
* Paragraph elements add a line after each paragraph. It is defined by wrapping text with a ```<p>``` tag.
* Headings have six different levels, from ```<h1>``` to ```<h6>```, the largest is h1, while h6 is the smallest.
* The ```<strong>``` element makes text bold. It also semantically marks it as important for screen readers.
* The ```<em>``` element makes text italic. 
* We indent elements that are within other elements. This is known as nesting elements.
  * There are parent, child, and sibling relationships.
* HTML comments are enclosed with ```<!--``` and ```-->``` tags.
  * An example would be ```<!-- comment -->```.
* You can use ```<b>``` to convey boldness and ```<i>``` for italics. ```<b>``` does not semantically cause importance to a word. ```<i>``` conveys a different mood or voice from the surrounding context.

### Lists
* HTML has two types of lists, ordered and unordered.
* Unordered lists are created using the ```<ul>``` element, and each item within the list is created using the list item element ```<li>```.
  * Each list item is displayed with a bullet point.
* Ordered lists are created using the ```<ol>``` element. It still uses the list item element ```<li>```, but instead of using bullet points it uses numbers.

### Links and Images

##### Links
* To create a link in HTML, we use the anchor element. It is defined by wrapping the text or another HTML element that we want to be the link with an ```<a>``` tag.
  * We need to tell the link where to go by using an HTML attribute.
* HTML attributes give additional information to an HTML element and always goes in the element's opening tag. It usually is made up of a name and a value (but doesn't always require a value).
  * An example link would look like this: ```<a href="https://www.google.com">click here to go to google</a>```.
    * In this case, 'href' is the attributes name, while the link is the value. 
* Another attribute you can add along with a link is 'target'. This attribute allows you to choose if you want the link opened in a new tab or not. 
  * The default value for 'target' is '_self'. This means that the link opens in the current tab.
  * The alternative value for 'target' is '_blank'.
  * When specifying this attribute, another is required. This is called 'rel'. This allows the opened link to gain access to the webpage from which is was opened. 
    * ```rel="noopener noreferrer"``` is how this attribute appears. 'noopener' prevents the opened link from gaining access, which prevents phishing attacks.
      * 'noreferrer' prevents the opened link from knowing which webpage or resource has a link to it. This prevents "tabnapping".
* To open a tab in a new window to Google and to prevent Google knowing about our page, we do this: ```<a href="https://www.google.com" target="_blank" rel="noopener noreferrer">Google</a>```.
* There are two kinds of links: Links to pages on other websites on the internet, Links to pages located on our own websites. These are known respectively as Absolute Links and Relative Links.
  * Absolute links are made up of the following parts: ```protocol://domain/path```. An absolute link will always contains the protocol and domain of the destination. 
  * Relative links do not include the domain name since it is another page on the same site. We use the relative filepath from the current page to create a link.
    * Prepending ```./``` before the link in most cases will prevent indexing errors. This makes the search relative to the current directory.
    * If you wanted to link to the HTML page 'about' in the directory 'pages', you would do this: ```<a href="pages/about.html">about page</a>```.
* Relative paths will always be faster than abolute paths for server speed.

##### Images
* To display an image, we use the ```<img>``` element. This image is self-closing. 
  * Empty, self-closing HTML elements do not need a closing tag. 
  * Instead of wrapping content with an opening and closing tag, it embeds an image into the page using a src attribute. 
    * The src attribute works much like the href attribute for anchor tags. It can use both absolute and relative paths.
  * An example would be ```<img src="https://www.theodinproject.com/mstile-310x310.png">``` or ```<img src="./images/dog.jpg">```.
* <b> Besides the src attribute, every image must also have an alt (alternative text) attribute. </b>
  * This is used to describe an image. It will be used in place of the image if it cannot be loaded and is used with screen readers to describe the image. 
  * Example: ``` <img src="https://www.theodinproject.com/mstile-310x310.png" alt="The Odin Project Logo">```.
* While not required, you can specify the height and width of an image which helps the browser with the layout. 
  * Example: ``` <img src="https://www.theodinproject.com/mstile-310x310.png" alt="The Odin Project Logo" height="310" width="310">```.
* Keeping files organized when building a website is very important. 
  * Many people create a folder for images called 'img'.
  * There is also a 'css' and 'js' folder in the home directory.
  * Keep naming simple and lowercase. Make file names as simple as possible to avoid problems. Do not use spaces, capitals, and numbers if possible.
* There are four main image formats in use on the web. JPG, GIF, PNG, and SVG.
  * JPG images are designed for handling larger color palettes without increasing file size. 
    * Good for images with lots of gradients, but doesn't allow transparent pixels. 
  * GIFs are the go-to option for simple animations. They are limited in color palette, and cannot get great detail on a transparent background. 
  * PNGs are great for anything that's not a photo or animated. PNGs for photos are generally larger than an equivalent JPG file. They deal with opacity fine and have no color palette limitations. 
    * Ideal for icons, technical diagrams, logos, etc. 
  * SVG is a vector-based graphics format. It can scale up or down to any dimension without loss of quality.
    * This is a plus for responsive design. 
    * Good for all use cases as PNGs, and should be used whenever possible. 
    * One downside is that you need to convert any text fields to outlines using your image editor. Can have an impact on file size if there is a lot of text in images.
* By default, the ```<img/>``` element uses the inherit dimensions of its image file. 
  * Pixel-based image formats need to be twice as big as you want them to appear on retina displays. 
  * Dimension values are in pixels. These attributes are usually better to set with CSS so you can alter them with media queries. 


### Commit Messages
* A good commit consists of a subject and a body. 
  * The subject is a brief summary of the change made to a project.
  * The body is a concise yet clear description of what you did. 
  * There is a 72-character limit.
* Commit every time there is a meaningful change in the code. 

### Intro to CSS







