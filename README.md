# JavaScript Notes

---

## 📝 Variable Declarations: var, let, const

- <span style="color:#007acc">**var**</span>
  - <span style="color:#228B22">Function-scoped, can be re-declared and updated. Hoisted to the top of its scope.</span>
  - **Example:**
    ```js
    var x = 5;
    x = 10;
    var x = 20; // Allowed
    ```

- <span style="color:#007acc">**let**</span>
  - <span style="color:#228B22">Block-scoped, can be updated but not re-declared in the same scope. Not hoisted in the same way as var.</span>
  - **Example:**
    ```js
    let y = 5;
    y = 10;
    // let y = 20; // Error: y has already been declared in this scope
    ```

- <span style="color:#007acc">**const**</span>
  - <span style="color:#228B22">Block-scoped, cannot be updated or re-declared. Must be initialized at declaration.</span>
  - **Example:**
    ```js
    const z = 5;
    // z = 10; // Error: Assignment to constant variable
    // const z = 20; // Error: z has already been declared
    ```

---

## 📦 Understanding Scope and Block

- <span style="color:#007acc">**Scope**</span>
  - <span style="color:#228B22">The area in code where a variable is accessible. In JavaScript, the main types are:</span>
    - <b>Global Scope:</b> Variables declared outside any function/block are accessible everywhere.
    - <b>Function Scope:</b> Variables declared inside a function are only accessible within that function.
    - <b>Block Scope:</b> Variables declared inside a block (like inside { ... }) are only accessible within that block.

- <span style="color:#007acc">**Block**</span>
  - <span style="color:#228B22">A block is any code wrapped in curly braces <code>{ ... }</code>. Common blocks are in if statements, loops, and functions.</span>
  - **Example:**
    ```js
    if (true) {
      let message = "Hello"; // message is only accessible inside this block
    }
    // console.log(message); // Error: message is not defined
    ```

---

## 🔀 Conditional Statements

- <span style="color:#007acc">**if statement**</span>
  - <span style="color:#228B22">Executes a block of code if a specified condition is true.</span>
  - **Example:**
    ```js
    let age = 18;
    if (age >= 18) {
      console.log("You are an adult");
    }
    ```

- <span style="color:#007acc">**if...else statement**</span>
  - <span style="color:#228B22">Executes one block if the condition is true, another if it's false.</span>
  - **Example:**
    ```js
    let age = 16;
    if (age >= 18) {
      console.log("You are an adult");
    } else {
      console.log("You are a minor");
    }
    ```

- <span style="color:#007acc">**if...else if...else statement**</span>
  - <span style="color:#228B22">Tests multiple conditions in sequence.</span>
  - **Example:**
    ```js
    let score = 85;
    if (score >= 90) {
      console.log("Grade: A");
    } else if (score >= 80) {
      console.log("Grade: B");
    } else if (score >= 70) {
      console.log("Grade: C");
    } else {
      console.log("Grade: F");
    }
    ```

- <span style="color:#007acc">**Nested if statements**</span>
  - <span style="color:#228B22">You can put if statements inside other if statements.</span>
  - **Example:**
    ```js
    let age = 20;
    let hasLicense = true;
    
    if (age >= 18) {
      if (hasLicense) {
        console.log("You can drive");
      } else {
        console.log("You need a license");
      }
    } else {
      console.log("You are too young to drive");
    }
    ```

- <span style="color:#007acc">**Comparison Operators**</span>
  - <span style="color:#228B22">Common operators used in conditions:</span>
  - **Example:**
    ```js
    let x = 5;
    let y = 10;
    
    if (x == y) console.log("Equal");           // == (loose equality)
    if (x === y) console.log("Strict equal");   // === (strict equality)
    if (x != y) console.log("Not equal");       // != (loose inequality)
    if (x !== y) console.log("Strict not equal"); // !== (strict inequality)
    if (x < y) console.log("Less than");        // <
    if (x > y) console.log("Greater than");     // >
    if (x <= y) console.log("Less or equal");   // <=
    if (x >= y) console.log("Greater or equal"); // >=
    ```

- <span style="color:#007acc">**switch statement**</span>
  - <span style="color:#228B22">The switch statement is used to perform different actions based on different conditions. It is often used as a cleaner alternative to many else if statements.</span>
  - **Example:**
    ```js
    let day = 3;
    let dayName;
    
    switch (day) {
      case 1:
        dayName = "Monday";
        break;
      case 2:
        dayName = "Tuesday";
        break;
      case 3:
        dayName = "Wednesday";
        break;
      case 4:
        dayName = "Thursday";
        break;
      case 5:
        dayName = "Friday";
        break;
      case 6:
        dayName = "Saturday";
        break;
      case 7:
        dayName = "Sunday";
        break;
      default:
        dayName = "Invalid day";
    }
    
    console.log(dayName); // 'Wednesday'
    ```
  - <span style="color:#228B22">The <b>break</b> statement stops the execution inside the switch. The <b>default</b> case runs if no case matches.</span>

- <span style="color:#007acc">**Ternary Operator (?:)**</span>
  - <span style="color:#228B22">The ternary operator is a shorthand for if...else. It evaluates a condition and returns one value if true, and another if false.</span>
  - **Syntax:**
    ```js
    condition ? valueIfTrue : valueIfFalse
    ```
  - **Example:**
    ```js
    let age = 20;
    let message = (age >= 18) ? "Adult" : "Minor";
    console.log(message); // 'Adult'
    ```
  - <span style="color:#228B22">You can also nest ternary operators, but for readability, avoid making them too complex.</span>
    ```js
    let score = 85;
    let grade = score >= 90 ? "A" : score >= 80 ? "B" : score >= 70 ? "C" : "F";
    console.log(grade); // 'B'
    ```

