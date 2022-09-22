# Front End development using React
Based on the course at [Fullstack Open](https://fullstackopen.com/en/)

## Go

- [Fundamentals of Web App](./react.md/#fundamentals-of-web-app)
- [React frontend basics](./react.md/#react)
- [Map, Reduce, Functional Programming](./react.md/#map,-reduce)


- [React docs](https://reactjs.org/docs/getting-started.html)
- [React Developer Tools (Extension)](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
- [JSONvue](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc)

## Fundamentals of Web App

ctrl + shift + i for developer tools.

### Success codes
- a GET request gets info from the page (OK 200)
- a POST request adds info (Created 201)
- a PUT request is used to update info (Created 201)
- a DELETE request is used to delete info (No Content 204)

### Failure codes
- code 400 => bad request
- code 404 => unknown ending/ data not found

### HTML

```html
<!DOCTYPE html> #required
<html lang="en-US">
  <head>
    <meta charset="utf-8" /> #helpful
    <meta name="viewport" content="width=device-width" /> #for mobile devices auto resize
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image" />
    <h1>Heading</h1>
    <ul>
      <li>Unordered lists</li>
    </ul>
    
    <ol>
      <li>Ordered lists</li>
    </ol>
    <a href="hyperlink.com">Hyperlink</a>
  </body>
</html>
```

#### Difference between href and src
for hyperlink and such stuff where the user needs a reference a url href is used.
for scripts/ images where user does not need the url src is used.

### CSS

```css
p { /*element selector*/
  color: red;
  width: 500px;
  border: 1px solid black;
}

#45 { /* id selector */
  color: brown;
}

.home { /* class selector (use )*/
  width: 600px;
}

img[src] { /* attribute selector selects elements that have a specific attribute (egs src)*/
  border: 5px solid black;
}
```

### HTML forms

```html
  <form action="/my-handling-form-page" method="post">
  <ul>
    <li>
      <label for="name">Name:</label>
      <input type="text" id="name" name="user_name" />
    </li>
    <li>
      <label for="mail">E-mail:</label>
      <input type="email" id="mail" name="user_email" />
    </li>
    <li>
      <label for="msg">Message:</label>
      <textarea id="msg" name="user_message"></textarea>
    </li>
    <li class="button">
      <button type="submit">Send your message</button>
     </li>
  </ul>
</form>
```

styling for above form
```css
form {
  /* Center the form on the page */
  margin: 0 auto;
  width: 400px;
  /* Form outline */
  padding: 1em;
  border: 1px solid #ccc;
  border-radius: 1em;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

form li + li {
  margin-top: 1em;
}

label {
  /* Uniform size & alignment */
  display: inline-block;
  width: 90px;
  text-align: right;
}

input,
textarea {
  /* To make sure that all text fields have the same font settings
     By default, textareas have a monospace font */
  font: 1em sans-serif;

  /* Uniform text field size */
  width: 300px;
  box-sizing: border-box;

  /* Match form field borders */
  border: 1px solid #999;
}

input:focus,
textarea:focus {
  /* Additional highlight for focused elements */
  border-color: #000;
}

textarea {
  /* Align multiline text fields with their labels */
  vertical-align: top;

  /* Provide space to type some text */
  height: 5em;
}

.button {
  /* Align buttons with the text fields */
  padding-left: 90px; /* same size as the label elements */
}

button {
  /* This extra margin represent roughly the same space as the space
     between the labels and their text fields */
  margin-left: 0.5em;
}
```

## React

to create a react app
```
npx create-react-app part1
cd part1
```

`npm start` to start.

Return value of a component should always be a single html element with other children elements.
We can enclose children elements in the empty element.
```
const component = () => {
  return(
    <>
    <p>This is a paragraph</p>
    <button>Click</button>
    </>
  )
}
```
Javascript stuff inside braces. Eg `{a} + {b} is {a+b} ` where a and b are variables
react is actually written in JSX which looks like HTML.

Node.js console can be open by typing `node` in the console.

### State and Event handlers in React
use `import {useState, useEffect} from 'react'` to import useState and use Effect

```javascript
const [state, setState]=useState(initState)
//setState is a function to change the value of state variable and re-render any components that use state.

useEffect(() => {
//do something
},
[state])
/* useEffect executes the given function anytime a state in the given array changes or one time 
after the entire app renders if the array is empty or continuously loops and renders the app if 
no second argument is given */
```

#### Timeout
Use `setTimeout(func, time)` to execute a function `func` after `time` in milliseconds.
setTimeout returns an Object that can be stored. This object can be used to cancel a timeout function. For example
```javascript
const newTimeout = setTimeout(()=>{
// do something
},
5000) // in 5 seconds

// other code
// oh no turns out you have to cancel the timeout
clearTimeout(newTimeout)
```
you can pass **Event Handlers** (functions) to attrbutes like onClick of a button or any other element.

Do not use the useEffect or useState function (ie. the initialising statements) in loops, conditional statements or functions or any where else that does not define a component. The useState and useEffect functions must always be called in the same order when rendering the components. So don't use them inside conditionals or loops or functions that may/may not be called conditionally.

Do not define components within other components.

### Debugging React Applications
Use console.logs
keep the developer console open (ctrl-shift-i)

use console debugger by writting command
```javascript
//code
debugger
//code
```
Anywhere in your code
Go to console tab to inspect current state of variables.

[React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
is a highly recommended extension.
[VueJSON](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) is also recommended.

### Rendering Collections
We can use map function to return an array of React components
Eg.
```javascript
const App = (props) => {
  const { notes } = props

  return (
    <div>
      <h1>Notes</h1>
      <ul>
        {notes.map(note => 
          <li key = {note.id}>
            {note.content}
          </li>
        )}
      </ul>
    </div>
  )
}
```

Try not to use array index as a key because it may create ambiguities for react.

## Map, Reduce

Check out functional programming

- [Higher order functions](https://www.youtube.com/watch?v=BMUiFMZr7vk&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)
- [Map](https://www.youtube.com/watch?v=bCqtb-Z5YGQ&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84&index=2)
- [Reduce basics](https://www.youtube.com/watch?v=Wl98eZpkp-c&t=31s)
