# DOM

1. What is DOM?
DOM (Document Object Model): A tree-like, structured representation of the HTML (or XML) document in memory that can be accessed and manipulated programmatically.
It is a Browser Web API, not part of js. However,   can interact with it via browser-provided interfaces.

2. How Does the DOM Work with HTML, CSS, and  ?
HTML: Provides the structure of the document (the DOM is based on this).
CSS: Defines the presentation layer, modifying the visual appearance of DOM elements.
 : The programming layer that dynamically manipulates the DOM by adding, updating, and removing elements or styles.

3. Relationship Between DOM,  , and Browser
The DOM is not  .
The browser engine (e.g., Blink, Gecko) implements the DOM as part of its Web APIs.
  interacts with the DOM by using these APIs.
Interaction between   and DOM happens through:
Call Stack: Executes   code.
Web APIs: DOM is accessed asynchronously via these APIs.
Event Loop and Task Queue: Manages asynchronous DOM updates.
How the DOM Works in the Browser:
Parser reads the HTML source code.
Tokenization: Splits code into tokens (tags, attributes, etc.).
Tree Representation: HTML is converted into a DOM Tree (nodes).
The CSSOM Tree (CSS Object Model) is built simultaneously.
Render Tree: Combines DOM + CSSOM to produce what you see on the screen.

4. Is the DOM Synchronous or Asynchronous?
The DOM is asynchronous because:
While   is single-threaded and synchronous (Call Stack), the browser processes DOM operations in the background via Web APIs.
Example: DOM events, animations, and fetching data are handled asynchronously.
Example of Async Processing:
console.log('Before DOM Update');
document.getElementById('content').textContent = 'Updated Content';
console.log('After DOM Update');
Even though textContent is set in code, rendering happens later due to the Event Loop.

5. DOM Parsing in Detail
HTML Parser:
Converts HTML source code into DOM.
Builds a tree structure node-by-node.
Tokenization:
Breaks down the code:
Tags → Element Nodes.
Text → Text Nodes.
Attributes → Attribute Nodes.
Building DOM Tree:
Parent-child relationships are established.
Example: <div><p>Text</p></div> becomes:
css
 
<div>
  <p>
    Text
6. DOM Tree Representation
The DOM Tree represents the document as nodes:

Root Node: Document object.
Element Nodes: HTML tags (e.g., <div>, <p>).
Text Nodes: Content inside elements (e.g., "Hello World").
Attribute Nodes: Attributes of elements (e.g., class, id).
Comment Nodes: HTML comments.
Example Tree:
html
 
<div id="root">
  <h1>Hello</h1>
  <p>World</p>
</div>
DOM Tree:

mathematica
 
Document
 └── Element: <div id="root">
      ├── Element: <h1>
      │    └── Text: "Hello"
      └── Element: <p>
           └── Text: "World"

7. Core DOM Properties and Methods
The DOM provides various properties and methods to interact with the document structure programmatically.

7.1. Core Properties
1. document Object
Entry point to interact with the DOM.
Properties:

document.title: Access or modify the title of the document.
 
 
console.log(document.title); // Get the current title
document.title = 'New Title'; // Change the title
document.URL: Retrieve the current page URL.
 
 
console.log(document.URL); // Outputs: http://example.com
document.body: Access the <body> element.
 
 
document.body.style.backgroundColor = 'lightblue'; // Change background color
2. Node Properties
Nodes are the fundamental units of the DOM tree.
Common Node Properties:

nodeName: Returns the name of the node (e.g., DIV, TEXT).
 
 
console.log(document.body.nodeName); // Outputs: BODY
nodeType: Identifies the type of node.
1: Element Node.
3: Text Node.
8: Comment Node.
 
 
const node = document.getElementById('example');
console.log(node.nodeType); // Outputs: 1 for Element Node
textContent: Retrieves or sets the text within a node.
 
 
const para = document.querySelector('p');
console.log(para.textContent); // Get text
para.textContent = 'Updated Text'; // Modify text
3. Element Properties
These properties are specific to element nodes.
Examples:

