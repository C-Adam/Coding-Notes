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

## for-of loop and .entries()

```JavaScript
const menu = ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad", "Pizza", "Pasta", "Risotto"]

//-------Example 1---------
/*
The code below prints each of the items in the array separately:

Focaccia
Bruschetta
Garlic Bread
Caprese Salad
Pizza
Pasta
Risotto
*/

for (const item of menu) {
  console.log(item);
}


//--------Using .entries()---------------
/*
If we want the index of the element, we use .entries() on the array which puts each item into their own array with their original indexes
[ 0, 'Focaccia' ]
[ 1, 'Bruschetta' ]
[ 2, 'Garlic Bread' ]
[ 3, 'Caprese Salad' ]
[ 4, 'Pizza' ]
[ 5, 'Pasta' ]
[ 6, 'Risotto' ]
*/

for (const item of menu.entries()) {
  console.log(item);
}

//--------Using destructuring with .entries()---------------
/*
We can separate the index and the element into separate variables via destructuring. This is the equivalent to a for i, v in pairs() loop in the Lua programming language. Which would print the following:

1: Focaccia
2: Bruschetta
3: Garlic Bread
4: Caprese Salad
5: Pizza
6: Pasta
7: Risotto

NOTE: The first element didn't start from 0 in the printed result because in the loop, we added 1 to the index for more accurate display.
*/

for (const [index, foodName] of menu.entries()) {
  console.log(`${index + 1}: ${foodName}`);
}

```

## Optional Chaining

```JavaScript
//If we are checking if a property exists, instead of using if statements, we can use optional chaining.

const restaurants = {
  openingHours: {
    wednesday: {open: 12, close: 6}
    thursday: {open: 9, close: 11},
    friday: {open: 2, close: 7},
  },

  SaySomething: function(something){
    console.log(something);
  }
}

/*This would be useful in cases of using an API since the data isn't hardcoded so a lot of checking would have to be done.
Instead of writing if(openingHours && openingHours.monday){...}, we can write:
*/

console.log(restaurant.openingHours?.mon?.open); //This would print undefined

/*The "?" checks the existence of all elements before it. If an element does not exist, "undefined" would be returned instead of proceeding. Without this optional chaining, we would receive an error because: monday is already undefined and trying to access an property of an undefined element results in a error.*/

//The same can be used on Methods:
console.log(restaurant.SaySomething?.("Hello World!") ?? "Method does not exist"); //This would print Hello World!
console.log(restaurant.RandomPhrase?.("Hello World!") ?? "Method does not exist"); //This would print Method does not exist

//As well as Arrays:
let users = [{ name: "jonas", email: "blalalal@gmail.com" }];

console.log(users[0]?.name ?? "Empty"); //Prints Jonas

users = []

console.log(users[0]?.name ?? "Empty"); //Prints Empty

//----------------------Extra Tip-------------------------
//Fun fact: This can be combined with the Ternary Operator:
console.log(restaurant.openingHours?.mon?.open ? "Exist" : "Doesn't Exist"); //Will print Doesn't exist.
```

## Looping Objects

```JavaScript
const restaurants = {
  openingHours: {
    wednesday: {open: 12, close: 6}
    thursday: {open: 9, close: 11},
    friday: {open: 2, close: 7},
  },
}


const days = Object.keys(restaurant.openingHours); //Creates an array and inserts all of the keys of the object provided
for (const day of days) {
  console.log(day); //Prints wednesday thursday friday
}

//We can alternatively use Object.values(restaurant.openingHours) if we need the values.

const entries = Object.entries(restaurant.openingHours);
console.log(entries); //This prints an array containing arrays that contain each key and value pair:
/*
[
  [ 'thu', { open: 12, close: 22 } ],
  [ 'fri', { open: 11, close: 23 } ],
  [ 'sat', { open: 0, close: 24 } ]
]
*/

//We can take this a step further with destructuring:
for (const [key, { open, close }] of entries) {
  console.log(key, open, close);
}

/*Which would print:
thu 12 22
fri 11 23
sat 0 24
*/
```

## Sets

