# Front End development using React
Based on the course at [Fullstack Open](https://fullstackopen.com/en/)





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