---

## 🔁 Loops

- <span style="color:#007acc">**for loop**</span>
  - <span style="color:#228B22">Repeats a block of code a specific number of times.</span>
  - **Example:**
    ```js
    for (let i = 0; i < 5; i++) {
      console.log(i);
    }
    // Output: 0 1 2 3 4
    ```

- <span style="color:#007acc">**while loop**</span>
  - <span style="color:#228B22">Repeats a block of code as long as a condition is true.</span>
  - **Example:**
    ```js
    let i = 0;
    while (i < 5) {
      console.log(i);
      i++;
    }
    // Output: 0 1 2 3 4
    ```

- <span style="color:#007acc">**do...while loop**</span>
  - <span style="color:#228B22">Like a while loop, but always runs the block at least once.</span>
  - **Example:**
    ```js
    let i = 0;
    do {
      console.log(i);
      i++;
    } while (i < 5);
    // Output: 0 1 2 3 4
    ```

- <span style="color:#007acc">**for...of loop**</span>
  - <span style="color:#228B22">Loops over iterable objects (like arrays, strings).</span>
  - **Example:**
    ```js
    let arr = ["a", "b", "c"];
    for (let value of arr) {
      console.log(value);
    }
    // Output: a b c
    ```

- <span style="color:#007acc">**for...in loop**</span>
  - <span style="color:#228B22">Loops over the enumerable properties of an object.</span>
  - **Example:**
    ```js
    let obj = {a: 1, b: 2, c: 3};
    for (let key in obj) {
      console.log(key, obj[key]);
    }
    // Output: a 1, b 2, c 3
    ```

- <span style="color:#007acc">**for...in loop with Objects**</span>
  - <span style="color:#228B22">Loops over the enumerable properties of an object. Useful for iterating through object keys.</span>
  - **Example:**
    ```js
    let person = {
      name: "John",
      age: 30,
      city: "New York"
    };
    
    for (let key in person) {
      console.log(key + ": " + person[key]);
    }
    // Output:
    // name: John
    // age: 30
    // city: New York
    ```

- <span style="color:#007acc">**hasOwnProperty() with for...in**</span>
  - <span style="color:#228B22">Use hasOwnProperty() to avoid inherited properties from the prototype chain.</span>
  - **Example:**
    ```js
    let obj = {
      ownProp: "I'm own property"
    };
    
    // Add a property to Object.prototype (not recommended in practice)
    Object.prototype.inheritedProp = "I'm inherited";
    
    for (let key in obj) {
      if (obj.hasOwnProperty(key)) {
        console.log(key + ": " + obj[key]);
      }
    }
    // Output: ownProp: I'm own property
    ```

- <span style="color:#007acc">**break statement**</span>
  - <span style="color:#228B22">Exits the loop immediately, even if the condition is still true.</span>
  - **Example:**
    ```js
    for (let i = 0; i < 10; i++) {
      if (i === 5) break;
      console.log(i);
    }
    // Output: 0 1 2 3 4
    ```

- <span style="color:#007acc">**continue statement**</span>
  - <span style="color:#228B22">Skips the current iteration and continues with the next one.</span>
  - **Example:**
    ```js
    for (let i = 0; i < 5; i++) {
      if (i === 2) continue;
      console.log(i);
    }
    // Output: 0 1 3 4
    ```

---

## String Properties & Methods

- <span style="color:#007acc">**.length**</span>
  - <span style="color:#228B22">Returns the length of the string.</span>
  - **Example:**
    ```js
    let name = "JavaScript";
    console.log(name.length); // 10
    ```

- <span style="color:#007acc">**.charAt(index)**</span>
  - <span style="color:#228B22">Returns the character at the specified index.</span>
  - **Example:**
    ```js
    let str = "Hello";
    console.log(str.charAt(1)); // 'e'
    ```

- <span style="color:#007acc">**.indexOf(substring)**</span>
  - <span style="color:#228B22">Returns the index of the first occurrence of the specified substring, or -1 if not found.</span>
  - **Example:**
    ```js
    let str = "banana";
    console.log(str.indexOf("a")); // 1
    ```

- <span style="color:#007acc">**.lastIndexOf(substring)**</span>
  - <span style="color:#228B22">Returns the index of the last occurrence of the specified substring, or -1 if not found.</span>
  - **Example:**
    ```js
    let str = "banana";
    console.log(str.lastIndexOf("a")); // 5
    ```

- <span style="color:#007acc">**.slice(start, end)**</span>
  - <span style="color:#228B22">Returns a section of the string from the start index up to, but not including, the end index. If end is omitted, extracts to the end of the string.</span>
  - **Example:**
    ```js
    let str = "JavaScript";
    console.log(str.slice(0, 4)); // 'Java'
    ```

- <span style="color:#007acc">**.toUpperCase()**</span>
  - <span style="color:#228B22">Converts the string to uppercase letters.</span>
  - **Example:**
    ```js
    let str = "hello";
    console.log(str.toUpperCase()); // 'HELLO'
    ```

- <span style="color:#007acc">**.toLowerCase()**</span>
  - <span style="color:#228B22">Converts the string to lowercase letters.</span>
  - **Example:**
    ```js
    let str = "HELLO";
    console.log(str.toLowerCase()); // 'hello'
    ```

- <span style="color:#007acc">**.includes(substring)**</span>
  - <span style="color:#228B22">Checks if the string contains the specified substring. Returns true or false.</span>
  - **Example:**
    ```js
    let str = "JavaScript";
    console.log(str.includes("Script")); // true
    ```

