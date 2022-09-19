# Front End development using React
Based on the course at [Fullstack Open](https://fullstackopen.com/en/)

## Go

[Fundamentals of Web App]()



## Fundamentals of Web App

ctrl + shift + i for developer tools.

a GET request gets info from the page (OK 200)

a POST request adds info (Created 201)

a PUT request is used to update info (Created 201)

a DELETE request is used to delete info (No Content 204)

code 400 => bad request

code 404 => unknown ending/ data not found

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
`npm start` to start

Return value of a component should always be a single html element with other children elements.
We can enclose children elements in the empty element
```
const component = () => {
  return(
    <>
    <p>This is a paragraph</p>
    <button>Click</button>
    </>
  )
}





