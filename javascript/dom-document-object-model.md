# JavaScript HTML DOM

source: [W3Schools](https://www.w3schools.com/js/js_htmldom.asp)

With the HTML DOM, JavaScript can access and change all the elements of an HTML document.

## The HTML DOM (Document Object Model)

When a web page is loaded, the browser creates a Document Object Model (DOM) of the page.

The **HTML DOM** model is constructed as a tree of **Objects**:
![](/img/Pasted-image-20230110.png)

With the object model, JavaScript gets all the power it needs to create dynamic HTML:

- JavaScript can change all the HTML elements in the page
- JavaScript can change all the HTML attributes in the page
- JavaScript can change all the CSS styles in the page
- JavaScript can remove existing HTML elements and attributes
- JavaScript can add new HTML elements and attributes
- JavaScript can react to all existing HTML elements and attributes
- JavaScript can create new HTML events in the page

## What You Will Learn

In the next chapters of this tutorial you will learn:

- How to change the content of HTML elements
- How to change the style (CSS) of HTML elements
- How to react to HTML DOM events
- How to add and delete HTML elements

## What is DOM?

The DOM is a W3C (World Wide Web Consortium) standard.

The DOM defines a standard for accessing documents:

_The W3C Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document._

The W3C DOM standard is separated into 3 different parts:

- Core DOM - standard model for all document types
- XML DOM - standard model for XML documents
- HTML DOM - standard model for HTML documents

## What is the HTML DOM?

The HTML DOM is a standard **object** model and **programming interface** for HTML. It defines:

- The HTML elements as **objects**
- The **properties** of all HTML elements
- The **methods** to access all HTML elements
- the **events** for all HTML elements

In other words: **THe HTML DOM is a standard for how to get, change, add, or delete HTML elements.**

# DOM Methods

HTML DOM methods are **actions** you can perform (on HTML Elements).

HTML DOM properties are **values** (of HTML Elements) that you can set or change.

## The DOM Programming Interface

The HTML DOM can be accessed with JavaScript (and with other programming languages).

In the DOM, all HTML elements are defined as **objects**.

The programming interface is the properties and methods of each object.

A **property** is a value that you can get or set (like changing the content of an HTML element).

A **method** is an action you can do (like add or deleting an HTML element).

**Example**:

The following example changes the content (the `innerHTML`) of the `<p>` element with `id="demo"`:

```html
<html>
  <body>
    <p id="demo"></p>

    <script>
      document.getElementById("demo").innerHTML = "Hello World!";
    </script>
  </body>
</html>
```

In the example above, `getElementById` is a **method**, while `innerHTML` is a **property**.

### The getElementByID Method

The most common way to access an HTML element is to use the `id` of the element.

In the example above the `getElementById` method used `id="demo"` to find the element.

### The innerHTML Property

The easiest way to get the content of an element is by using the `innerHTML` property.

The `innerHTML` property is useful for getting or replacing the content of HTML elements.

> The `innerHTML` property can be used to get or change any HTML element, including `<html>` and `<body>`.

# DOM Document

The HTML DOM document object is the owner of all other objects in your web page.

## The HTML DOM Document Object

The document object represents your web page.

If you want to access any element in an HTML page, you always start with accessing the document object.

Below are some examples of how you can use the document object to access and manipulate HTML.

### Finding HTML Elements

| Method                               | Description                   |
| ------------------------------------ | ----------------------------- |
| document.getElementById(id)          | Find an element by element id |
| document.getElementByTagName(name)   | Find elements by tag name     |
| document.getElementByClassName(name) | Find elements by class name   |

### Changing HTML Elements

| Property                               | Description                                   |
| -------------------------------------- | --------------------------------------------- |
| element.innerHTML = _new html content_ | Change the inner HTML of an element           |
| element.attribute = _new value_        | Change the attribute value of an HTML element |
| element.style.property = _new style_   | Change the style of an HTML element           |
| **Method**                             | **Description**                               |
| element.setAttribute(attribute, value) | Change the attribute value of an HTML element |

### Adding and Deleting Elements

| Method                            | Description                       |
| --------------------------------- | --------------------------------- |
| document.createElement(_element_) | Create an HTML element            |
| document.removeChild(_element_)   | Remove an HTML element            |
| document.appendChild(_element_)   | Add an HTML element               |
| document.replaceChild(_new, old_) | Replace a HTML element            |
| document.write(_text_)            | Write into the HTML output stream |

### Adding Events Handlers

| Method                                                   | Description                                   |
| -------------------------------------------------------- | --------------------------------------------- |
| document.getElementById(_id_).onclick = function(){code} | Adding event handler code to an onclick event |

# DOM Elements

This page teaches you how to find and access HTML elements in an HTML page.

## Finding HTML Elements

Often, with JavaScript, you want to manipulate HTML elements.

To do so, you have to find the elements first. There are several ways to do this:

- Finding HTML elements by id
- Finding HTML elements by tag name
- Finding HTML elements by class name
- Finding HTML elements by CSS selectors
- Finding HTML elements by HTML object collections

```js
// Finding HTML Element by ID
const element = document.getElementById("intro");
```

```js
// Finding HTML Elements by Tag Name
const element = document.getElementsByTagName("p");
```

```js
// This example finds the element with `id="main"`, and then finds all `<p>` element inside the `"main"`
const x = document.getElementById("main");
const y = x.getElementsByTagName("p");
```

```js
// Finding HTML Element by Class Name
const x = document.getElementsByClassName("intro");
```

```js
// Finding HTML Elements by CSS Selectors
const x = document.querySelectorAll("p.intro");
```

```js
// Finding HTML Elements by HTML Object Collections
const x = document.forms["frm1"];
let text = "";
for (let i = 0; i < x.length; i++) {
  text += x.elements[i].value + "<br>";
}
document.getElementById("demo").innerHTML = text;
```

# DOM - Changing HTML

The HTML DOM allows JavaScript to change the content of HTML elements.

## Changing the HTML Content

```html
<html>
  <body>
    <p id="p1">Hello World!</p>

    <script>
      document.getElementById("p1").innerHTML = "New text!";
    </script>
  </body>
</html>
```

Example explained:

- The HTML document above contains a `<p>` element with `id="p1"`
- We use the HTML DOM to get the element with `id="p1"`
- A JavaScript changes the content (`innerHTML`) of that element to "New text!"

This example changes the content of an `<h1>` element:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 id="id01">Old Heading</h1>

    <script>
      const element = document.getElementById("id01");
      element.innerHTML = "New Heading";
    </script>
  </body>
</html>
```

Example explained:

- The HTML document above contains an `<h1>` element with `id="id01"`
- We use the HTML DOM to get the element with `id="id01"`
- A JavaScript changes the content (`innerHTML`) of that element to "New Heading"

## Changing the Value of an Attribute

```html
<!DOCTYPE html>
<html>
  <body>
    <img id="myImage" src="smiley.gif" />

    <script>
      document.getElementById("myImage").src = "landscape.jpg";
    </script>
  </body>
</html>
```

Example explained:

- The HTML document above contains an `<img>` element with `id="myImage"`
- We use the HTML DOM to get the element with `id="myImage"`
- A JavaScript changes the `src` attribute of that element from "smiley.gif" to "landscape.jpg"

## Dynamic HTML content

```html
<!DOCTYPE html>
<html>
  <body>
    <script>
      document.getElementById("demo").innerHTML = "Date : " + Date();
    </script>
  </body>
</html>
```

## document.write()

```html
<!DOCTYPE html>
<html>
  <body>
    <p>Bla bla bla</p>

    <script>
      document.write(Date());
    </script>

    <p>Bla bla bla</p>
  </body>
</html>
```

# DOM Forms | JavaScript Forms

## JavaScript Form Validation

HTML form validation can be done by JavaScript.

If a form field (fname) is empty, this function alerts a message, and returns false, to prevent the form from being submitted:

```js
function validateForm() {
  let x = document.forms["myForm"]["fname"].value;
  if (x == "") {
    alert("Name must be filled out");
    return false;
  }
}
```

The function can be called when the form is submitted:

```html
<form
  name="myForm"
  action="/action_page.php"
  onsubmit="return validateForm()"
  method="post"
>
  Name: <input type="text" name="fname" />
  <input type="submit" value="Submit" />
</form>
```

## Automatic HTML Form Validation

HTML form validation can be performed automatically by the browser:

If a form field (fname) is empty, the `required` attribute prevents this form from being submitted:

```html
<form action="/action_page.php" method="post">
    <input type="text" name="fname" required />   <input
    type="submit"
    value="Submit"
  />
</form>
```

## Data Validation

Data validation is the process of ensuring that user input is clean, correct, and useful.

Typical validation tasks are:

- has the user filled in all required fields?
- has the user entered a valid date?
- has the user entered text in a numeric field?

Most often, the purpose of data validation is to ensure correct user input.

Validation can be defined by many different methods, and deployed in many different ways.

**Server side validation** is performed by a web server, after input has been sent to the server.

**Client side validation** is performed by a web browser, before input is sent to a web server.

## HTML Constraint Validation

HTML5 introduced a new HTML validation concept called **constraint validation**.

HTML constraint validation is based on:

- Constraint validation **HTML** **Input Attributes**
- Constraint validation **CSS Pseudo Selectors**
- Constraint validation **DOM Properties and Methods**

### Constraint Validation HTML Input Attributes

| Attribute | Description                                         |
| --------- | --------------------------------------------------- |
| disable   | Specifies that the input element should be disabled |
| max       | Specifies the maximum value of an input element     |
| min       | Specifies the minimum value of an input element     |
| pattern   | Specifies the value pattern of an input element     |
| required  | Specifies that the input field requires an element  |
| type      | Specifies the type of an input element              |

For a full list, go to [HTML Input Attributes](https://www.w3schools.com/html/html_form_attributes.asp)

### Constraint Validation CSS Pseudo Selectors

| Selector  | Description                                                    |
| --------- | -------------------------------------------------------------- |
| :disable  | Selects input elements with the "disable" attribute specified  |
| :invalid  | Selects input elements with invalid values                     |
| :optional | Selects input elements with no "required" attribute specified  |
| :required | Selects input elements with the "required" attribute specified |
| :valid    | Selects input elements with valid values                       |

# DOM - Changing CSS

The HTML DOM allows JavaScript to change the style of HTML elements.

## Changing HTML Style

```html
<html>
  <body>
    <p id="p2">Hello World!</p>

    <script>
      document.getElementById("p2").style.color = "blue";
    </script>
  </body>
</html>
```

## Using Events

The HTML DOM allows you to execute code when an event occurs.

Events are generated by the browser when "things happen" to HTML elements:

- An element is clicked on
- The page has loaded
- Input fields are changed

You will learn more about events in the next chapter of this tutorial.

This example changes the style of the HTML element with `id="id1"`, when the user clicks a button:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 id="id1">My Heading 1</h1>

    <button
      type="button"
      onclick="document.getElementById('id1').style.color = 'red'"
    >
      Click Me!
    </button>
  </body>
</html>
```

# DOM Animation

Learn to create HTML animations using JavaScript.

## A Basic Web Page

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>My First JavaScript Animation</h1>

    <div id="animation">My animation will go here</div>
  </body>
</html>
```

### Create an Animation Container

```html
<div id="container">
    
  <div id="animate">My animation will go here</div>
</div>
```

### Style the Elements

```css
#container {
  width: 400px;
  height: 400px;
  position: relative;
  background: yellow;
}
#animate {
  width: 50px;
  height: 50px;
  position: absolute;
  background: red;
}
```

### Animation Code

JavaScript animations are done by programming gradual changes in an element's style.

The changes are called by a timer. When the timer interval is small, the animation looks continuous.

The basic code is:

```js
id = setInterval(frame, 5);

