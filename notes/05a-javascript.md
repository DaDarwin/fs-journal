# Primitive Types

## Strings

```js
"String"
'Also a String'
`A Formated ${String}`
```

### **Constructor**

```js
const a = new String("Hello world"); // a === "Hello world" is false
const b = String("Hello world"); // b === "Hello world" is true
a instanceof String; // is true
b instanceof String; // is false
typeof a; // "object"
typeof b; // "string"
```

Don't use it

### **Properties**

```js
const string = "This is a String"

string.length // returns 16
```

Strings have one property `length` it's the last index + 1

### **Methods**

#### Accessing Values by Index & The diffrences between`.at()` , `.charAt()` , `.slice()` , `substring()` & Bracket Notation

```js
const string = "This is a String"
let index = "1"
let index2 ="1 + 1"

// .at()
string.at(3) // returns "s"
string.at(-2) // returns "n"
string.at(index) // returns "h"
string.at(index2) // returns "T"

// .charAt()
string.charAt(3) //returns "s"
string.charAt(-2)//returns ""
string.charAt(index) //returns "h
string.charAt(index2) // returns "T"

//  .slice()
string.slice(3) // returns "s is a String"
string.slice(-2) // returns "ng"
string.slice(index) // returns "his is a String"
string.slice(index2) // returns "This is a String"
string.slice(1,3) //returns "hi"


// Bracket Notation
string[3] // returns "s"
string[-2] // returns undefined
string[index] // returns "h"
string[index2] // returns undefined
```

##### **The Diffrences Are...**

* `.at()` & `.atChar()` are identical besides two points

  1. `.at()` Can accept a negative index to return a value from the end of the string

  2. If `.at()` gets a positive index out of range it returns `undefined`

While `.charAt()` returns an empty string if accessed with a negative number or any other number out of range. Making `.at()` more useful in majority of functions with it's shorter syntax, besides cases where a empty string is needed and not just a **Falsy** value

* `.slice()`, While it can be used in a method similar to `.at()`, but with it's multiple parameters it's intended use is to access multiple values in a string, not for accessing a singular value

* **Bracket Notation** is mostly shorthand for `.charAt()` with two key diffrences *(In the case of accessing values in a string, it does a lot more* ***See Bracket Notation in Operators)***

  1. `.at()` & `.charAt()` attempts to convert the variable given as an index into a integer while **Bracket Notation** doesn't, see `index` and `index2`
  
      * On `index` all three are able to interpret `"1"` as `1`

      * While on `index2` `.at()` & `.charAt()` interpreted it as `0` while **Bracket Notation** just said no
  
  1. And like `.at()` **Bracket Notation** returns `undefined` when out of range

Thus **Bracket Notation** is the shortest syntax for accessing a singular value with a positive index, so it would be used instead of `.at()` in those cases

```js
const string = "This is a String"

string[2] // returns "i"
string.at(-2) // returns "n"
string.slice(0,4) // returns "This"
```

In summary **Bracket Notation** should be used when accessing a singular value with a positive index, `.at()` with a negative index, `.splice()` when accessing multiple values & `.charAt()` on cases where a empty string is needed and not just a **Falsy** value.

Or just use **Bracket Notation** for singular values and `.slice()` for multiple or even a singular negative if you're inclined

```js
string[2] // returns "i"
string[string.length - 2] // returns "n"
string.slice(0,4) // returns "This"
string.slice(-2,-1) // returns "n"
```

`.at()` & `.atChar()` are both made irrelevent by **Bracket Notation**, while `.at()` has shorter and cleaner syntax the times where you would be accessing a singular value by a negative are severely limited, & There's even fewer times where a better alternative isn't available to you.

Also `.substring()` is just `.slice()` but intracts with negative numbers diffrently I'm just going throw the MDN examples below

```js
const text = "Mozilla";
console.log(text.substring(5, 2)); // "zil"
console.log(text.slice(5, 2)); // ""

console.log(text.substring(-5, 2)); // "Mo"
console.log(text.substring(-5, -2)); // ""

console.log(text.slice(-5, 2)); // ""
console.log(text.slice(-5, -2)); // "zil"
```

Do I need to say more