- <span style="color:#007acc">**.split(separator)**</span>
  - <span style="color:#228B22">Splits the string into an array of substrings using the specified separator.</span>
  - **Example:**
    ```js
    let str = "a,b,c";
    console.log(str.split(",")); // ['a', 'b', 'c']
    ```

- <span style="color:#007acc">**.trim()**</span>
  - <span style="color:#228B22">Removes whitespace from both ends of a string (spaces, tabs, newlines).</span>
  - **Example:**
    ```js
    let str = "   Hello World!   ";
    let trimmed = str.trim();
    console.log(trimmed); // 'Hello World!'
    ```

---

## 🔢 Number Function

- <span style="color:#007acc">**Number(value)**</span>
  - <span style="color:#228B22">Converts a value (string, boolean, etc.) to a number. If the value cannot be converted, it returns NaN (Not a Number).</span>
  - **Examples:**
    ```js
    Number("123");      // 123
    Number("12.34");    // 12.34
    Number("abc");      // NaN
    Number(true);        // 1
    Number(false);       // 0
    Number(null);        // 0
    Number(undefined);   // NaN
    ```

---

## 🔢 Number Methods & Usage

- <span style="color:#007acc">**Number.isInteger(value)**</span>
  - <span style="color:#228B22">Checks if the value is an integer.</span>
  - **Example:**
    ```js
    Number.isInteger(10);    // true
    Number.isInteger(10.5);  // false
    ```

- <span style="color:#007acc">**parseFloat(string)**</span>
  - <span style="color:#228B22">Parses a string and returns a floating point number.</span>
  - **Example:**
    ```js
    parseFloat("3.14");     // 3.14
    parseFloat("10");       // 10
    ```

- <span style="color:#007acc">**parseInt(string, radix)**</span>
  - <span style="color:#228B22">Parses a string and returns an integer. The radix is the base (e.g., 10 for decimal).</span>
  - **Example:**
    ```js
    parseInt("42");         // 42
    parseInt("101", 2);     // 5 (binary to decimal)
    ```

- <span style="color:#007acc">**number.toFixed(digits)**</span>
  - <span style="color:#228B22">Formats a number using fixed-point notation (keeps specified decimal places, returns a string).</span>
  - **Example:**
    ```js
    let n = 3.14159;
    n.toFixed(2);            // '3.14'
    ```

- <span style="color:#007acc">**number.toString([radix])**</span>
  - <span style="color:#228B22">Converts a number to a string. Optionally, you can specify a radix (base).</span>
  - **Example:**
    ```js
    let n = 255;
    n.toString();            // '255'
    n.toString(16);          // 'ff' (hexadecimal)
    ```

- <span style="color:#007acc">**Chaining Methods**</span>
  - <span style="color:#228B22">You can chain methods to perform multiple operations in one line.</span>
  - **Example:**
    ```js
    let n = 3.14159;
    let result = n.toFixed(2).toString(); // '3.14'
    ```

- <span style="color:#007acc">**Number.isNaN(value)**</span>
  - <span style="color:#228B22">Checks if the value is NaN (and of type number).</span>
  - **Example:**
    ```js
    Number.isNaN(NaN);       // true
    Number.isNaN("abc");    // false
    Number.isNaN(parseInt("abc")); // true
    ```

- <span style="color:#007acc">**isNaN(value)**</span>
  - <span style="color:#228B22">Checks if the value is NaN (tries to convert the value to a number first).</span>
  - **Example:**
    ```js
    isNaN(NaN);              // true
    isNaN("abc");           // true
    isNaN("123");           // false
    ```

---

## 📐 Math Object & Methods

- <span style="color:#007acc">**What is Math?**</span>
  - <span style="color:#228B22">Math is a built-in JavaScript object that provides mathematical constants and functions. It's not a constructor, so you don't use 'new' with it.</span>
  - **Example:**
    ```js
    // Math is an object with properties and methods
    console.log(Math.PI);        // 3.141592653589793
    console.log(Math.E);         // 2.718281828459045
    console.log(Math.random());  // Random number between 0 and 1
    ```

- <span style="color:#007acc">**Math.trunc(number)**</span>
  - <span style="color:#228B22">Removes the decimal part of a number, returning the integer part.</span>
  - **Example:**
    ```js
    Math.trunc(3.7);   // 3
    Math.trunc(-3.7);  // -3
    Math.trunc(3);     // 3
    ```

- <span style="color:#007acc">**Math.round(number)**</span>
  - <span style="color:#228B22">Rounds a number to the nearest integer.</span>
  - **Example:**
    ```js
    Math.round(3.4);   // 3
    Math.round(3.5);   // 4
    Math.round(3.6);   // 4
    Math.round(-3.5);  // -3
    ```

- <span style="color:#007acc">**Math.ceil(number)**</span>
  - <span style="color:#228B22">Rounds a number up to the nearest integer (always rounds up).</span>
  - **Example:**
    ```js
    Math.ceil(3.1);    // 4
    Math.ceil(3.9);    // 4
    Math.ceil(3);      // 3
    Math.ceil(-3.1);   // -3
    ```

- <span style="color:#007acc">**Math.floor(number)**</span>
  - <span style="color:#228B22">Rounds a number down to the nearest integer (always rounds down).</span>
  - **Example:**
    ```js
    Math.floor(3.1);   // 3
    Math.floor(3.9);   // 3
    Math.floor(3);     // 3
    Math.floor(-3.1);  // -4
    ```

