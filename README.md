# Bootstrap 4 and JavaScript






## Examples of Personal Websites

* https://dveleztx.github.io/
* https://jtom.me/
* https://caferati.me/
* https://andrewborstein.com/
* https://chippd.github.io/
* https://www.adamhartwig.co.uk/
* https://derolez.dev/
* https://www.devonstank.com/
* http://findmatthew.com/
* http://brandoncjohnson.com/

## Bootstrap 4







---
---

## JavaScript
Is a high-level programming language. It was originally designed as a scripting language for websites but became widely adopted as a general-purpose programming language, and is currently the most popular programming language in use. JavaScript is usually found running in a web browser as interactive or automated content, ranging from popup messages and live clocks to large web applications. JavaScript is also commonly used in server-side programming through platforms like Node.js , or "embedded" in non-JavaScript applications where the base programming language lacks the high-level functionality that JavaScript offers.

Alongside HTML and CSS, JavaScript is one of the core technologies of the World Wide Web. Despite the similarities in name and syntax, JavaScript is not related to the programming language Java. Though the names of both languages are trademarks of Oracle Corporation, the two languages follow different design principles, and are actively developed by unrelated organizations. 

### [Console API](https://developer.mozilla.org/en-US/docs/Web/API/Console_API)
The Console API provides functionality to allow developers to perform debugging tasks, such as logging messages or the values of variables at set points in your code, or timing how long an operation takes to complete.

* Provides rudimentary debugging functionality, including logging, stack traces, timers, and counters
* By far the most commonly-used method is `console.log`, which is used to log the current value contained inside a specific variable

##### Syntax

###### JavaScript
```
let myString = 'Hello world';

// Output "Hello world" to the console
console.log(myString)
```

---

### [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)
The Document interface represents any web page loaded in the browser and serves as an entry point into the web page's content, which is the DOM tree. The DOM tree includes elements such as <body> and <table>, among many others. It provides functionality globally to the document, like how to obtain the page's URL and create new elements in the document.

### Methods

#### document.getElementById(*id*)
**Document.getElementById()** returns an Element object representing the element whose id property matches the specified string. Since element IDs are required to be unique if specified, they're a useful way to get access to a specific element quickly.

**id**: The ID of the element to locate. The ID is case-sensitive string which is unique within the document; only one element may have any given ID. 
##### Syntax
HTML
```
<html>
<head>
  <title>getElementById example</title>
</head>
<body>
  <p id="para">Some text here</p>
  <button onclick="changeColor('blue');">blue</button>
  <button onclick="changeColor('red');">red</button>
</body>
</html>
```
JavaScript
```
function changeColor(newColor) {
  var elem = document.getElementById('para');
  elem.style.color = newColor;
}
```

---

#### document.write(*markup*)
The **document.write()** method writes a string of text to a document stream.

**markup**: A string containing the text to be written to the document 

##### Syntax
JavaScript
```
document.write("<h1>Out with the old - in with the new!</h1>");
```

---

### [GlobalEventHandlers](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
The **GlobalEventHandlers** mixin describes the event handlers common to several interfaces like HTMLElement, Document, or Window. Each of these interfaces can, of course, add more event handlers in addition to the ones listed below.

### Methods

#### onmouseover()
The onmouseover property of the GlobalEventHandlers mixin is an EventHandler that processes mouseover events.

The mouseover event fires when the user moves the mouse over a particular element.

##### Syntax

###### HTML
```
<p>Test your mouse on me!</p>
```
###### JavaScript
```
const p = document.querySelector('p');
p.onmouseover = logMouseOver;
p.onmouseout = logMouseOut;

function logMouseOver() {
  p.innerHTML = 'MOUSE OVER detected';
}

function logMouseOut() {
  p.innerHTML = 'MOUSE OUT detected';
}
```

---

#### onclick()
The onclick property of the GlobalEventHandlers mixin is the EventHandler for processing click events on a given element.

The click event is raised when the user clicks on an element. It fires after the mousedown and mouseup events, in that order.

##### Syntax

###### HTML
```
<button id="demo">Click here</button>
```
###### JavaScript
```
document.getElementById('demo').onclick = function changeContent() {

   document.getElementById('demo').innerHTML = "Help me";
   document.getElementById('demo').style = "Color: red";

}
```

---

#### onload()
The onload property of the GlobalEventHandlers mixin is an EventHandler that processes load events on a Window, XMLHttpRequest, `<img>` element, etc.

The load event fires when a given resource has loaded.

##### Syntax
###### JavaScript
```
window.onload = function() {
  init();
  doSomethingElse();
};
```

**Note**: The load event fires at the end of the document loading process. At this point, all of the objects in the document are in the DOM, and all the images, scripts, links and sub-frames have finished loading.

There are also DOM Events like DOMContentLoaded and DOMFrameContentLoaded (which can be handled using EventTarget.addEventListener()) which are fired after the DOM for the page has been constructed, but do not wait for other resources to finish loading.

---

### [Window](https://developer.mozilla.org/en-US/docs/Web/API/Window)
The Window interface represents a window containing a DOM document; the document property points to the DOM document loaded in that window. A window for a given document can be obtained using the document.defaultView property.

### Methods

