# JavaScript DOM & Event Handling
 This README explains some important concepts of working with the DOM (Document Object
 Model) and events in JavaScript. I wrote it in a simple way, based on what I’ve learned and
 understood.--

 ### 1. Difference between getElementById, getElementsByClassName, and querySelector /
 querySelectorAll-
 **getElementById("id")** - Returns a single element that matches the given ID. - IDs should be
 unique in the page.
 **getElementsByClassName("class")** - Returns a live HTMLCollection of all elements with that
 class. - “Live” means if the DOM changes, the collection updates automatically.
 **querySelector("selector")** - Returns the first element that matches a CSS selector. - Very
 flexible because you can use IDs, classes, attributes, etc.
 **querySelectorAll("selector")** - Returns a NodeList (not live) of all matching elements.
 **In short:** - Use getElementById when you know the unique ID. - Use getElementsByClassName
 for multiple elements with the same class. - Use querySelector / querySelectorAll for more flexibility
 with CSS selectors.

 
### 2. How to create and insert a new element into the DOM
 Steps: 1. Create the element ```javascript const newDiv = document.createElement("div"); ```
 2. Add content or attributes ```javascript newDiv.textContent = "Hello World!"; newDiv.className =
 "greeting"; ```
 3. Insert into the DOM - Append as last child: ```javascript document.body.appendChild(newDiv); ```- Insert before a specific element: ```javascript const parent =
 document.getElementById("container"); const ref = document.getElementById("reference");
 parent.insertBefore(newDiv, ref); ```

 
### 3. What is Event Bubbling and how does it work?
 Event bubbling means when you trigger an event on a child element, the event automatically
 "bubbles up” to its parent, then to the parent’s parent, and so on until it reaches the root
 (document).
 Example: Clicking a button inside a div will trigger both the button’s click event and the div’s click
 event.

 
### 4. What is Event Delegation in JavaScript? Why is it useful?
Event delegation is a technique where instead of adding event listeners to many child elements,
you add one event listener to the parent, and use the event’s target to figure out which child was clicked.
Why useful? - You don’t need to attach separate listeners to each child. - Works even if new 
elements are added later. - Improves performance by reducing number of listeners.

 
### 5. Difference between preventDefault() and stopPropagation()- 
**preventDefault()** - Stops the default browser behavior. - Example: prevent a form from
 submitting.
**stopPropagation()** - Stops the event from bubbling up to parent elements.
