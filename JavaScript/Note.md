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

## Shallow cloning an object (deeply nested objects within an object are cloned however if manipulated, the original object will also be affected)

```JavaScript
const jessica = {
    firstName: "Jessica",
    lastName: "Williams",
    family: ["Alice", "Bob"] //This is an example of a deeply nested object that will be changed in both objects if manipulated.
}

const jessicaCopy = Object.assign({}, jessica); //Shallow clones the object into a blank object (jessica --> {})

jessicaCopy.lastName = "Davis"; //Will only change in the jessicaCopy object

jessicaCopy.family.push("Mary"); //Adding marry to jessica copy's family will also add it to the original jessica object.

```

## Destructuring Arrays

```JavaScript
const restaurant = {
  name: "Classico Italiano",
  location: "Via Angelo Tavanti 23, Firenze, Italy",
  categories: ["Italian", "Pizzeria", "Vegetarian", "Organic"],
  starterMenu: ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad"],
  mainMenu: ["Pizza", "Pasta", "Risotto"],

  Order: function (starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  },
}

let [main, , secondary] = restaurant.categories; //The , , means to skip an index

console.log(`Main: ${main}, Secondary: ${secondary}`); //Prints main = "Italian" and secondary = "Vegetarian"

[main, secondary] = [secondary, main]; //Switches the order from "Italian" "Vegetarian --> "Vegetarian" "Italian"

console.log(`Main: ${main}, Secondary: ${secondary}`); //Prints main = "Vegetarian" and secondary = "Italian"

const [starter, mainCourse] = restaurant.Order(2, 0); //Storing multiple returned values into an array.

console.log(starter, mainCourse); //Prints "Garlic Bread" and "Pizza"

const nested = [2, 4, [5, 6]];

const [i, , [j, k]] = nested; //Skips the four and stores the appropriate values

console.log(i, j, k); //Prints 2, 5, 6
```

## Destructuring Objects

```JavaScript
const restaurant = {
  name: "Classico Italiano",
  location: "Via Angelo Tavanti 23, Firenze, Italy",
  categories: ["Italian", "Pizzeria", "Vegetarian", "Organic"],
  starterMenu: ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad"],
  mainMenu: ["Pizza", "Pasta", "Risotto"],

  openingHours: {
    thu: {
      open: 12,
      close: 22,
    },

    fri: {
      open: 11,
      close: 23,
    },

    sat: {
      open: 0, // Open 24 hours
      close: 24,
    },
  },
};

const { name, openingHours, categories } = restaurant; //Unlike arrays, the order does not matter, the variable names should match the object's variable name.

console.log(name, openingHours, categories); //Prints "Classico Italiano", {thu: {}, fri: {}, sat: {}}, ["Italian", "Pizzeria", etc...]


const {
  name: restaurantName, //The colon after the variable name allows for re-naming so when accessing the variables, the assigned names are used.
  openingHours: hours,
  categories: tags,
} = restaurant;

console.log(restaurantName, hours, tags); //Still prints "Classico Italiano", {thu: {}, fri: {}, sat: {}}, ["Italian", "Pizzeria", etc...]

const {fri: { open, close }} = openingHours;

console.log(open, close); //Prints 11 and 23
```

## Destructuring Objects in Function Parameters

```JavaScript
//Unpacking the object using correct naming like in the example above allows for the parameter order to be ignored.

//Adding the "=" after a variable when destructuring sets the default value for that variable in the event that it cannot be destructured (for example if a value is undefined). Which means that if the starterIndex was not provided, the value of the parameter in the function would be the default value of 1.

function OrderDelivery ({ starterIndex = 1, mainIndex = 0, time, address }) {
  console.log(starterIndex);
},

OrderDelivery({ //The variables do not match the function parameters however it is still passed
  time: "22:30",
  address: "Via del Sole, 21",
  mainIndex: 2,
  starterIndex: 2,
});
```

## The Spread Operator(...) and Rest Pattern

```JavaScript
const arr = [7, 8, 9];
const newArr = [1, 2, ...arr];

console.log(newArr); //Prints the array: [1, 2, 7, 8, 9]

console.log(...newArr); //Prints the contents of the array separately: 1 2 7 8 9

//The spread operator works with all iterables(arrays, strings, maps, sets, etc)

//Breaking down a string
const myName = "Adam"

const myNameLetters = [...myName] //Saves each letter into the array separated by commas

console.log(myNameLetters) //Prints ["A", "d", "a", "m"]
console.log(...myName) //Prints A d a m

//Using spread operator in a function with multiple parameters
const restaurant = {
  OrderPasta: function (ing1, ing2, ing3) {
    console.log(
      `Here is your delicious pasta with ${ing1}, ${ing2}, and ${ing3}`
      );
  },
}

//Prompt the user for input
const ingredients = [
  prompt("Let's make pasta! Ingredient 1?"),
  prompt("Let's make pasta! Ingredient 2?"),
  prompt("Let's make pasta! Ingredient 3?"),
];

restaurant.OrderPasta(...ingredients); //Unpacks the 3 ingredients in the array and provides them as the 3 required parameters.

//------Rest Pattern------

// In Destructuring:
const names = ["Adam", "Bob", "Barry", "Lola", "Cassandra"]

const [myName, ...otherNames] = names;

console.log(myName, otherNames) //Prints Adam separately and an array with ["Bob", "Barry", "Lola", "Cassandra"]

//In Functions:
//...numbers packs all of the arguments into an array
function add(...numbers){
let sum = 0

for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i]
}

console.log(sum);
}

add(2, 3) //Prints 5

const x = [1, 2, 3]

add(...x)//Unpacks all elements and provides them as individual arguments printing 5
```

## Short Circuiting

```JavaScript
//The OR operator (||) will return the first truthy value of all the operands or the last value if all are falsy.
console.log("" || "Adam") //Prints Adam
console.log(true || 0) //Prints true

//The AND operator (&&) will return the first falsy value of all operands or the last value if all are truthy.
console.log(0 && "Adam") //Prints 0
console.log(7 && "Adam") //Prints Adam
```

## Nullish Coalescing Operator

```JavaScript
const myGuest = 0;

const guests = myGuest || 10;

console.log(guests); //Prints 10 because 0 is a falsy value.

//However, if we want to check only if the variable exists regardless if it is falsy or not, we can use the nullish coalescing operator.

const guestCorrect = myGuest ?? 10;

console.log(guestCorrect); //Prints 0 if myGuest exists or 10 if the variable is null/undefined.
```

## for-of loop

```JavaScript
const restaurant = {
  starterMenu: ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad"],
  mainMenu: ["Pizza", "Pasta", "Risotto"],
}

const menu = [...restaurant.starterMenu, ...restaurant.mainMenu]; //Unpacks both menu's into 1 array

for (const item of menu) {
  console.log(item);
}

for (const [index, foodName] of menu.entries()) {
  console.log(`${index + 1}: ${foodName}`);
}

```
