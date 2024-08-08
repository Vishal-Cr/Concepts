
## Javascript DOM notes :robot:

# **Examine the Document Object**

 **1. `console.dir(document);`**
- Outputs a detailed, interactive list of the properties of the `document` object.

 **2. `console.log(document.domain);`**
- Logs the domain name of the document (e.g., `"example.com"`).

 **3. `console.log(document.URL);`**
- Logs the full URL of the document (e.g., `"https://www.example.com/page"`).

 **4. `console.log(document.title);`**
- Logs the title of the document, which is set in the `<title>` tag within the `<head>` section of the HTML.

 **5. `//document.title = 123;` (Commented Out)**
- This line is commented out. If uncommented, it would set the document’s title to `123`.

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

 15. -   **`textContent`**: Retrieves all text within an element, including hidden text. Faster and simpler, but doesn't consider styling.
 -   **16.- `innerText`**: Retrieves only visible text, considering CSS styles. Slower due to reflow but reflects what the user sees.
 - 17- `The document.querySelector`: Can get classes, id's and even html elements by tag names but gets only the first matching element.
 - 18- `document.querySelectorAll`: gets all the matching elements.
 - -19- `document.getElementsByTagName`: gets the element with the given tagName(descendents). 
 - `document.getElementByClassName` :gets all descendants of the matching classes.
 - Innerhtml--changes the content of the inner html but advised not to used.
 ## Accessing the DOM nodes
 - `childnodes`- array of all the child elements of a parentnode.
 - `firstchild`, `lastchild` -- gets the firstChild and the lastchild of given element, if no child, returns null
 - `previousSibling`,`nextSibling`--returns previous element and next DOM element respectively.
 - `removeChild`-Removes a child Dom element from the DOM
 - `appendChild`- adds a new child element to the DOM.
 

    
   
   
