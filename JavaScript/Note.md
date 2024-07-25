## Always use strict mode, it helps to catch errors

```JavaScript
"use strict";
```

```JavaScript
console.log() //print
```

## use const when variable not supposed to change and let when it will change

## Template Literals

```JavaScript
//Encase string with ` ` to use template literals
//Use ${variable name} to insert variables in the string
const adam_new = `I'm from ${country}, which is in ${contient}`
```

## Type conversion

```JavaScript
const my_number = "1"
console.log(my_number + 1) //Would print 11
console.log(Number(my_number) + 1) //Would print 2
console.log(String(0)) //Would print "0"
```

## === vs ==

```JavaScript
 18 === 18 // --> true
 18 === "18" // --> false
 18 == "18" // --> true
 //== does type coercion
```

## Use prompt to get user input (appears in a similar box to alert)

```JavaScript
const favorite_number = Number(prompt(`What's your favorite number?`))

if (favorite_number > 1){
    console.log(`Is greater than 1`)
}else{
    console.log(`Is not greater than 1`)
}
```

## Logical operators

```JavaScript
// && --> and
// || --> or
// !{boolean} --> not
```

## Switch Statement, another form of if/else statement

```JavaScript
const day = "Monday";

switch (day) {
    case "Monday":
        console.log("The day is Monday");
        break;
    case "Tuesday":
        console.log("The day is Tuesday");
        break;
    case "Wednesday":
    case "Thursday":
        console.log("The day is either Wednesday or Thursday");
        break;
    case "Friday":
        console.log("The day is Friday");
        break;
    case "Saturday":
    case "Sunday":
        console.log("It is either Saturday or Sunday");
        break;
    default:
        console.log("No day of the week was entered!");
        break;
}
```

## Ternary Operator - For quick if else checking, use ? after the expression then [code to run if true] : [code to run if false]

```JavaScript
const age = 24

age >= 18 ? console.log("Adult") : console.log("Child")
```

## Array Methods:

```JavaScript
array.push(item) //adds the item next to the last index in the array AND returns the new length of the array if stored in a variable.
array.unshift(item) //adds the item to the first index in the array AND returns the new length of the array if stored in a variable.
array.shift(item) //removes the first index of the array and returns the value if stored in a variable.
array.pop() //removes the last index of the array and returns the value if stored in a variable.
array.indexOf(item) //returns index of the item.
array.includes(item) //returns a boolean whether the item was found within the array.
```

## Dictionary:

```JavaScript
const adam = {
    first_name: "Adam",
    last_name: "Cooper",
}
```

## To reference HTML elements via JS, use:

```JavaScript
document.querySelector(".class"/"#id")
```

## Scoping

![Presentation explaining JavaScript Scopes (See JS_Scoping.PNG)](JS_Scoping.png)

## This Keyword

Using "this" in a method:
![Presentation explaining the "this" keyword in JS (See this_keyword_method_example.PNG)](this_keyword_method_example.PNG)

All Uses:

![Presentation explaining the "this" keyword in JS (See uses_of_this_keyword.PNG)](uses_of_this_keyword.PNG)

## Shallow cloning an object (deeply nested )