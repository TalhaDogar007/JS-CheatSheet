# JS-CheatSheet
https://htmlcheatsheet.com/js/

# Strings

```javascript
var abc = "abcdefghijklmnopqrstuvwxyz";
var esc = 'I don\'t \n know';   // \n new line
var len = abc.length;           // string length
abc.indexOf("lmno");            // find substring, -1 if doesn't contain 
abc.lastIndexOf("lmno");        // last occurrence
abc.slice(3, 6);                // cuts out "def", negative values count from behind
abc.replace("abc","123");       // find and replace, takes regular expressions
abc.toUpperCase();              // convert to upper case
abc.toLowerCase();              // convert to lower case
abc.concat(" ", str2);          // abc + " " + str2
abc.charAt(2);                  // character at index: "c"
abc[2];                         // unsafe, abc[2] = "C" doesn't work
abc.charCodeAt(2);              // character code at index: "c" -> 99
abc.split(",");                 // splitting a string on commas gives an array
abc.split("");                  // splitting on characters
128.toString(16);               // number to hex(16), octal (8) or binary (2)
```

# Arrays

```javascript
var dogs = ["Bulldog", "Beagle", "Labrador"]; 
var dogs = new Array("Bulldog", "Beagle", "Labrador");  // declaration

alert(dogs[1]);             // access value at index, first item being [0]
dogs[0] = "Bull Terier";    // change the first item

for (var i = 0; i < dogs.length; i++) {     // parsing with array.length
console.log(dogs[i]);
}

dogs.toString();                        // convert to string: results "Bulldog,Beagle,Labrador"
dogs.join(" * ");                       // join: "Bulldog * Beagle * Labrador"
dogs.pop();                             // remove last element
dogs.push("Chihuahua");                 // add new element to the end
dogs[dogs.length] = "Chihuahua";        // the same as push
dogs.shift();                           // remove first element
dogs.unshift("Chihuahua");              // add new element to the beginning
delete dogs[0];                         // change element to undefined (not recommended)
dogs.splice(2, 0, "Pug", "Boxer");      // add elements (where, how many to remove, element list)
var animals = dogs.concat(cats,birds);  // join two arrays (dogs followed by cats and birds)
dogs.slice(1,4);                        // elements from [1] to [4-1]
dogs.sort();                            // sort string alphabetically
dogs.reverse();                         // sort string in descending order
x.sort(function(a, b){return a - b});   // numeric sort
x.sort(function(a, b){return b - a});   // numeric descending sort
highest = x[0];                         // first item in sorted array is the lowest (or highest) value
x.sort(function(a, b){return 0.5 - Math.random()});     // random order sort


var dogs = ["Bulldog", "Beagle", "Labrador"]; 

dogs.concat(["Poodle", "Husky"]);           // Concatenates two arrays: ["Bulldog", "Beagle", "Labrador", "Poodle", "Husky"]

dogs.copyWithin(2, 0, 1);                   // Copies array elements to another position within the array: ["Bulldog", "Beagle", "Bulldog"]

dogs.every((dog) => dog.length > 5);        // Checks if all elements pass a test: false

dogs.fill("Dalmatian", 1, 2);               // Fills elements in an array with a static value: ["Bulldog", "Dalmatian", "Labrador"]

dogs.filter((dog) => dog.startsWith("B"));  // Creates a new array with elements passing a test: ["Bulldog", "Beagle"]

dogs.find((dog) => dog === "Beagle");       // Returns the first element passing a test: "Beagle"

dogs.findIndex((dog) => dog === "Beagle");  // Returns the index of the first element passing a test: 1

dogs.forEach((dog) => console.log(dog));    // Executes a function for each array element

dogs.indexOf("Beagle");                     // Returns the first index of a specified value: 1

Array.isArray(dogs);                        // Checks if a value is an array: true

dogs.join(", ");                            // Joins all array elements into a string: "Bulldog, Beagle, Labrador"

dogs.lastIndexOf("Beagle");                // Returns the last index of a specified value: 1

dogs.map((dog) => dog.toUpperCase());      // Creates a new array with the results of a function on each element: ["BULLDOG", "BEAGLE", "LABRADOR"]

dogs.pop();                                // Removes the last element from an array: "Labrador"

dogs.push("Poodle");                       // Adds one or more elements to the end of an array: ["Bulldog", "Beagle", "Poodle"]

dogs.reduce((accumulator, currentValue)
=> accumulator + currentValue);           // Reduces an array to a single value (from left to right): "BulldogBeagleLabrador"

dogs.reduceRight((accumulator, currentValue)
=> accumulator + currentValue);          // Reduces an array to a single value (from right to left): "LabradorBeagleBulldog"

dogs.reverse();                          // Reverses the order of array elements: ["Labrador", "Beagle", "Bulldog"]

dogs.slice(1, 2);                        // Extracts a section of an array: ["Beagle"]

dogs.some((dog) => dog.length > 5);      // Checks if at least one element passes a test: true

dogs.sort();                             // Sorts array elements alphabetically: ["Beagle", "Bulldog", "Labrador"]

dogs.splice(1, 1, "Poodle");             // Adds/removes array elements: ["Beagle", "Poodle"]

dogs.toString();                         // Converts array elements into a string: "Beagle,Poodle"

dogs.valueOf();                          // Returns the primitive value of an array: ["Beagle", "Poodle
```

