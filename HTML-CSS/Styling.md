### All content goes in the body.
```Html
<body>
    <h1>This is a test</h1>
    <p>Another Test</p>
</body>
```
### All settings, title, link, etc goes in the head:
```Html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="Style.css">
    <title>Learning HTML & CSS</title>
</head>
```

### Use div to create empty boxes that contain content
```Html
<div>
    <h1>Will be shown in an invisible box that can be manipulated</h1>
</div>
```

### Use form to create an empty box that takes in an input
```Html
<form id="your_name">
    <h2>Your name here</h2>
    <p class="first">Please fill in this form</p>
    <input type="text" placeholder="Your name">
    <button>Ok!</button>
</form>
```

### Id's can only be used once (another id cannot have the same name); Use classes for multiple objects and id's for single objects


### CSS Box Model
![alt text](CSS_Box_Model.PNG)

### Use *{} to modify all elements on a page
```CSS
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /*Always use border-box because it allows the width to be unaffected by padding*/
}
```

### Use .classname to access classes in css
```CSS
.first {
    color: blue;
}
```

### Use #idname to access id's
```CSS
#your_name {
    background-color: orange;
    border: 5px solid #444;
}
```

### Use p{} to mofidy all paragraph elements on the page
```CSS
p {
    margin-bottom: 20px;
}
```

### Use a{} to modify all hyperlinks
```CSS
a {
    background-color: yellowgreen;
}
```
### Selecting child classes/ids/objects (call the parent (#your_name) then the child (h2))
```CSS
#your_name h2 {
    color: olivedrab;
}
``` 

### console.log() to print in the console.