function frame() {
  if (/* test for finished */) {
    clearInterval(id);
  } else {
    /* code to change the element style */ 
  }
}
```

### Create the Full Animation Using JavaScript

```js
function myMove() {
  let id = null;
  const elem = document.getElementById("animate");
  let pos = 0;
  clearInterval(id);
  id = setInterval(frame, 5);
  function frame() {
    if (pos == 350) {
      clearInterval(id);
    } else {
      pos++;
      elem.style.top = pos + "px";
      elem.style.left = pos + "px";
    }
  }
}
```

# DOM Events

HTML DOM allows JavaScript to react to HTML events:

## Reacting to Events

A JavaScript can be executed when an event occurs, like when a user clicks on an HTML element.

To execute code when a user clicks on an element, add JavaScript code to an HTML event attribute: `onclick = JavaScript`

Examples of HTML events:

- When a user clicks the mouse
- When a web page has loaded
- When an image has been loaded
- When the mouse moves over an element
- When an input field is changed
- When an HTML form is submitted
- When a user strokes a key

In this example, the content of the `<h1>` element is changed when a user clicks on it:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>
  </body>
</html>
```

In this example, a function is called from the event handler:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 onclick="changeText(this)">Click on this text!</h1>

    <script>
      function changeText(id) {
        id.innerHTML = "Ooops!";
      }
    </script>
  </body>