# Numbers and Math

## Basic Number Operations

```javascript
var pi = 3.141;
pi.toFixed(0);          // Returns 3
pi.toFixed(2);          // Returns 3.14 (useful for working with money)
pi.toPrecision(2);      // Returns 3.1
pi.valueOf();           // Returns the number

Number(true);           // Converts true to 1
Number(new Date());     // Converts a date to the number of milliseconds since 1970

parseInt("3 months");   // Returns the first number: 3
parseFloat("3.5 days"); // Returns 3.5

Number.MAX_VALUE        // Largest possible JavaScript number
Number.MIN_VALUE        // Smallest possible JavaScript number
Number.NEGATIVE_INFINITY// -Infinity
Number.POSITIVE_INFINITY// Infinity

######################################################### Math Functions

var pi = Math.PI;       // 3.141592653589793

Math.round(4.4);        // Returns 4 (rounded)
Math.round(4.5);        // Returns 5

Math.pow(2, 8);         // Returns 256 (2 to the power of 8)
Math.sqrt(49);          // Returns 7 (square root)

Math.abs(-3.14);        // Returns 3.14 (absolute, positive value)
Math.ceil(3.14);        // Returns 4 (rounded up)
Math.floor(3.99);       // Returns 3 (rounded down)

Math.sin(0);            // Returns 0 (sine)
Math.cos(Math.PI);      // Returns -1 (cosine)

// Other trigonometric functions: tan, atan, asin, acos

Math.min(0, 3, -2, 2);  // Returns -2 (the lowest value)
Math.max(0, 3, -2, 2);  // Returns 3 (the highest value)
```

# Variablesx
```javascript
var a;                          // variable
var b = "init";                 // string
var c = "Hi" + " " + "Joe";     // = "Hi Joe"
var d = 1 + 2 + "3";            // = "33"
var e = [2,3,5,8];              // array
var f = false;                  // boolean
var g = /()/;                   // RegEx
var h = function(){};           // function object
const PI = 3.14;                // constant
var a = 1, b = 2, c = a + b;    // one line
let z = 'zzz';                  // block scope local variable


########################################################### Strict mode
"use strict";   // Use strict mode to write secure code
x = 1;          // Throws an error because variable is not declared

########################################################### Values
false, true                     // boolean
18, 3.14, 0b10011, 0xF6, NaN    // number
"flower", 'John'                // string
undefined, null , Infinity      // special

########################################################### Operators
a = b + c - d;      // addition, substraction
a = b * (c / d);    // multiplication, division
x = 100 % 48;       // modulo. 100 / 48 remainder = 4
a++; b--;           // postfix increment and decrement

########################################################### Bitwise operators
&	AND 	 5 & 1 (0101 & 0001)	1 (1)
|	OR 	 5 | 1 (0101 | 0001)	5 (101)
~	NOT 	 ~ 5 (~0101)	10 (1010)
^	XOR 	 5 ^ 1 (0101 ^ 0001)	4 (100)
<<	left shift 	 5 << 1 (0101 << 1)	10 (1010)
>>	right shift 	 5 >> 1 (0101 >> 1)	2 (10)
>>>	zero fill right shift 	 5 >>> 1 (0101 >>> 1)	2 (10)

############################################################ Arithmetic
a * (b + c)         // grouping
person.age          // member
person[age]         // member
!(a == b)           // logical not
a != b              // not equal
typeof a            // type (number, object, function...)
x << 2  x >> 3      // minary shifting
a = b               // assignment
a == b              // equals
a != b              // unequal
a === b             // strict equal
a !== b             // strict unequal
a < b   a > b       // less and greater than
a <= b  a >= b      // less or equal, greater or eq
a += b              // a = a + b (works with - * %...)
a && b              // logical and
a || b              // logical or

Math.log(1);            // Returns 0 (natural logarithm)
Math.exp(1);            // Returns 2.7182 (e to the power of x)

Math.random();          // Returns a random number between 0 and 1
Math.floor(Math.random() * 5) + 1;  // Returns a random integer from 1 to 5
```