#### window.alert(*message*)
The **window.alert()** method displays an alert dialog with the optional specified content and an OK button.

* **message** (optional): A string of text to display to the user. Can be omitted if there is nothing to show in the prompt window.

##### Syntax
###### JavaScript
```
window.alert(message);
```
or
###### JavaScript
```
alert(message);
```

---

#### window.prompt(*message*, *default*)
The **window.prompt()** displays a dialog with an optional message prompting the user to input some text.

* **message** (optional): A string of text to display to the user. Can be omitted if there is nothing to show in the prompt window.
* **default** (optional): A string containing the default value displayed in the text input field.

##### Syntax
###### JavaScript
```
result = window.prompt(message, default);
```

**NOTE**: The return value of window.prompt() is a string containing the text entered by the user, or null.

---

### [WindowOrWorkerGlobalScope](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope)
The WindowOrWorkerGlobalScope mixin describes several features common to the Window and WorkerGlobalScope interfaces. Each of these interfaces can, of course, add more features in addition to the ones listed below.

### Methods

#### fetch(*resource* *[, init]*)
The fetch() method of the WindowOrWorkerGlobalScope mixin starts the process of fetching a resource from the network, returning a promise which is fulfilled once the response is available. The promise resolves to the Response object representing the response to your request. The promise does not reject on HTTP errors — it only rejects on network errors. You must use then handlers to check for HTTP errors.

* resource
    This defines the resource that you wish to fetch. This can either be:
    * A USVString containing the direct URL of the resource you want to fetch. Some browsers accept the blob: and data: schemes.
    * A Request object.
* init (Optional)
    An object containing any custom settings that you want to apply to the request. The possible options are:

    * method
        The request method, e.g., `GET`, `POST`. Note that the Origin header is not set on Fetch requests with a method of `HEAD` or `GET`.
        (This behavior was corrected in Firefox 65 — see bug 1508661).
    * headers
        Any headers you want to add to your request, contained within a Headers object or an object literal with ByteString values. Note that some names are forbidden.
    * body
        Any body that you want to add to your request: this can be a Blob, BufferSource, FormData, URLSearchParams, USVString, or ReadableStream object. Note that a request using the `GET` or `HEAD` method cannot have a body.
    * mode
        The mode you want to use for the request, e.g., cors, no-cors, or same-origin.
    * credentials
        The request credentials you want to use for the request: omit, same-origin, or include. To automatically send cookies for the current domain, this option must be provided. Starting with Chrome 50, this property also takes a FederatedCredential instance or a PasswordCredential instance.
    * cache
        The cache mode you want to use for the request.
    * redirect
        The redirect mode to use: follow (automatically follow redirects), error (abort with an error if a redirect occurs), or manual (handle redirects manually). In Chrome the default is follow (before Chrome 47 it defaulted to manual).
    * referrer
        A USVString specifying the referrer of the request. This can be a same-origin URL, about:client, or an empty string.
    * referrerPolicy
        Specifies the referrer policy to use for the request. May be one of no-referrer, no-referrer-when-downgrade, same-origin, origin, strict-origin, origin-when-cross-origin, strict-origin-when-cross-origin, or unsafe-url.
    * integrity
        Contains the subresource integrity value of the request (e.g., `sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=`).
    * keepalive
        The keepalive option can be used to allow the request to outlive the page. Fetch with the keepalive flag is a replacement for the `Navigator.sendBeacon()` API. 
    * signal
        An AbortSignal object instance; allows you to communicate with a fetch request and abort it if desired via an AbortController.

---
### Additional Resources
* https://developer.mozilla.org/bm/docs/Web/JavaScript/Guide
* https://www.w3schools.com/js/
* http://jsforcats.com/
* https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/JavaScript_Introduction.html
* https://www.asmarterwaytolearn.com/htmlcss/j.html (first page is blank scroll down a little to see the content)
* https://channel9.msdn.com/Series/Javascript-Fundamentals-Development-for-Absolute-Beginners
* https://javascript.info/

#### Tutorials
* https://www.learn-js.org/
* https://learnjavascript.online/
* https://www.codecademy.com/learn/introduction-to-javascript
* https://developer.mozilla.org/en-US/docs/Web/JavaScript
* https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/




---
### Programming problems
1. Write a script that reads an integer and determines and displays whether it is an odd or even number.

2. A company wants to transmit data over a network, but they are concerned that the link may be tapped. All of its data is transmitted as four-digit integers. It has asked you to write a program that will encrypt its data so that the data may be transmitted more securely. Your script should read a four-digit integer entered by the user in a prompt dialog and encrypt it as follows: Replace each digit by (the sum of that digit plus 7) modulus 10 . Then swap the first digit with the third digit, and swap the second digit with the fourth. Then output html5 text that displays the encrypted integer.

3. A mail-order house sells five different products whose retail prices are as follows: product 1, $2.98; product 2, $4.50; product 3, $9.98; product 4, $4.49; and product 5, $6.87. Write a script that reads a series of pairs of numbers as follows: a) Product number b) Quantity sold for one day Your program should use a switch statement to determine each product's retail price and should calculate and output HTML5 that displays the total retail value of all the products sold last week. Use a sentinel-controlled loop to determine when the program should stop looping and display the final results.