</html>
```

## HTML Event Attributes

To assign events to HTML elements you can use event attributes.

```html
<button onclick="displayDate()">Try it</button>
```

In the example above, a function named `displayDate` will be executed when the button is clicked.

## Assign Events Using the HTML DOM

The HTML DOM allows you to assign events to HTML elements using JavaScript:

```html
<script>
  document.getElementById("myBtn").onclick = displayDate;
</script>
```

### The onload and onunload Events

The `onload` and `onunload` events are triggered when the user enters or leaves the page.

The `onload` event can be used to check the visitor's browser type and browser version, and load the proper version of the web page based on the information.

The `onload` and `onunload` events can be used to deal with cookies.

```html
<body onload="checkCookies()"></body>
```

### The onchange Event

The `onchange` event is often used in combination with validation of input fields.

Below is an example of how to use the onchange. The `upperCase()` function will be called when a user changes the content of an input field.

```html
<input type="text" id="fname" onchange="upperCase()" />
```

# DOM EventListener

## The addEventListener() method

```js
document.getElementById("myBtn").addEventListener("click", displayDate);
```

## Add an Event Handler to an Element

```js
element.addEventListener("click", function () {
  alert("Hello World!");
});
```

```js
element.addEventListener("click", myFunction);

function myFunction() {
  alert("Hello World!");
}
```

# DOM Navigation

With the HTML DOM, you can navigate the node tree using node relationships.

## DOM Nodes

According to the W3C HTML DOM standard, everything in an HTML document is a node:

- The entire document is a document node
- Every HTML element is an element node
- The text inside HTML elements are text nodes
- Every HTML attribute is an attribute node (deprecated)
- All comments are comment nodes

![](/img/Pasted-image-20230110201913.png)

With the HTML DOM, all nodes in the node tree can be accessed by JavaScript.

New nodes can be created, and all nodes can be modified or deleted.

## Node Relationships

The nodes in the node tree have a hierarchical relationship to each other.

The terms parent, child, and sibling are used to describe the relationships.

- In a node tree, the top node is called the root (or root node)
- Every node has exactly one parent, except the root (which has no parent)
- A node can have a number of children
- Siblings (brothers or sisters) are nodes with the same parent

```html
<html>
    <head>
        
    <title>DOM Tutorial</title>
      
  </head>

    
  <body>
        
    <h1>DOM Lesson one</h1>
        
    <p>Hello world!</p>
      
  </body>