```JavaScript
const ordersSet = new Set(["Pizza", "Pasta", "Pizza", "Risotto"]); //A set only hold unique data

console.log(ordersSet); //Will print {"Pizza", "Pasta", "Risotto"}; The second pizza value is removed

console.log(ordersSet.has("Bread")); //Similar to array.includes(), this checks if an item is inside of a set.

ordersSet.add("Garlic Bread");//The equivalent to array.push(); adding an item to the set

ordersSet.delete("Risotto")//Deletes the element within the set.

console.log(ordersSet); //Will print {"Pizza", "Pasta", "Garlic Bread"}; Added Garlic Bread and deleted Risotto.

ordersSet.clear() //Removes all elements in the set.

```

## Maps

```JavaScript
const rest = new Map(); //Creates the map

rest.set("Name", "Classico Italiano"); //Take 2 inputs: Key, Value; Then puts them into the set.
rest.set(1, "Rome, Italy"); //The key can be any type, boolean, number, string, etc.
console.log(rest.set(2, "Lisbon, Portugal")); //When we call map.set(), not only is the pair added, but the map is also returned. This will print:

/*
Map(3) {
  'Name' => 'Classico Italiano',
  1 => 'Rome, Italy',
  2 => 'Lisbon, Portugal'
}
*/

//We can also create sets by using nested arrays:
const question = new Map([
  ["question", "What is my name?"],
  [1, "Adam"],
  [2, "Bob"],
  [3, "Fred"],
  ["correct", 1],
  [true, "Correct!"],
  [false, "Try again!"],
]);

/*
Which will print:
Map(7) {
  'question' => 'What is my name?',
  1 => 'Adam',
  2 => 'Bob',
  3 => 'Fred',
  'correct' => 1,
  true => 'Correct!',
  false => 'Try again!'
}
*/

//To retrieve values, we use Map.get(key).
console.log(rest.get("Name")); //Will print Classico Italiano

//With booleans as keys, we can do things like this:
rest.set(false, "This is false!");
console.log(rest.get(0 > 1)); //Since 0 is not greater than 1, false is passed as the value and This is false! is printed.

//We can check if a map has a certain key using:
console.log(rest.has("categories")); //Prints false.

//We can remove key, value pairs using rest.delete(key):
rest.delete("Name");

//We can check the size of a map using:
console.log(rest.size)

//Maps can even store arrays as keys. HOWEVER, the array needs to be stored in a variable. When using rest.get() on an array, we are accessing it through it's address in the Heap, not it's specific value.

rest.set([1, 2], "Hello World")

console.log(rest.get([1, 2])) //NOTE: This will print undefined because both arrays are not the same object in the heap.

//We should do this instead:

const myArray = [1, 2]

rest.set(myArray, "Hello World");

console.log(rest.get(myArray)); //Will print Hello World because we accessed the object directly through its address.

//----------UNIQUE TIP----------
//Since Maps are created with nested arrays. We can create maps with Object.entries()
const restaurant = {
  openingHours: {
    wednesday: {open: 12, close: 6}
    thursday: {open: 9, close: 11},
    friday: {open: 2, close: 7},
  },
}

const anotherMap = new Map(Object.entries(restaurant.openingHours))

/*
Which would print:
Map(3) {
  'wednesday' => { open: 12, close: 22 },
  'thursday' => { open: 11, close: 23 },
  'friday' => { open: 0, close: 24 }
}
*/


//----------------Iterating Over Maps-------------------
//We can iterate over maps the same way as we do when destructuring an object in a for loop:

for (const [key, value] of question) {
  console.log(key, value);
}

//Also similar to objects, we can call map.keys() and map.values()
```

## String Manipulation

