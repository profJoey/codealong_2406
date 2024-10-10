# Teaching Guide

## 1. Introduction to JavaScript Functions and Events

### Concepts:

**Javascript:**
1. Programming language used to make websites interactive
2. Can do things like: respond to user actions, update content on page, make websites dynamic
3. It runs directly in the web browser (server-side programming).

> Two ways to add javascript to your html document:

```html
<!-- inline -->
<script>
    // javascript goes here
</script>
```

```html
<!-- external -->
<script src="script.js" defer></script>
```

> External is best practice; seperation of concerns

**Events:**
1. action or occurrence that happens in the browser
2. ex: user clicking a button, typing in a form, loading a page
3. When events happen, you can use JavaScript to make the webpage respond to them.

```html
<!-- add onclick property-->
<button onclick="addItem()">Add Item</button>
```

> `onclick` is a property we can define on an html elements to add an event handler

**Function:**

To do something with the event, we need a function

1. Reusable block of code that performs a specific task
2. Define once, then "call" or "run" it whenever needed 


```javascript
// Function runs when button is clicked.
function addItem() {
    console.log('item added!');
}
```

### Explaination

1. `function` keyword starts the function `addItem()`

2. `addItem` is the name of the function

3. `()` parentheses can hold parameters (none in this case)

4. `{}` curly braces encloses the code to run when the function is called

> to use the function, you "call" it like this:

```javascript
addItem();
```

> The `onclick` property is calling the function

```html
<button onclick="addItem()">Add Item</button>
```

## 2. Variables

**Variables**:
1. It's like a container that stores a value
2. You can think of it as a box with a label
3. inside the box you can store information, like a number or a word
4. The variable makes retrieving the information easier / efficient
5. Three ways to create variables: `let`, `const`, and `var`
6. `let`: variable that can change
7. `const`: variable that cannot change
8. `var`: older version of let, but not as commonly used today

```javascript
function addItem() {
    // Using a variable to store the input value
    const input = document.getElementById('itemInput');
}
```

### Explaination

1. Enter text in the input field
2. Click the button
3. The function gets the input from the input element
4. stores the text inside a variable so we can do something with it

## 5. The DOM and Javascript Objects
Concepts: Creating, appending, and modifying DOM elements dynamically

**DOM (document object model):**
1. like a map or structure of a webpage
2. represents everything on the page (like text, images, buttons, etc.) as objects
3. objects are what javascript can interact with

```javascript
function addItem() {
    const input = document.getElementById('itemInput');
    //log the variable 'input' to see the input element as an object
}
```

**Javascript Objects:**
1. an object is like a collection of related information
2. grouped together in one container using `{}` curly braces
3. Each piece of information is stored as a property (like a label and value pair)

> We can create javascript objects of our own

```javascript
const car = {
  brand: "Toyota",
  color: "red",
  yearsOld: 10,
  features: [
    "automatic drive",
    "power windows",
    "leather seats"
  ],
  driver: {
    "name" : "joey"
    "height" : "1.7 meters": 
  }
  drive: function() {
    console.log("The car is driving");
  },
  isDriving: false
};
```

### Explaination

1. `car` is the variable
2. `{}` curly braces enclose the object
3. `brand`, `color` `yearsOld` `drive` are properties of the object
4. `Toyota`, `red` are values. They are string values
5. `10` is also a value. A number value.
6. The value of `features` is an array, like a list
7. The value of `driver` is an object. You can have objects inside objects
6. The value of `drive` is a method
7. The value of `isDriving` is a boolean
7. These are examples of different datatypes in javscript
8. We need to be mindful of datatypes so we can work with them correctly

## 6. Functions vs. Methods

### Explaination

1. Methods and functions are similar: they both do something programatically
2. A function is a standalone block of code designed to perform a specific task
3. A method is a function that is associated with an object
4. `drive()` is a method of the `car` object
5. `getElementById()` is a method of the `document` object
6. `addText()` is a function that we created


> just like we can log `car` to the console, we can log `input`

## 6. DOM Manipulation

### Concepts

1. Interacting with the DOM through JavaScript
2. DOM manipulation (creating and appending elements)

```javascript
function addItem() {
    const input = document.getElementById('itemInput');
    const li = document.createElement('li');
    li.textContent = input;
    document.getElementById('itemList').appendChild(li);
    input.value = ""; 
}
```

### Explanation:

1. Use `document.createElement()` to create new elements
2. Use `appendChild()` to add new elements to the DOM

> Food For Thought: What if you had a database of a thousand videos, and wanted to create the same html elements 1000 times? Instead of writing and editing 1000 different video elements, you can use javascript to create and update them

## 7. Conditional Statements

### Concepts

1. Conditional statements (if).
2. Comparison operators like !==
3. `==` (equal to)
4. `!=` (Not equal to)
5. `>` (Greater than)
6. `<` (Less than)
7. `>=` (Greater than or equal to)
8. `<=` (Less than or equal to)

```javascript
function addItem() {
    // If the input is not empty, proceed
    if (input !== "") {
        
        // const li = document.createElement('li');
        // li.textContent = itemText;
        // document.getElementById('itemList').appendChild(li);
        // input.value = "";
    } else {
        alert("type some text in the input field");
    }
}
```


# Optional Enhancement

## 1. Event Handlers

> Two ways to add an eventhandler: `onclick` vs `addEventListener()`

```javascript
document.querySelector('button').addEventListener('click', addItem);
```


## 2. Using Trim()

```javascript
function addItem() {
    // const input = document.getElementById('itemInput');
    const itemText = input.value.trim();

  
    if (itemText !== "") {
        
        // const li = document.createElement('li');

        li.textContent = itemText;

        // document.getElementById('itemList').appendChild(li);
        // input.value = "";
    }
}
```

### Explanation:

1. Check if the input is empty before adding it to the list.
2. Show why this step is important to avoid adding blank list items.