</html>
```

![](/img/Pasted-image-20230110202015.png)

From the HTML above you can read:

- `<html>` is the root node
- `<html>` has no parents
- `<html>` is the parent of `<head>` and `<body>`
- `<head>` is the first child of `<html>`
- `<body>` is the last child of `<html>`

and:

- `<head>` has one child: `<title>`
- `<title>` has one child (a text node): "DOM Tutorial"
- `<body>` has two children: `<h1>` and `<p>`
- `<h1>` has one child: "DOM Lesson one"
- `<p>` has one child: "Hello world!"
- `<h1>` and `<p>` are siblings

## Navigating Between Nodes

You can use the following node properties to navigate between nodes with JavaScript:

- `parentNode`
- `childNodes[nodenumber]`
- `firstChild`
- `lastChild`
- `nextSibling`
- `previousSibling`

# DOM Elements (Nodes)

Adding and Removing Nodes (HTML Elements)

## Creating New HTML Elements (Nodes)

To add a new element to the HTML DOM, you must create the element (element node) first, and then append it to an existing element.

```html
<div id="div1">
    
  <p id="p1">This is a paragraph.</p>
    
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);

  const element = document.getElementById("div1");
  element.appendChild(para);
</script>
```

## Creating new HTML Elements - insertBefore()

The `appendChild()` method in the previous example, appended the new element as the last child of the parent.

If you don't want that you can use the `insertBefore()` method:

```html
<div id="div1">
    
  <p id="p1">This is a paragraph.</p>
    
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);

  const element = document.getElementById("div1");
  const child = document.getElementById("p1");
  element.insertBefore(para, child);
