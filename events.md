Why we need events? 
A. To perform any action in our web page, 
B. User Interaction 
C. To submit anything
D. functionalities(multiple event handlers):- Attach multiple actions to the same element for different events or even the same event.
E. Dynamic Behaviour:- Modern web applications heavily rely on dynamic behavior for an engaging user experience. Using addEventListener enables developers to respond to user actions programmatically
F. Separation of Concerns:- With addEventListener, JavaScript logic is kept separate from HTML, leading to cleaner and more maintainable code.
Inline handlers like onclick="..." mix behavior with structure, making the code harder to manage.
G. Advanced Features like Supports options like:
1.Event capturing and bubbling: Decide the flow of events.
2.Once-only execution: Run an event handler only once.
3.Passive listeners: Optimize performance for events like scrolling.
------------------------------------------------------------------------------------------------
What is an event? 
A. A function that is called when a certain action occurs IN OUR WEB PAGE often triggered by user interactions like clicking a button, hovering over an element, typing in a field, or even system-generated events like page loading or network updates.

------------------------------------------------------------------------------------------------
Where to Use addEventListener?
addEventListener can be used on any DOM element where interaction is required:

Buttons: To trigger form submissions, modals, or navigation.
Forms: To validate user inputs.
Lists or Tables: To add dynamic filtering or sorting.
Media Elements: To handle play, pause, or volume controls.
Mouse or Keyboard Events: For custom navigation or shortcuts.
Window Events: For tracking resizing, scrolling, or detecting device orientation.
-----------------------------------------------------------------------------------------------
Understanding addEventListener:- 
Syntax:- `${element.addEventListener(event, listener, options)}`;
1.event: A string representing the name of the event, e.g., 'click', 'keydown', 'mouseover'.
2.listener: The function to be executed when the event occurs.
3.options (optional): Additional configuration options (details below).

Basic Example:- 
<button id="myButton">Click Me</button>  //html
<script>  //js
    const button = document.getElementById("myButton"); //selecting an element

    // Add an event listener to handle click events
    button.addEventListener("click", () => {  //event type: click, listener:- function
        alert("Button was clicked!");
    });
</script>
-----------------------------------------------------------------------------------------------
Features of addEventListener
1. Advanced Event Handling:- Multiple Event Listeners, Unlike inline handlers, you can attach multiple listeners to the same element:

Example:- 
const button = document.querySelector("#myButton");

button.addEventListener("click", () => console.log("Listener 1"));
button.addEventListener("click", () => console.log("Listener 2"));

Output on click:
Listener 1
Listener 2
------------------------------------------------------------------------------------------------
Accessing the Event Object:- Every event provides an event object with information about the event, such as:

Target element (event.target)
Event type (event.type)
Mouse coordinates (event.clientX, event.clientY)
Example:
button.addEventListener("click", (event) => {
    console.log(`Clicked element: ${event.target.tagName}`);
});
------------------------------------------------------------------------------------------------
Event Flow: Bubbling and Capturing
Events propagate in two phases:

Capturing Phase: From the document root to the target element.
Bubbling Phase: From the target element back to the document root.
Control propagation using the capture option:

const parent = document.getElementById("parent");
const child = document.getElementById("child");

parent.addEventListener("click",() => console.log("Parent Clicked! (Capturing Phase)"), true);

child.addEventListener("click", () => console.log("Child Clicked!"));
------------------------------------------------------------------------------------------------
4. One-Time Event Handling:- Use the once option to execute a listener only once:

button.addEventListener(
    "click",
    () => console.log("This runs only once"),
    { once: true }
);
------------------------------------------------------------------------------------------------
Removing Event Listeners
Event listeners can be removed using removeEventListener.
Note: The function must be declared separately for removal to work.

const logClick = () => console.log("Clicked!");
button.addEventListener("click", logClick);
button.removeEventListener("click", logClick);
------------------------------------------------------------------------------------------------
Types:- 
scroll, keyboard, touch, mouse, drag drop, window events, 

click, submit, onmousehover, ondragover, ondragstart, ondragend
, focus, onkeypress, onkeyup, onkeydown

how ? 

<!-- <button onclick="alert(you clicked me)">Click me!</button>

const btn = d.gebtg("button)

btn.addeventlisteners(click, ()=>{alert("you clicked me")}) -->
const container = document.getElementById("container");
 <div id="container">
        <button id="btn1">Button 1</button>
        <button id="btn2">Button 2</button>
    </div>
        // Event delegation
        container.addEventListener("click", (event) => {
            console.log(event)
            if (event.target.tagName === "BUTTON") {
                alert(`${event.target.textContent} was clicked!`);
            }
        })