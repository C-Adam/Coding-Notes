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

<!--Then to access these sections, create a nav element (usually at the top of the body)-->
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

## Link a phone number to directly call

```Html
<!--Using "tel:PhoneNumber"-->
<a href="tel:+12424334663">Call me at:</a>
```

## To make a link open in a new tab, use the following:

```Html
<!--The "target="_blank" attribute makes the link open a new tab-->
<a href="https://www.google.com" target="_blank">Google</a>
```

## Adding images:

```Html
<img src="images/Plane.png" alt="A cool plane!" title="A cool plane!">
```

## Loading WebPages

Use the <loading="lazy"> attribute on images that are not initially seen on the webpage. This improves loading time and provides optimization. With the lazy attribute, the image will only load once the user's scroll bar is near the image.

## Text with a drop down:

```Html
<!--Anything under the summary within the details element will be displayed once the dropdown arrow is clicked.-->
    <details>
        <summary>Hello</summary>
        <a href="https://www.google.com" target="_blank">Google</a>
    </details>
```

## Tables:

```Html
    <table>
        <caption>My Daily Schedule</caption>
        <thead> <!--thead, tbody (found below) and tfoot are simply semantic and assist with code organization and screen reading.-->
            <th>Time</th>
            <th>Activity</th>
        </thead>
        <tbody>
            <tr>
                <td><time datetime="08:00">8am</time> - <time datetime="12:00">12pm</time></td>
                <td>Study</td>
            </tr>
            <tr>
                <td><time datetime="13:00">1pm</time> - <time datetime="15:00">3pm</time></td>
                <td>Reading</td>
            </tr>
            <tr>
                <td rowspan="2">All other times</td>
                <td>Free time</td>
            </tr>
            <tr>
                <td>Sleep</td>
            </tr>
        </tbody>
    </table>

<!--To add borders around the table, that requires CSS, find the CSS code below-->
```

```CSS
table,
tr,
th,
td,
caption {
  border: 1px, solid;
  font-family: "Courier New", Courier, monospace;
  border-collapse: collapse;
  border-color: white;
  padding: 0.5rem;
}
```

## Sections vs Articles:

This is purely semantic however, sections should be used to divide different groups of content while the article element should be treated as the main holder of information that are related to each other (which can be divided with sections).

For example:

```Html
<article>
    <h1>People</h1>
    <p>text about people</p>
    <section>
        <h1>fat people</h1>
        <p>text about fat people</p>
    </section>
    <section>
        <h1>skinny people</p>
        <p>text about skinny people</p>
    </section>
</article>
<article>
    <h1>Cars</h1>
    <p>text about cars</p>
    <section>
        <h1>Fast Cars</h1>
        <p>text about fast cars</p>
    </section>
</article>
```

## Getting user input:

```Html

<!--Some attributes are optional such as: autocomplete, required, autofocus, and placeholder -->
<!--The autocomplete attribute is not supported for type="password"-->

<form action="https://httpbin.org/get" method="get">
    <fieldset> <!--Puts a box/border around everything within the element-->
        <legend>Personal Information</legend> <!--A title at the top of the fieldset border-->

        <p><!--Wrapping the contents in a paragraph allows there to be white space. div can also be used as an alternative-->
            <label for="firstName">First Name:</label>
            <input type="text" id="firstName" name="firstName" placeholder="Enter your first name here" autocomplete="on" required autofocus>
        </p>
</form>

<!--type="tel" adds ease to the website for a user because when a mobile user is filling out the form, a number keypad will be displayed instead of an alphabetical one.-->
<form action="https://httpbin.org/get" method="get">
    <label for="phoneNumber">Phone Number:</label>
    <input type="tel" id="phoneNumber" name="phoneNumber" placeholder="Enter your phone number here"
        pattern="[0-9]{3}[0-9]{3}[0-9]{4}">
    </p>
</form>

<!--This creates a drop down box that allows a value to be selected.-->
<form action="https://httpbin.org/get" method="get">
 <p>
    <label for="coffee">Favorite Coffee</label>
    <select name="coffee" id="coffee">
        <optgroup label="Coffees"> <!--Option group puts a bold title above the options within the selection box (is not selectable)-->
            <option value="regularCoffee">Regular Coffee</option>
            <option value="blackCoffee">Black Coffee</option>
            <option value="icedCoffee">Iced Coffee</option>
        </optgroup>
        <optgroup label="Espresso Drinks">
            <option value="latte">Latte</option>
            <option value="other" selected>Other</option>
        </optgroup>
    </select>
</p>
</form>

<!--This also creates a selection box however the user is able to type an input and it the selection list will autocomplete. Additionally, the list items can have descriptions with them-->
<p>
    <label for="coffee">Favorite Coffee:</label>
    <input type="text" id="coffee" name="coffee" , list="coffeeList">
    <datalist id="coffeeList">
        <option value="coffee">A delicious drink</option> <!--The text within the option elements will be the description and the value will be the title. (The title becomes bold)-->
        <option value="latte"></option>
        <option value="espresso"></option>
        <option value="cortado"></option>
        <option value="americano"></option>
    </datalist>
</p>

```

## Buttons

```Html
<form action="https://httpbin.org/get" method="get">
    <button type="submit">Submit</button>
    <button type="reset">Reset</button>
    <button type="submit" formaction="https://httpbin.org/post" formmethod="post">Post</button> <!--This is important because, although the form method is "get", this button overrides the method to "post". This is important because in a get request, all of the private information will be displayed in the URL while in a post request, the information stays hidden-->
</form>
```