```JavaScript
let myString = "a+very+nice+tool";

myString.indexOf(/*string*/) //Returns the index where the letter/word was found
myString.slice(/*index*/) //Splits the string and returns the resulted string after the index provided.
myString.toLowerCase()
myString.toUpperCase()
myString.trim() //Removes whitespace in the string
myString.replace(/*string to replace*/, /*new string*/)
myString.replaceAll(/*string to replace*/, /*new string*/) //Replaces all existing instances of the string provided.
myString.includes(/*string*/) //Returns boolean of whether the string contains the provided character
myString.startsWith(/*string*/)
myString.endsWith(/*string*/)
myString.split("+") //Returns ["a", "very", "nice", "tool"]
myString.join(/*Character that connects the string*/) //Takes in an array of strings and joins them with the provided string/character
myString.padStart(/*The desired length of the string*/, /*The character to pad those spaces*/) //Fills in the start of the selected string with the character provided until it is the desired length.
myString.padEnd(/*The desired length of the string*/, /*The character to pad those spaces*/) //Fills in the end of the selected string with the character provided until it is the desired length.
myString.repeat(/*number of times to repeat*/) //Repeats the string x amount of times (console.log(myString.repeat(5)))
```

## Deep Cloning Objects with Lodash

```JavaScript
/*To clone deep objects (objects that contain other objects) and ensure that the original object is not changed upon manipulation of the copy, we can use a JavaScript Library called Lodash.

1. Run npm install lodash in the working directory
2. Require the lodash library (preferably at the top of the code)
*/

const passenger1 = {
  name: 'Adam',
  id: 2312321736,
  family: {
    mother: 'Sigita',
    father: 'Paul',
  },
};

 const passenger2 = Object.assign({}, passenger1); //Will create a shallow clone
//const passenger2 = { ...passenger1 }; //Will also only create a shallow clone

passenger2.name = 'Bob';
passenger2.id = 87172467126;
passenger2.family.mother = 'Neringa';

console.log('Passenger1:', passenger1);
console.log('Passenger2:', passenger2);

/* Will print the following:
Passenger1: {
  name: 'Adam',
  id: 2312321736,
  family: { mother: 'Neringa', father: 'Paul' }
}
Passenger2: {
  name: 'Bob',
  id: 87172467126,
  family: { mother: 'Neringa', father: 'Paul' }
}
*/

//-----------------------------------Using Lodash-------------------------------------------

const _ = require('lodash');

const passenger2 = _.cloneDeep(passenger1); //Using this method in the library, we can create a Deep Clone.

passenger2.name = 'Bob';
passenger2.id = 87172467126;
passenger2.family.mother = 'Neringa';

console.log('Passenger1:', passenger1);
console.log('Passenger2:', passenger2);

/* Will print the following:

Passenger1: {
  name: 'Adam',
  id: 2312321736,
  family: { mother: 'Sigita', father: 'Paul' }
}
Passenger2: {
  name: 'Bob',
  id: 87172467126,
  family: { mother: 'Neringa', father: 'Paul' }
}
*/

/*As we can see above, in the first example when cloning the table with the assign method or spread operator, the mother value in the family object is affected in both the original and cloned object. To prevent this, we use Lodash. */
```

## Returning Functions

```JavaScript
function Greet(greeting) {
  return function (name) {
    console.log(`${greeting} ${name}`);
  };
}

const greeterHey = Greet("Hey"); //The variable stores the function that is returned as well as the parameter [Function (anonymous)]. The anonymous is the greeting parameter

greeterHey("Jonas"); //We then call this function with the the name argument and it uses both parameters stored to print the full greeting to the console: Hey Jonas

Greet("Hey")("Adam");//This is the same as the above since we are calling both functions however it is more compact but less readable.

const arrGreet = greeting => name => console.log(`${greeting} ${name}`); //This is how to return functions in arrow functions

arrGreet("Hi")("Adam");

```

## The call and apply method

