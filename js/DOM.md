
# Javascript DOM  :robot:

The Document Object Model (DOM) is crucial in web development. The DOM is a programming interface for web documents. It represents the document as a tree of objects, enabling dynamic content manipulation. JavaScript interacts with the DOM to create interactive web experiences.

### DOM Tree
The DOM represents a document as a tree structure. The `document` object is the root, branching into elements, attributes, and text nodes.

**Example DOM Tree:**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Example</title>
  </head>
  <body>
    <div id="main">
      <h1>Welcome</h1>
      <p>Example paragraph.</p>
    </div>
  </body>
</html>
```

### Nodes and Elements

Each part of the document is a node. Common node types include:

- **Element nodes**: Represent HTML tags.
- **Attribute nodes**: Represent attributes.
- **Text nodes**: Represent text content.

### Accessing the DOM

JavaScript provides methods to access and manipulate DOM elements:

- `getElementById(id)`: Select by `id`.
- `getElementsByClassName(className)`: Select by `class`.
- `querySelector(selector)`: Select the first match.
- `querySelectorAll(selector)`: Select all matches.

**Example:**

```javascript
let header = document.getElementById('main');
console.log(header);
```

## 3. Manipulating the DOM

### Changing Content

Use `innerHTML` or `textContent` to change an element's content.

**Example:**

```javascript
let paragraph = document.querySelector('p');
paragraph.innerHTML = 'Content updated!';
```

### Modifying Attributes

Attributes can be accessed and modified using:

- `getAttribute`
- `setAttribute`
- `removeAttribute`

**Example:**

```javascript
let img = document.querySelector('img');
img.setAttribute('src', 'new-image.jpg');
```

### Adding and Removing Elements

Create and add elements using `createElement`, `appendChild`, and `insertBefore`. Remove elements with `removeChild`.

**Example:**

```javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'New div element';
document.body.appendChild(newDiv);
```

## Event Handling in the DOM
Events are actions like clicks, typing, or scrolling. JavaScript can handle these using event listeners.

### Adding Event Listeners
Attach an event handler to an element with `addEventListener`.

**Example:**

```javascript
let button = document.querySelector('button');
button.addEventListener('click', function() {
  alert('Button clicked!');
});
```

### Common Events

- **click**: Triggered by clicking.
- **mouseover**: Triggered by hovering.
- **keydown**: Triggered by pressing a key.

## Use Cases and Applications

### Form Validation

Validate user input on the client side before form submission.

**Example:**

```javascript
let form = document.querySelector('form');
form.addEventListener('submit', function(event) {
  let input = document.querySelector('input').value;
  if (input === '') {
    event.preventDefault();
    alert('Fill out the required field.');
  }
});
```

### Dynamic Content Loading

Load content dynamically without refreshing the page.

**Example:**

```javascript
document.querySelector('#loadContent').addEventListener('click', function() {
  let content = document.createElement('div');
  content.textContent = 'Dynamic content loaded!';
  document.body.appendChild(content);
});
```

### Interactive User Interfaces

Create tabs, modals, and dropdowns for better user interaction.

**Example:**

```javascript
let tabButtons = document.querySelectorAll('.tab-button');
let tabs = document.querySelectorAll('.tab-content');

tabButtons.forEach(function(button, index) {
  button.addEventListener('click', function() {
    tabs.forEach(tab => tab.classList.remove('active'));
    tabs[index].classList.add('active');
  });
});
```

## Some Useful Functions
```
## **Examine the Document Object**

 **1. `console.dir(document);`**
- Outputs a detailed, interactive list of the properties of the `document` object.

 **2. `console.log(document.domain);`**
- Logs the domain name of the document (e.g., `"example.com"`).

 **3. `console.log(document.URL);`**
- Logs the full URL of the document (e.g., `"https://www.example.com/page"`).

 **4. `console.log(document.title);`**
- Logs the title of the document, which is set in the `<title>` tag within the `<head>` section of the HTML.

 **5. `document.title = 123;`**
-  It would set the document’s title to `123`.

 **6. `console.log(document.doctype);`**
- Logs the document type declaration (e.g., `<!DOCTYPE html>`).

 **7. `console.log(document.head);`**
- Logs the `<head>` element of the document, which contains metadata, links to stylesheets, etc.

 **8. `console.log(document.body);`**
- Logs the `<body>` element of the document, which contains the visible content of the webpage.

