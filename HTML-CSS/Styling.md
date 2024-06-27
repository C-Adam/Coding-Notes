## All content goes in the body.

```Html
<body>
    <h1>This is a test</h1>
    <p>Another Test</p>
</body>
```

## All settings, title, link, etc goes in the head:

```Html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="Style.css"> <!--stylesheet is for the css settings created for the web page.-->
    <title>Learning HTML & CSS</title>
</head>
```

## Use div to create empty boxes that contain content

```Html
<div>
    <h1>Will be shown in an invisible box that can be manipulated</h1>
</div>
```

## Use form to create an empty box that takes in an input

```Html
<form id="your_name">
    <h2>Your name here</h2>
    <p class="first">Please fill in this form</p>
    <input type="text" placeholder="Your name">
    <button>Ok!</button>
</form>
```

## Id's can only be used once (another id cannot have the same name); Use classes for multiple objects and id's for single objects

## CSS Box Model

![alt text](CSS_Box_Model.PNG)

## Use \*{} to modify all elements on a page

```CSS
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /*Always use border-box because it allows the width to be unaffected by padding*/
}
```

## Use .classname to access classes in css

```CSS
.first {
    color: blue;
}
```

## Use #idname to access id's

```CSS
#your_name {
    background-color: orange;
    border: 5px solid #444;
}
```

## Use p{} to mofidy all paragraph elements on the page

```CSS
p {
    margin-bottom: 20px;
}
```

## Use a{} to modify all hyperlinks

```CSS
a {
    background-color: yellowgreen;
}
```

## Selecting child classes/ids/objects (call the parent (#your_name) then the child (h2))

```CSS
#your_name h2 {
    color: olivedrab;
}
```

## Use the w3c validator website to check html code for errors

## Italicize/Bold text for screen readers. Real styling should be done with CSS however this is important for screen readers.

```Html
<em>Hello World</em> <!--Italics-->
<strong>Goodbye World</strong><!--Bold-->
```

## Can show full meaning of abbreviations with:

```Html
<abbr title="Adam Paul Cooper">APC</abbr>
```

## For italics and screen readability, when adding an address/location, use the following:

```Html
<address>One Casino Drive, Suite 41, Paradise Island, Bahamas.</address>
```

## Ordered/Unordered/Description list:

```Html
<ol>
    <li>This is #1</li>
    <li>This is #2</li>
    <li>This is #3</li>
</ol>

<ul>
    <li>This is #1</li>
    <li>This is #2</li>
    <li>This is #3</li>
</ul>

<dl>
    <dt>North Pole</dt> <!--Description Term-->
    <dd>This is a very cold place</dd> <!--Description for the term above. This text is directly under the description term and indented.-->
</dl>

```

## Creating links (absolute reference aka linking to another website through the server https)

```Html
<a href="https://www.youtube.com/">YouTube</a>
```

## Linking to another local website file (relative reference)

```Html
<a href="about.html">Click this to read my About Me!</a>
```

## Linking to another location on the current web page (internal reference)

```Html
<!--First create sections which must have id's to be referenced to-->
<section id="First">
    <p>This is the first section</p>
</section>

<section id="Second">
    <p>This is the second section</p>
</section>

<!--Then to access these sections, create a nav element-->
<nav>
    <a href="#First">First</a>
    <br>
    <a href="#Second">Second</a>
</nav>

<!--Note, to take the user back to the top of the page, use the following-->
<a href="#">Back to Top</a>
```

## Download files via links:

```Html
<!--The download attribute in the a element is what actually makes the file downloadable-->
 <a href="pengu.jpg" download="intended file name here">Download a cool picture of a penguin!</a>
```

## Link to an email:

```Html
 <a href="mailto:adamcooper427@gmail.com">Contact me at:</a>
```