```JavaScript
//Creating an airline object that has a method that creates bookings
const lufthansa = {
  airline: "Lufthansa",
  iataCode: "LH",
  bookings: [],
  Book: function (flightNum, passengerName) {
    console.log(
      `${passengerName} booked a seat on ${this.airline} flight ${this.iataCode}${flightNum}`
    );
    this.bookings.push({
      flight: `${this.iataCode}${flightNum}`,
      passengerName,
    });
  },
};

//Assume however, that we want to create a new airline but do not want to copy and paste the Book function from the first object since it is bad practice.
const eurowings = {
  airline: "Eurowings",
  iataCode: "EW",
  bookings: [],
};

//We can then store the objects function in another variable
const Book = lufthansa.Book;

//However, we get an error calling this because in regular function calls, the "this" keyword is undefined because since we are not passing in an object, how would the function know which airline to run the book function on.
Book(23, "Adam Cooper");

//To fix this issue, we use the call method. The first argument is the object that we want to use for the "this" value. Then rest of the arguments are for the parameters of the function.
Book.call(eurowings, 23, "Adam Cooper");
console.log(eurowings);

//-----------------------APPLY-----------------------
//The apply method is the same as the call method. HOWEVER, instead of the parameters of the function being passed in as separate arguments, the apply method takes an array of the arguments and unpacks them as required parameters.

const flightData = [583, "George Cooper"] //Array of arguments
Book.apply(eurowings, flightData)

/*NOTE: Apply is not that useful since we can simply use the spread operator in a call method*/
Book.call(eurowings, ...flightData)
```

## The bind method

```JavaScript
//The bind method has the same functionality as the call and apply method however, we can pre-apply arguments within the bind method.
const BookEW = Book.bind(eurowings);
BookEW(523, "Adam Cooper");

const BookEW23 = Book.bind(eurowings, 523);
BookEW23("Adam Cooper");

//------------------------------IMPORTANT------------------------------------
//When using event listeners, the "this" keyword points to the element that the event listener is acting on. However we can use the bind method to reassign the "this" keyword to a specific object.
lufthansa.planes = 300;
lufthansa.BuyPlane = function () {
  this.planes++;
  console.log(this.planes);
};

document.querySelector(".buy").addEventListener("click", lufthansa.BuyPlane); //This would bring Not a Number because the "this" keyword points to the buy button which cannot be incremented.

document.querySelector(".buy").addEventListener("click", lufthansa.BuyPlane.bind(lufthansa)); //This on the other hand will run as needed because we binded the "this" keyword to the specific object.

//We also cannot use the "call" method above because adding the call method runs the function which causes an error since the function provided is supposed to be a callback

//-----------------------------Partial Application---------------------------
//Initial Function
const addTax = (rate, value) => value + value * rate;
console.log(addTax(0.1, 200));

/*Function with same functionality as the one above however the rate is constant. Instead of constantly passing in the same argument each time, we create a new function with the bind method.
Provide null as the "this" keyword, then provide the constant/default arguments.*/
const addVAT = addTax.bind(null, [0.23]);
console.log(addVAT(100));
```

## Immediately Invoked Function Expression (IIFE)

```JavaScript
//This function is not assigned to a variable nor has a function declaration name which means it cannot be re-called. However, it can be ran once and immediately when put into parentheses since JavaScript sees this as an expression.
(function () {
  console.log("This will never be run again");
})();

//The same can be done for arrow functions
(() => console.log("This will never be run again"))();
```

## Closures

```JavaScript
//Informal Definition of Closure: a closure is like a backpack that a function carries. This backpack has all of the variables that were present in the environment where the function was created.
function SecureBooking() {
  let passengerCount = 0;

  return function () {
    passengerCount++;
    console.log(`${passengerCount} passengers`);
  };
}

const Booker = SecureBooking();

Booker();//Prints 1 passengers
Booker();//Prints 2 passengers
Booker();//Prints 3 passengers

//The passenger count variable is stored in a closure in the Booker scope chain and is updated each time the function is ran.

let f;

const g = function () {
  const a = 23;
  f = function () { //Re-assign f
    console.log(a * 2);
  };
};

const h = function () {
  const b = 777;
  f = function () { //Re-assign f once again
    console.log(b * 20);
  };
};

g(); //Run it to initialize f as a function, a as 23, and put "a" into f's closure.
f(); //Prints 46 because f still has access to the a variable
h(); //Run it to rewrite f as a different function, b as 777, and put replace "a" with "b" in f's closure.
f(); //Prints 1554
```

## setTimeout