**9. `console.log(document.all);`**
- Logs a collection of all elements in the document. This property is a legacy feature.

 **10. `console.log(document.all[10]);`**
- Logs the 11th element (index 10) in the document’s collection of all elements.

 **11. `// document.all[10].textContent = 'Hello';` (Commented Out)**
- This line is commented out. If uncommented, it would change the text content of the 11th element in the document to `"Hello"`.

**12. `console.log(document.forms[0]);`**
- Logs the first form (`<form>`) element in the document.

**13. `console.log(document.links);`**
- Logs a collection of all `<a>` elements (links) in the document.

 **14. `// console.log(document.images);` (Commented Out)**
- This line is commented out. If uncommented, it would log a collection of all images (`<img>` elements) in the document.


```
## TextContent vs InnerText
 -   **`textContent`**: Retrieves all text within an element, including hidden text. Faster and simpler, but doesn't consider styling.
 - `innerText`**: Retrieves only visible text, considering CSS styles. Slower due to reflow but reflects what the user sees.
 
 
 
 ## Query Selectors and Tag Selectors
- `The document.querySelector`: Can get classes, id's and even html elements by tag names but gets only the first matching element.
- `document.querySelectorAll`: gets all the matching elements.
- `document.getElementsByTagName`: gets the element with the given tagName(descendents). 
- `document.getElementByClassName` :gets all descendants of the matching classes.
- Innerhtml--changes the content of the inner html but advised not to used.


 ## Accessing the DOM nodes :leaves:
 - `childnodes`- array of all the child elements of a parentnode.
 - `firstchild`, `lastchild` -- gets the firstChild and the lastchild of given element, if no child, returns null
 - `previousSibling`,`nextSibling`--returns previous element and next DOM element respectively.
 - `removeChild`-Removes a child Dom element from the DOM
 - `appendChild`- adds a new child element to the DOM.
 
 ##     The Problems with Line Breaks: :warning:
 - `childNodes` fetches the linebreaks also if it exsists among the child nodes.
 - `children` only fetches the child nodes within the parent node.
   use  firstElementChild
- `firstChild` also can potentially give a text node(linebreak) as value.
- use `firstElementChild` instead.
- Similarly for `lastChild` and `lastElementChild`
-`nextSibling` for `nextElementSibling`.
-`previousSibling` and `previousElementSibling`

## Creating New Elements using DOM
-`let createdDiv= document.createElement('div')`-- creates a new div element.
- To add class-- `createdDiv.className='hello'`--will add a class of hello.
-createdDiv.id='createdId'
-`setAttribute` `createdDiv.setAttribute('title','hello-div')` sets the attribute of createdDiv as title with value hello-div.
- TO add text to the div. first create the text, `let textNode=document.createTextNode('This is text')
createdDiv.appendChild(textNode);
- Note: :exclamation: you have to insert it into the DOM to show up on th screen.
insertBefore, insertAfter can be used.
`


# 🌟 Event Bubbling & Capturing


```markdown

## Overview
- **🔽 Event Capturing (Trickling Down)**: The event is first captured by the outermost element and propagated to the element where the event is triggered.
- **🔼 Event Bubbling (Bubbling Up)**: The event starts from the innermost event triggered element and bubbles up to the outermost element.

## 🛠️ Example Structure
```html
<div id="grandparent">
    <div id="parent">
        <div id="child"></div>
    </div>
</div>
```

### 🔄 Event Flow

1. **🔽 Capturing Phase (Trickling Down)**:
    - The event is first captured by the `#grandparent` div.
    - Then it is passed down to the `#parent` div.
    - Finally, it reaches the `#child` div.

2. **🔼 Bubbling Phase (Bubbling Up)**:
    - The event is triggered in the `#child` div.
    - It bubbles up to the `#parent` div.
    - Finally, it reaches the `#grandparent` div.

## 📝 Event Listener with `useCapture`

```javascript
element.addEventListener('click', () => {
    // Your code here
}, useCapture);
```

- `useCapture`: A boolean value.
  - **✅ true**: The event handler is executed in the capturing phase.
  - **❌ false**: The event handler is executed in the bubbling phase.


## Conclusion
The DOM is vital for web interactivity. It allows JavaScript to dynamically 
manipulate content, respond to user actions, and enhance user experience. A deep understanding of the DOM is essential for modern web development.

### Author
Vishal-Anthony&copy;2024