- <span style="color:#007acc">**Math.pow(base, exponent)**</span>
  - <span style="color:#228B22">Returns the value of a base raised to the power of an exponent.</span>
  - **Example:**
    ```js
    Math.pow(2, 3);    // 8 (2^3)
    Math.pow(5, 2);    // 25 (5^2)
    Math.pow(10, 0);   // 1
    ```

- <span style="color:#007acc">**Math.min(...numbers)**</span>
  - <span style="color:#228B22">Returns the smallest number from a list of numbers.</span>
  - **Example:**
    ```js
    Math.min(1, 2, 3);     // 1
    Math.min(-1, -2, -3);  // -3
    Math.min(5, 5, 5);     // 5
    ```

- <span style="color:#007acc">**Math.max(...numbers)**</span>
  - <span style="color:#228B22">Returns the largest number from a list of numbers.</span>
  - **Example:**
    ```js
    Math.max(1, 2, 3);     // 3
    Math.max(-1, -2, -3);  // -1
    Math.max(5, 5, 5);     // 5
    ```

- <span style="color:#007acc">**Math.random()**</span>
  - <span style="color:#228B22">Returns a random number between 0 (inclusive) and 1 (exclusive).</span>
  - **Example:**
    ```js
    Math.random();          // Random number between 0 and 1
    Math.random() * 10;     // Random number between 0 and 10
    Math.floor(Math.random() * 10); // Random integer between 0 and 9
    ```

- <span style="color:#007acc">**Chaining Math Methods**</span>
  - <span style="color:#228B22">You can chain Math methods to perform complex calculations.</span>
  - **Example:**
    ```js
    // Generate random integer between 1 and 100
    let randomNum = Math.floor(Math.random() * 100) + 1;
    
    // Round the result of a power calculation
    let result = Math.round(Math.pow(2.5, 3)); // 16
    
    // Find the maximum of rounded numbers
    let maxRounded = Math.max(
      Math.round(3.2), 
      Math.round(4.7), 
      Math.round(2.9)
    ); // 5
    ```

---

## 📚 More Math Methods