```JavaScript
//Functions similarly to the task.spawn() method in Lua however the wait time is required as an argument.
//Multi-threading
function BoardPassengers(n, wait) {
  const perGroup = n / 3;

  setTimeout(function () { //This will run after 3 seconds
    console.log(`We are now boarding all ${n} passengers`);
    console.log(`There are 3 groups, each with ${perGroup} passengers`);
    }, wait * 1000); //The argument takes in milliseconds which is why we multiply by 1000 to convert the desired time into seconds.

  console.log(`Will start boarding in ${wait} seconds`); //This will run before the setTimeout function
}

BoardPassengers(180, 3)
```

## Array Methods

```JavaScript
//-------------------------------array.slice()------------------------------------------
//First parameter is where the slice starts and second parameter(optional) is where the slice should end.
//          0    1    2    3    4
let arr = ['a', 'b', 'c', 'd', 'e'];
//Starts at index 2 and includes the value however when we end on 4, the value is not included.s
console.log(arr.slice(2, 4)); //Prints ["c", "d"]


//-------------------------------array.splice()------------------------------------------
//Similar to the slice method however, this method mutates the array. Values that are being spliced are taken off of the original array.
//          0    1    2    3    4
let arr = ['a', 'b', 'c', 'd', 'e'];
console.log(arr.splice(0, 2)); //The first parameter is where the splice starts; The second parameter(optional) is the number of indexes to remove. Prints ["a", "b"]
console.log(arr); //Prints ["c", "d", "e"]


//-------------------------------array.reverse()------------------------------------------
//NOTE: This method mutates the original array. Make a copy before reversing an array if needed.
let arr = ['a', 'b', 'c', 'd', 'e'];
console.log(arr.reverse()) //Prints ['e', 'd', 'c', 'b', 'a']


//-------------------------------array.concat()------------------------------------------
//This method creates a new array (does not mutate original) so it should be stored in a variable for reference.
let arr = ['a', 'b', 'c'];
let others = ['d', 'e', 'f'];
console.log(arr.concat(others)); //Prints ['a', 'b', 'c', 'd', 'e', 'f']


//-------------------------------array.join()------------------------------------------
let arr = ['a', 'b', 'c'];
console.log(arr.join('-')); //Prints a string: a-b-c


//-------------------------------array.at()------------------------------------------
//Functions the exact same as the bracket notation arr[0] however we can get the last element of the array using -1 only with the at method.
let arr = [23, 11, 64];
arr[-1]//Prints undefined
arr[arr.length - 1] //Prints 64 (only way we can get the last index with bracket notation)
arr.at(-1);//Prints 64


//-------------------------------array.forEach()------------------------------------------
//Similar to the for-of loop however this loop runs the callback function for each index of the entire array without interruption (THIS LOOP CANNOT BE BROKEN OUT OF)
//The forEach method also can be used on maps and sets.
arr.forEach(function (value, index) {
  console.log(`index ${index}, value ${value}`);
});

//-------------------------------array.map()------------------------------------------
//Returns a new array containing the results of applying an operation on all original array elements
let numbers = [2, 4, 6, 8]
const doubledNumbers = numbers.map(function(num){
  return num  * 2
})

console.log(doubledNumbers) //[4, 8, 12, 16]

//-------------------------------array.filter()------------------------------------------
//


```

## element.insertAdjacentHTML()

```JavaScript
/*We can insert html into an page element using the insertAdjacentHtml method. The first parameter is the location where the HTML should be inserted (see: mdn insertAdjacentHtml for details). While the second parameter is the html string to be inserted.*/
const html = `
<div class="movements__row">
  <div class="movements__type movements__type--${type}">${index + 1} ${type}
  </div>
  <div class="movements__value">${value}€</div>
</div>`;

containerMovements.insertAdjacentHTML("afterbegin", html);
```

## element.innerHTML()

```JavaScript
//We can see/manipulate an elements html code directly in JavaScript

const myElement = document.querySelector(".movements")

console.log(myElement.innerHtml) //Will print out the entire html of the element
myElement.innerHtml = "" //Rewrites the element's html code; In this case, deletes all of the html.
```