</script>
```

## Removing Existing HTML Elements

```html
<div>
    
  <p id="p1">This is a paragraph.</p>
    
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  const elmnt = document.getElementById("p1");
  elmnt.remove();
</script>
```

## Removing a Child Node

For browsers that does not support the `remove()` method, you have to find the parent node to remove an element:

```html
<div id="div1">
    
  <p id="p1">This is a paragraph.</p>
    
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  const parent = document.getElementById("div1");
  const child = document.getElementById("p1");
  parent.removeChild(child);
</script>
```

## Replacing HTML Elements

```html
<div id="div1">
    
  <p id="p1">This is a paragraph.</p>
    
  <p id="p2">This is another paragraph.</p>
</div>

<script>
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);

  const parent = document.getElementById("div1");
  const child = document.getElementById("p1");
  parent.replaceChild(para, child);
</script>
```

# DOM Collections

## The HTML Collection Object

The `getElementsByTagName()` method returns an `HTMLCollection` object.

An `HTMLCollection` object is an array-like list (collection) of HTML elements.

The following code selects all `<p>` elements in a document:

```js
const myCollection = document.getElementsByTagName("p");
```

## HTML HTMLCollection Length

The `length` property defines the number of elements in an `HTMLCollection`:

```js
myCollection.length;
```

The `length` property is useful when you want to loop through the elements in a collection:

```js
const myCollection = document.getElementsByTagName("p");
for (let i = 0; i < myCollection.length; i++) {
  myCollection[i].style.color = "red";
}
```

> **An HTMLCollection is NOT an array!**
> An HTMLCollection may look like an array, but it is not.
> You can loop through the list and refer to the elements with a number (just like an array).
> However, you cannot use array methods like valueOf(), pop(), push(), or join() on an HTMLCollection.

# DOM Node Lists

## The HTML DOM NodeList Object

A `NodeList` object is a list (collection) of nodes extracted from a document.

A `NodeList` object is almost the same as an `HTMLCollection` object.

Some (older) browsers return a NodeList object instead of an HTMLCollection for methods like `getElementsByClassName()`.

All browsers return a NodeList object for the property `childNodes`.

Most browsers return a NodeList object for the method `querySelectorAll()`.

The following code selects all `<p>` nodes in a document:

```js
const myNodeList = document.querySelectorAll("p");
```

## HTML DOM Node List Lenght

```js
myNodelist.length;
```

The `length` property is useful when you want to loop through the nodes in a node list:

```js
const myNodelist = document.querySelectorAll("p");
for (let i = 0; i < myNodelist.length; i++) {
  myNodelist[i].style.color = "red";
}
```

## The Difference Between an HTMLCollection and a NodeList

A **NodeList** and an **HTMLcollection** is very much the same thing.

Both are array-like collections (lists) of nodes (elements) extracted from a document. The nodes can be accessed by index numbers. The index starts at 0.

Both have a **length** property that returns the number of elements in the list (collection).

An HTMLCollection is a collection of **document elements**.

A NodeList is a collection of **document nodes** (element nodes, attribute nodes, and text nodes).

HTMLCollection items can be accessed by their name, id, or index number.

NodeList items can only be accessed by their index number.

An HTMLCollection is always a **live** collection. Example: If you add a `<li>`element to a list in the DOM, the list in the HTMLCollection will also change.

A NodeList is most often a **static** collection. Example: If you add a `<li>` element to a list in the DOM, the list in NodeList will not change.

The `getElementsByClassName()` and `getElementsByTagName()` methods return a live HTMLCollection.

The `querySelectorAll()` method returns a static NodeList.

The `childNodes` property returns a live NodeList.