For a complete list of Math methods and properties, visit the [MDN Math Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

---

## 🧩 Functions

- <span style="color:#007acc">**Function Declaration**</span>
  - <span style="color:#228B22">Defines a named function that can be called anywhere in the scope.</span>
  - **Example:**
    ```js
    function greet(name) {
      return "Hello, " + name + "!";
    }
    console.log(greet("Alice")); // 'Hello, Alice!'
    ```

- <span style="color:#007acc">**Function Expression**</span>
  - <span style="color:#228B22">Defines a function as part of an expression, often assigned to a variable.</span>
  - **Example:**
    ```js
    const add = function(a, b) {
      return a + b;
    };
    console.log(add(2, 3)); // 5
    ```

- <span style="color:#007acc">**Arrow Function**</span>
  - <span style="color:#228B22">A shorter syntax for writing function expressions. Does not have its own 'this'.</span>
  - **Example:**
    ```js
    const multiply = (a, b) => a * b;
    console.log(multiply(3, 4)); // 12
    ```

- <span style="color:#007acc">**Parameters and Arguments**</span>
  - <span style="color:#228B22">Parameters are variables listed in the function definition. Arguments are values passed to the function when called.</span>
  - **Example:**
    ```js
    function sayHello(name) { // 'name' is a parameter
      console.log("Hello, " + name);
    }
    sayHello("Bob"); // 'Bob' is an argument
    ```

- <span style="color:#007acc">**Return Statement**</span>
  - <span style="color:#228B22">The return statement ends function execution and specifies the value to be returned.</span>
  - **Example:**
    ```js
    function square(x) {
      return x * x;
    }
    let result = square(5); // 25
    ```

---

## 📚 Arrays & Array Methods

- <span style="color:#007acc">**Array Creation**</span>
  - <span style="color:#228B22">Arrays are used to store multiple values in a single variable.</span>
  - **Example:**
    ```js
    let fruits = ["apple", "banana", "cherry"];
    ```

- <span style="color:#007acc">**.push(item)**</span>
  - <span style="color:#228B22">Adds an item to the end of the array.</span>
  - **Example:**
    ```js
    fruits.push("orange");
    // ['apple', 'banana', 'cherry', 'orange']
    ```

- <span style="color:#007acc">**.pop()**</span>
  - <span style="color:#228B22">Removes and returns the last item from the array.</span>
  - **Example:**
    ```js
    let last = fruits.pop();
    // last: 'orange', fruits: ['apple', 'banana', 'cherry']
    ```

- <span style="color:#007acc">**.shift()**</span>
  - <span style="color:#228B22">Removes and returns the first item from the array.</span>
  - **Example:**
    ```js
    let first = fruits.shift();
    // first: 'apple', fruits: ['banana', 'cherry']
    ```

- <span style="color:#007acc">**.unshift(item)**</span>
  - <span style="color:#228B22">Adds an item to the beginning of the array.</span>
  - **Example:**
    ```js
    fruits.unshift("mango");
    // ['mango', 'banana', 'cherry']
    ```

- <span style="color:#007acc">**.splice(start, deleteCount, ...items)**</span>
  - <span style="color:#228B22">Adds/removes items at a specific index.</span>
  - **Example:**
    ```js
    fruits.splice(1, 1, "kiwi");
    // Removes 1 item at index 1 and adds 'kiwi': ['mango', 'kiwi', 'cherry']
    ```

- <span style="color:#007acc">**.slice(start, end)**</span>
  - <span style="color:#228B22">Returns a shallow copy of a portion of the array (does not modify original).</span>
  - **Example:**
    ```js
    let someFruits = fruits.slice(0, 2);
    // ['mango', 'kiwi']
    ```

- <span style="color:#007acc">**.concat(array2)**</span>
  - <span style="color:#228B22">Combines two or more arrays and returns a new array.</span>
  - **Example:**
    ```js
    let moreFruits = ["pear", "grape"];
    let allFruits = fruits.concat(moreFruits);
    // ['mango', 'kiwi', 'cherry', 'pear', 'grape']
    ```

- <span style="color:#007acc">**.join(separator)**</span>
  - <span style="color:#228B22">Joins all elements into a string, separated by the specified separator.</span>
  - **Example:**
    ```js
    let str = fruits.join(", ");
    // 'mango, kiwi, cherry'
    ```

- <span style="color:#007acc">**.indexOf(item)**</span>
  - <span style="color:#228B22">Returns the first index of the item, or -1 if not found.</span>
  - **Example:**
    ```js
    let idx = fruits.indexOf("kiwi");
    // 1
    ```

- <span style="color:#007acc">**.includes(item)**</span>
  - <span style="color:#228B22">Checks if the array contains the item. Returns true or false.</span>
  - **Example:**
    ```js
    fruits.includes("cherry");
    // true
    ```

- <span style="color:#007acc">**.forEach(callback)**</span>
  - <span style="color:#228B22">Executes a function for each array element.</span>
  - **Example:**
    ```js
    fruits.forEach(function(fruit) {
      console.log(fruit);
    });
    // Output: mango kiwi cherry
    ```

---

## 🏗️ Objects

- <span style="color:#007acc">**Object Creation**</span>
  - <span style="color:#228B22">Objects are used to store key-value pairs. They can contain various data types.</span>
  - **Example:**
    ```js
    let person = {
      name: "John",
      age: 30,
      isStudent: false,
      hobbies: ["reading", "gaming"],
      address: {
        street: "123 Main St",
        city: "New York"
      }
    };
    ```

- <span style="color:#007acc">**Accessing Properties**</span>
  - <span style="color:#228B22">You can access object properties using dot notation or bracket notation.</span>
  - **Example:**
    ```js
    console.log(person.name);        // 'John'
    console.log(person["age"]);      // 30
    console.log(person.address.city); // 'New York'
    ```

- <span style="color:#007acc">**Adding/Modifying Properties**</span>
  - <span style="color:#228B22">You can add new properties or modify existing ones.</span>
  - **Example:**
    ```js
    person.email = "john@example.com";
    person.age = 31;
    person["phone"] = "555-1234";
    ```

- <span style="color:#007acc">**Object Methods**</span>
  - <span style="color:#228B22">Objects can contain functions as properties (methods).</span>
  - **Example:**
    ```js
    let calculator = {
      add: function(a, b) {
        return a + b;
      },
      subtract(a, b) {
        return a - b;
      }
    };
    
    console.log(calculator.add(5, 3));      // 8
    console.log(calculator.subtract(10, 4)); // 6
    ```

- <span style="color:#007acc">**Nested Objects**</span>
  - <span style="color:#228B22">Objects can contain other objects as properties.</span>
  - **Example:**
    ```js
    let company = {
      name: "Tech Corp",
      employees: {
        manager: {
          name: "Alice",
          salary: 75000
        },
        developer: {
          name: "Bob",
          salary: 65000
        }
      }
    };
    
    console.log(company.employees.manager.name); // 'Alice'
    ```

- <span style="color:#007acc">**Object Destructuring**</span>
  - <span style="color:#228B22">Extract values from objects into variables.</span>
  - **Example:**
    ```js
    let { name, age } = person;
    console.log(name); // 'John'
    console.log(age);  // 31
    
    // With default values
    let { name: fullName, country = "USA" } = person;
    console.log(fullName); // 'John'
    console.log(country);  // 'USA'
    ```

- <span style="color:#007acc">**Object Methods (Built-in)**</span>
  - <span style="color:#228B22">Common methods for working with objects.</span>
  - **Example:**
    ```js
    let keys = Object.keys(person);
    console.log(keys); // ['name', 'age', 'isStudent', 'hobbies', 'address']
    
    let values = Object.values(person);
    console.log(values); // ['John', 31, false, ['reading', 'gaming'], {...}]
    
    let entries = Object.entries(person);
    console.log(entries); // [['name', 'John'], ['age', 31], ...]
    ```

- <span style="color:#007acc">**Spread Operator with Objects**</span>
  - <span style="color:#228B22">Create new objects by spreading existing ones.</span>
  - **Example:**
    ```js
    let personCopy = { ...person };
    let personWithJob = { ...person, job: "Developer" };
    let updatedPerson = { ...person, age: 32 };
    ```

---

## 🧩 Object Inheritance

- <span style="color:#007acc">**Object Inheritance**</span>
  - <span style="color:#228B22">JavaScript uses prototype-based inheritance. Objects can inherit properties and methods from other objects.</span>
  - **Example:**
    ```js
    // Parent object
    let animal = {
      name: "Animal",
      speak() {
        return `${this.name} makes a sound`;
      }
    };
    
    // Child object inheriting from animal
    let dog = Object.create(animal);
    dog.name = "Dog";
    dog.bark() {
      return "Woof!";
    }
    
    console.log(dog.speak()); // 'Dog makes a sound'
    console.log(dog.bark());  // 'Woof!'
    ```

- <span style="color:#007acc">**Constructor Functions**</span>
  - <span style="color:#228B22">Functions used to create objects with shared properties and methods.</span>
  - **Example:**
    ```js
    function Person(name, age) {
      this.name = name;
      this.age = age;
    }
    
    Person.prototype.greet = function() {
      return `Hello, I'm ${this.name}`;
    };
    
    let person1 = new Person("Alice", 25);
    let person2 = new Person("Bob", 30);
    
    console.log(person1.greet()); // 'Hello, I'm Alice'
    console.log(person2.greet()); // 'Hello, I'm Bob'
    ```

- <span style="color:#007acc">**Class Inheritance**</span>
  - <span style="color:#228B22">ES6 classes provide a cleaner syntax for inheritance.</span>
  - **Example:**
    ```js
    class Vehicle {
      constructor(brand, model) {
        this.brand = brand;
        this.model = model;
      }
      
      getInfo() {
        return `${this.brand} ${this.model}`;
      }
    }
    
    class Car extends Vehicle {
      constructor(brand, model, year) {
        super(brand, model); // Call parent constructor
        this.year = year;
      }
      
      getFullInfo() {
        return `${this.getInfo()} (${this.year})`;
      }
    }
    
    let myCar = new Car("Toyota", "Camry", 2020);
    console.log(myCar.getFullInfo()); // 'Toyota Camry (2020)'
    ```

- <span style="color:#007acc">**Method Overriding**</span>
  - <span style="color:#228B22">Child classes can override parent methods.</span>
  - **Example:**
    ```js
    class Animal {
      speak() {
        return "Some sound";
      }
    }
    
    class Dog extends Animal {
      speak() {
        return "Woof!";
      }
    }
    
    class Cat extends Animal {
      speak() {
        return "Meow!";
      }
    }
    
    let dog = new Dog();
    let cat = new Cat();
    
    console.log(dog.speak()); // 'Woof!'
    console.log(cat.speak()); // 'Meow!'
    ```

- <span style="color:#007acc">**Prototype Chain**</span>
  - <span style="color:#228B22">JavaScript looks up properties through the prototype chain.</span>
  - **Example:**
    ```js
    let parent = {
      value: 42,
      getValue() {
        return this.value;
      }
    };
    
    let child = Object.create(parent);
    child.value = 100;
    
    let grandchild = Object.create(child);
    
    console.log(grandchild.getValue()); // 100 (from child)
    console.log(grandchild.hasOwnProperty('value')); // false
    console.log(child.hasOwnProperty('value')); // true
    ```

- <span style="color:#007acc">**Multiple Inheritance (Mixins)**</span>
  - <span style="color:#228B22">Combine multiple objects to create complex inheritance.</span>
  - **Example:**
    ```js
    let canFly = {
      fly() {
        return "Flying high!";
      }
    };
    
    let canSwim = {
      swim() {
        return "Swimming deep!";
      }
    };
    
    let duck = Object.assign({}, canFly, canSwim);
    duck.name = "Donald";
    
    console.log(duck.fly());  // 'Flying high!'
    console.log(duck.swim()); // 'Swimming deep!'
    ```

---

## 👨‍👩‍👧‍👦 Parent-Child Class Relationships

- <span style="color:#007acc">**Basic Inheritance**</span>
  - <span style="color:#228B22">Child classes inherit properties and methods from parent classes. The 'extends' keyword creates this relationship.</span>
  - **Example:**
    ```js
    class Animal {
      constructor(name, species) {
        this.name = name;
        this.species = species;
        this.isAlive = true;
      }
      
      eat() {
        return `${this.name} is eating`;
      }
      
      sleep() {
        return `${this.name} is sleeping`;
      }
      
      getInfo() {
        return `Name: ${this.name}, Species: ${this.species}`;
      }
    }
    
    class Dog extends Animal {
      constructor(name, breed) {
        super(name, "Canis"); // Call parent constructor
        this.breed = breed;
        this.legs = 4;
      }
      
      bark() {
        return `${this.name} says: Woof!`;
      }
      
      fetch() {
        return `${this.name} fetches the ball`;
      }
    }
    
    let myDog = new Dog("Buddy", "Golden Retriever");
    console.log(myDog.getInfo()); // 'Name: Buddy, Species: Canis'
    console.log(myDog.eat());     // 'Buddy is eating'
    console.log(myDog.bark());    // 'Buddy says: Woof!'
    ```

- <span style="color:#007acc">**Method Overriding**</span>
  - <span style="color:#228B22">Child classes can override parent methods to provide different behavior while keeping the same method name.</span>
  - **Example:**
    ```js
    class Vehicle {
      constructor(brand, model) {
        this.brand = brand;
        this.model = model;
        this.isRunning = false;
      }
      
      start() {
        this.isRunning = true;
        return `${this.brand} ${this.model} is starting`;
      }
      
      stop() {
        this.isRunning = false;
        return `${this.brand} ${this.model} is stopping`;
      }
      
      getInfo() {
        return `${this.brand} ${this.model} (Running: ${this.isRunning})`;
      }
    }
    
    class Car extends Vehicle {
      constructor(brand, model, year) {
        super(brand, model);
        this.year = year;
        this.doors = 4;
      }
      
      // Override parent method
      start() {
        super.start(); // Call parent method first
        return `${this.brand} ${this.model} engine is running smoothly`;
      }
      
      // Add new method specific to Car
      honk() {
        return `${this.brand} ${this.model} honks: Beep! Beep!`;
      }
      
      // Override getInfo with additional car-specific info
      getInfo() {
        return `${super.getInfo()}, Year: ${this.year}, Doors: ${this.doors}`;
      }
    }
    
    class Motorcycle extends Vehicle {
      constructor(brand, model, engineSize) {
        super(brand, model);
        this.engineSize = engineSize;
        this.wheels = 2;
      }
      
      // Override with motorcycle-specific behavior
      start() {
        super.start();
        return `${this.brand} ${this.model} engine is revving loudly`;
      }
      
      wheelie() {
        return `${this.brand} ${this.model} does a wheelie!`;
      }
    }
    
    let car = new Car("Toyota", "Camry", 2020);
    let bike = new Motorcycle("Honda", "CBR", "600cc");
    
    console.log(car.start());   // 'Toyota Camry engine is running smoothly'
    console.log(bike.start());  // 'Honda CBR engine is revving loudly'
    console.log(car.honk());    // 'Toyota Camry honks: Beep! Beep!'
    console.log(bike.wheelie()); // 'Honda CBR does a wheelie!'
    ```

- <span style="color:#007acc">**Constructor Chaining**</span>
  - <span style="color:#228B22">Child constructors must call parent constructors using super() before accessing 'this'.</span>
  - **Example:**
    ```js
    class Employee {
      constructor(name, id, salary) {
        this.name = name;
        this.id = id;
        this.salary = salary;
        this.department = "General";
      }
      
      work() {
        return `${this.name} is working`;
      }
      
      getSalary() {
        return `$${this.salary}`;
      }
    }
    
    class Manager extends Employee {
      constructor(name, id, salary, teamSize) {
        super(name, id, salary); // Must call super() first
        this.teamSize = teamSize;
        this.department = "Management";
      }
      
      manage() {
        return `${this.name} is managing ${this.teamSize} employees`;
      }
      
      // Override with bonus calculation
      getSalary() {
        const bonus = this.salary * 0.2;
        return `$${this.salary + bonus} (including 20% bonus)`;
      }
    }
    
    class Developer extends Employee {
      constructor(name, id, salary, programmingLanguage) {
        super(name, id, salary);
        this.programmingLanguage = programmingLanguage;
        this.department = "Engineering";
      }
      
      code() {
        return `${this.name} is coding in ${this.programmingLanguage}`;
      }
    }
    
    let manager = new Manager("Alice", "M001", 80000, 5);
    let developer = new Developer("Bob", "D001", 70000, "JavaScript");
    
    console.log(manager.manage());     // 'Alice is managing 5 employees'
    console.log(developer.code());     // 'Bob is coding in JavaScript'
    console.log(manager.getSalary());  // '$96000 (including 20% bonus)'
    console.log(developer.getSalary()); // '$70000'
    ```

- <span style="color:#007acc">**Multi-level Inheritance**</span>
  - <span style="color:#228B22">Classes can inherit from classes that inherit from other classes, creating an inheritance chain.</span>
  - **Example:**
    ```js
    class LivingThing {
      constructor(name) {
        this.name = name;
        this.isAlive = true;
      }
      
      breathe() {
        return `${this.name} is breathing`;
      }
    }
    
    class Animal extends LivingThing {
      constructor(name, species) {
        super(name);
        this.species = species;
        this.legs = 4;
      }
      
      move() {
        return `${this.name} is moving`;
      }
    }
    
    class Dog extends Animal {
      constructor(name, breed) {
        super(name, "Canis");
        this.breed = breed;
      }
      
      bark() {
        return `${this.name} barks: Woof!`;
      }
      
      // Override move with dog-specific behavior
      move() {
        return `${this.name} runs on ${this.legs} legs`;
      }
    }
    
    class Puppy extends Dog {
      constructor(name, breed, age) {
        super(name, breed);
        this.age = age;
        this.isTrained = false;
      }
      
      play() {
        return `${this.name} is playing with toys`;
      }
      
      // Override bark with puppy-specific behavior
      bark() {
        return `${this.name} barks softly: Yip! Yip!`;
      }
    }
    
    let puppy = new Puppy("Max", "Golden Retriever", 6);
    console.log(puppy.breathe()); // 'Max is breathing' (from LivingThing)
    console.log(puppy.move());    // 'Max runs on 4 legs' (from Animal, overridden by Dog)
    console.log(puppy.bark());    // 'Max barks softly: Yip! Yip!' (overridden by Puppy)
    console.log(puppy.play());    // 'Max is playing with toys' (Puppy-specific)
    ```

- <span style="color:#007acc">**The 'super' Keyword**</span>
  - <span style="color:#228B22">'super' is used to call parent class methods and constructor. It's essential for proper inheritance.</span>
  - **Example:**
    ```js
    class BankAccount {
      constructor(owner, balance = 0) {
        this.owner = owner;
        this.balance = balance;
        this.accountNumber = this.generateAccountNumber();
      }
      
      generateAccountNumber() {
        return Math.floor(Math.random() * 1000000);
      }
      
      deposit(amount) {
        this.balance += amount;
        return `Deposited $${amount}. Balance: $${this.balance}`;
      }
      
      withdraw(amount) {
        if (amount <= this.balance) {
          this.balance -= amount;
          return `Withdrew $${amount}. Balance: $${this.balance}`;
        }
        return "Insufficient funds";
      }
      
      getInfo() {
        return `Account: ${this.accountNumber}, Owner: ${this.owner}, Balance: $${this.balance}`;
      }
    }
    
    class SavingsAccount extends BankAccount {
      constructor(owner, balance, interestRate = 0.02) {
        super(owner, balance); // Call parent constructor
        this.interestRate = interestRate;
        this.accountType = "Savings";
      }
      
      addInterest() {
        const interest = this.balance * this.interestRate;
        this.balance += interest;
        return `Added $${interest.toFixed(2)} interest. New balance: $${this.balance}`;
      }
      
      // Override withdraw with minimum balance requirement
      withdraw(amount) {
        const minBalance = 100;
        if (this.balance - amount >= minBalance) {
          return super.withdraw(amount); // Call parent method
        }
        return `Cannot withdraw. Minimum balance of $${minBalance} required`;
      }
      
      // Override getInfo with additional savings info
      getInfo() {
        return `${super.getInfo()}, Type: ${this.accountType}, Interest Rate: ${this.interestRate * 100}%`;
      }
    }
    
    let savings = new SavingsAccount("John", 1000, 0.03);
    console.log(savings.getInfo());     // Account info with savings details
    console.log(savings.addInterest()); // 'Added $30.00 interest. New balance: $1030'
    console.log(savings.withdraw(50));  // 'Withdrew $50. Balance: $980'
    console.log(savings.withdraw(900)); // 'Cannot withdraw. Minimum balance of $100 required'
    ```

---

## 🏛️ Classes

- <span style="color:#007acc">**Class Declaration**</span>
  - <span style="color:#228B22">Classes are templates for creating objects. They provide a cleaner syntax for constructor functions.</span>
  - **Example:**
    ```js
    class Person {
      constructor(name, age) {
        this.name = name;
        this.age = age;
      }
      
      greet() {
        return `Hello, I'm ${this.name}`;
      }
    }
    
    let person = new Person("Alice", 25);
    console.log(person.greet()); // 'Hello, I'm Alice'
    ```

- <span style="color:#007acc">**Constructor Method**</span>
  - <span style="color:#228B22">The constructor method is called when a new instance is created. It initializes object properties.</span>
  - **Example:**
    ```js
    class Car {
      constructor(brand, model, year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
        this.isRunning = false;
      }
    }
    
    let myCar = new Car("Toyota", "Camry", 2020);
    console.log(myCar.brand); // 'Toyota'
    ```

- <span style="color:#007acc">**Instance Methods**</span>
  - <span style="color:#228B22">Methods that belong to instances of the class.</span>
  - **Example:**
    ```js
    class BankAccount {
      constructor(owner, balance = 0) {
        this.owner = owner;
        this.balance = balance;
      }
      
      deposit(amount) {
        this.balance += amount;
        return `Deposited $${amount}. New balance: $${this.balance}`;
      }
      
      withdraw(amount) {
        if (amount <= this.balance) {
          this.balance -= amount;
          return `Withdrew $${amount}. New balance: $${this.balance}`;
        } else {
          return "Insufficient funds";
        }
      }
    }
    
    let account = new BankAccount("John", 1000);
    console.log(account.deposit(500)); // 'Deposited $500. New balance: $1500'
    console.log(account.withdraw(200)); // 'Withdrew $200. New balance: $1300'
    ```

- <span style="color:#007acc">**Static Methods**</span>
  - <span style="color:#228B22">Methods that belong to the class itself, not instances. Called on the class, not objects.</span>
  - **Example:**
    ```js
    class MathUtils {
      static add(a, b) {
        return a + b;
      }
      
      static multiply(a, b) {
        return a * b;
      }
      
      static isEven(num) {
        return num % 2 === 0;
      }
    }
    
    console.log(MathUtils.add(5, 3));      // 8
    console.log(MathUtils.multiply(4, 6)); // 24
    console.log(MathUtils.isEven(10));     // true
    ```

- <span style="color:#007acc">**Getters and Setters**</span>
  - <span style="color:#228B22">Special methods that allow you to get and set property values with additional logic.</span>
  - **Example:**
    ```js
    class Circle {
      constructor(radius) {
        this._radius = radius;
      }
      
      get radius() {
        return this._radius;
      }
      
      set radius(value) {
        if (value > 0) {
          this._radius = value;
        } else {
          throw new Error("Radius must be positive");
        }
      }
      
      get area() {
        return Math.PI * this._radius ** 2;
      }
    }
    
    let circle = new Circle(5);
    console.log(circle.radius); // 5
    console.log(circle.area);   // 78.54...
    circle.radius = 10;
    console.log(circle.area);   // 314.16...
    ```

- <span style="color:#007acc">**Class Inheritance**</span>
  - <span style="color:#228B22">Classes can inherit from other classes using the extends keyword.</span>
  - **Example:**
    ```js
    class Animal {
      constructor(name) {
        this.name = name;
      }
      
      speak() {
        return `${this.name} makes a sound`;
      }
    }
    
    class Dog extends Animal {
      constructor(name, breed) {
        super(name); // Call parent constructor
        this.breed = breed;
      }
      
      speak() {
        return `${this.name} barks: Woof!`;
      }
      
      fetch() {
        return `${this.name} fetches the ball`;
      }
    }
    
    let dog = new Dog("Buddy", "Golden Retriever");
    console.log(dog.speak()); // 'Buddy barks: Woof!'
    console.log(dog.fetch()); // 'Buddy fetches the ball'
    ```

- <span style="color:#007acc">**Private Fields (ES2022)**</span>
  - <span style="color:#228B22">Private fields are only accessible within the class.</span>
  - **Example:**
    ```js
    class BankAccount {
      #balance = 0; // Private field
      
      constructor(owner) {
        this.owner = owner;
      }
      
      deposit(amount) {
        this.#balance += amount;
        return `Balance: $${this.#balance}`;
      }
      
      getBalance() {
        return this.#balance;
      }
    }
    
    let account = new BankAccount("John");
    console.log(account.deposit(100)); // 'Balance: $100'
    console.log(account.getBalance());  // 100
    // console.log(account.#balance); // Error: Private field
    ```

---