#### **Accessing Indexes by Value: `.indexOf()` & `.lastIndexOf()`**

```js
const string = "This is a String"

string.indexOf("i") // returns 2
string.lastIndexOf("i") // returns 13

string.indexOf("is") // returns 2
string.indexOf("is", 3)  // returns 5

string.lastIndexOf("is") // returns 5
string.lastIndexOf("is", 4) // returns 2
```

Pretty self-explanatory if you remember they exist. `.indexOf()` returns the first occurrence of the value, & `.lastIndexOf()` returns the last occurrence. Both have optional parameter for starting position.

#### **Replacing Values in a String: `replace()` & `replaceAll()`**

```js
let string = "This String is a String"

string.replace("i", "a") // returns "Thas String is a String"
string.replaceAll("i", "a") // returns "Thas Strang as a Strang"

string.replace("String", "Wall") // returns "This Wall is a String"
string.replaceAll("String", "Wall") // returns "This Wall is a Wall"
```

The only diffrence between the two is `.replaceAll()` replaces all occurrences while `.replace()` only does the first. Both can accept any string on both parameters

#### **Spliting Joining & Merging Strings: `.split()` `.join()` `.concat()`**

```js
let string = "This is a String"
let word = "Primitive"
let array = ["This", "is", "a", "String"]

string.split('') // returns ["T", "h", "i", "s", " ", "i", "s", " ", "a", " ", "S", "t", "r", "i", "n", "g"]
string.split(' ') //returns ["This", "is", "a", "String"]

array.join('') // returns "ThisisaString"
array.join(' ') // returns "This is a String"

string.concat('', word) // returns "This is a StringPrimitive"
string.concat(' ', word) // returns "This is a String Primitive"
```

`.split()` & `.join()` do the opposite of each other and `.concat()` merges an unlimited number of strings together

#### **`.startsWith()` `.includes()` `.endsWith()`**

```js
const string = "This is a String"

string.startsWith("String") // returns false
string.startsWith("This") // returns true

string.includes("Primitive") // returns false
string.includes("String") // returns true

string.endsWith("This") // returns false
string.endsWith("String") // returns true
```

If it exists in the string it returns `true`

#### **Odds & Ends: `.repeat()` `.toLowerCase()` `.toUpperCase()`**

```js
let string = "This is a String"

string.repeat(2) // returns "This is a StringThis is a String"
string.toLowerCase() // returns "this is a string"
string.toUpperCase() // returns "THIS IS A STRING"
```

<!-- #### `.trim()` `.pad()`

#### `[@@iterator]()` `.match()` `.search()`

#### .charCodeAt() .codePointAt() .fromCharCode() .fromCodePoint()

#### toWellFormed() .normalize() .isWellFormed() 

#### Non-Primitive Strings:`.valueOf()` `.toString()` -->

## Numbers & Big Int

```js
255; // two-hundred and fifty-five
255.0; // same number
255 === 255.0; // true
255 === 0xff; // true (hexadecimal notation)
255 === 0b11111111; // true (binary notation)
255 === 0.255e3; // true (decimal exponential notation)

const previouslyMaxSafeInteger = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991); // 9007199254740991n

const hugeString = BigInt("9007199254740991"); // 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff"); // 9007199254740991n

const hugeOctal = BigInt("0o377777777777777777"); // 9007199254740991n

const hugeBin = BigInt("0b11111111111111111111111111111111111111111111111111111",); // 9007199254740991n
```

Did you pass 2nd Grade? If so you know what a Number is.

Did you pass 9th Grade? If so you know what a Big Int is. (Only use a Big Int values when values greater than 2<sup>53</sup> are reasonably expected.)

While there are methods for Numbers and Big Int only certain programmers will ever use them often

## Booleans, Undefined & Null

`null` the value of nothing

`undefined` the absence of a value

### Booleans

A logical data type that can have only the values `true` or `false`

#### `Falsy` & `Truthy`

* `Falsy` undefined, null, ***Numbers:*** 0, -0, NaN , ***BigInt:*** 0n, ***Strings:*** an Empty String all return as `false`

* `Truthy` everything else returns `true`

## Sympol

IDK some kind of unique id

</end>