id and className: Access id or class attributes.
 
 
const element = document.querySelector('div');
console.log(element.id); // Get ID
element.id = 'newId'; // Set a new ID
style: Inline styling of elements.
 
 
element.style.color = 'red'; // Change text color
element.style.fontSize = '20px'; // Set font size
innerHTML: Access or set the inner content (includes HTML tags).
 
 
console.log(element.innerHTML); // Get inner content
element.innerHTML = '<strong>New Content</strong>'; // Modify inner content
7.2. Methods to Access Elements
1. document.getElementById()
Access an element by its id.
 
 
const header = document.getElementById('header');
header.style.textAlign = 'center'; // Center align the header
2. document.getElementsByClassName()
Access elements by their class name (returns a live collection).
 
 
const items = document.getElementsByClassName('item');
items[0].style.backgroundColor = 'yellow'; // Modify first item
3. document.getElementsByTagName()
Access elements by their tag name (returns a live collection).
 
 
const paragraphs = document.getElementsByTagName('p');
for (const para of paragraphs) {
    para.style.color = 'blue'; // Set all paragraphs' text to blue
}
4. document.querySelector()
Access the first element that matches a CSS selector.
 
 
const firstDiv = document.querySelector('div');
firstDiv.style.border = '1px solid black'; // Add border
5. document.querySelectorAll()
Access all elements that match a CSS selector (returns a static NodeList).
 
 
const allDivs = document.querySelectorAll('div');
allDivs.forEach(div => div.style.padding = '10px'); // Apply padding to all divs
8. DOM Traversal and Manipulation
DOM Traversal allows you to navigate through parent, child, and sibling nodes. Manipulation lets you dynamically modify these nodes.

8.1. Traversing Nodes
1. Parent Nodes
Access the parent node using parentNode or parentElement.
 
 
const child = document.querySelector('#child');
console.log(child.parentNode); // Outputs: Parent Node
2. Child Nodes
Access child nodes using childNodes or children.
 
 
const parent = document.querySelector('#parent');
console.log(parent.childNodes); // Includes text, comments, and element nodes
console.log(parent.children); // Only element nodes
3. Sibling Nodes
Navigate between siblings using nextSibling or previousSibling.
 
 
const item = document.querySelector('.item');
console.log(item.nextSibling); // Access the next sibling
console.log(item.previousSibling); // Access the previous sibling
8.2. Adding and Removing Nodes
1. Create New Nodes
Use createElement() to create new elements.
 
 
const newDiv = document.createElement('div');
newDiv.textContent = 'I am a new div!';
document.body.appendChild(newDiv); // Add to DOM
2. Insert Elements
Use appendChild() or insertBefore().
 
 
const list = document.getElementById('list');
const newItem = document.createElement('li');
newItem.textContent = 'New Item';
list.appendChild(newItem); // Add at the end
3. Remove Elements
Use removeChild() or remove().
 
 
const item = document.getElementById('item');
item.remove(); // Remove directly
8.3. Modifying Nodes
1. Update Content
 
 
const heading = document.getElementById('heading');
heading.textContent = 'Updated Heading'; // Change text
heading.innerHTML = '<em>Updated Content</em>'; // Add HTML
2. Modify Attributes
 
 
const link = document.querySelector('a');
link.setAttribute('href', 'https://example.com'); // Set new URL
link.getAttribute('href'); // Retrieve URL
3. Update Styles Dynamically
 
 
const button = document.getElementById('btn');
button.style.backgroundColor = 'green';
button.style.padding = '10px';
8.4. Nodes: Adding, Deleting, and Replacing
Add Child Nodes
 
 
const container = document.getElementById('container');
const newPara = document.createElement('p');
newPara.textContent = 'This is a new paragraph.';
container.appendChild(newPara);
Remove Nodes
 
 
const oldPara = document.querySelector('.old');
oldPara.remove();
Replace Nodes
 
 
const newHeading = document.createElement('h2');
newHeading.textContent = 'New Heading';
const oldHeading = document.querySelector('h1');
oldHeading.parentNode.replaceChild(newHeading, oldHeading);
9. Events and DOM Interaction
Events are actions that occur in the browser (e.g., clicks, keypresses). The DOM provides methods to bind and handle events.

9.1. Event Binding
Use addEventListener() to bind an event.
 
 
const btn = document.getElementById('btn');
btn.addEventListener('click', () => {
    alert('Button clicked!');
});
9.2. Common Events
click: Triggered when an element is clicked.
mouseover: Triggered when hovering over an element.
keydown: Triggered when a key is pressed.
