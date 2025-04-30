// ==========================
// Scope
// ==========================

// 'var' has function scope, not block scope. That's why the variable outside isn't changed.
var lang = "Bangla";

function learn(topic){
    var lang = topic; // This 'lang' is function scoped (not global).
    console.log(`I'm learning ${topic}`);
}
learn("Javascript");
console.log(`I know ${lang}`); // Output: I know Bangla (original value remains unchanged)

/*
🔔 Note:
- 'var' is hoisted and function-scoped.
- Avoid using 'var' in modern JavaScript.

✅ Tip:
Use `let` and `const` instead of `var` to avoid scope-related bugs.
*/

// ==========================
// Function Types
// ==========================

// ✅ Regular Function Declaration
function hello(){
    console.log("Hello World");
}
hello();

let msg = hello(); // returns undefined because hello() has no return statement
console.log(msg); // Output: undefined

/*
💡 Note:
- Regular functions are hoisted (can be called before their declaration).
*/

// ✅ Function Expression
const hello = function(){
    console.log("Hello World");
};
hello();

/*
🧠 Tip:
- Function expressions are NOT hoisted.
- Useful when passing functions as values or arguments.
*/
// ✅ Named Function Expression
const hello = function hello(){
    console.log("Hello World");
};
hello();

/*
📌 Exclusive:
- The internal name `hello` is available only inside the function body (useful for recursion or debugging).
*/
// ✅ Arrow Function
const hello = () => {
    console.log("Hello World");
};
hello();

/*
🚀 Tip:
- Arrow functions are concise and do NOT have their own 'this'.
- Best used for short callbacks or functions without complex behavior.
*/
// ✅ Arrow Function returning an Object
const hello = () => ({
    a: 5,
    b: 6,
});
console.log(hello());

/*
❗ Important:
- When returning an object from an arrow function, wrap it in parentheses to avoid syntax errors.
*/
// ✅ Anonymous Function returning another function
function hello(){
    return function(){
        console.log("Hello World");
    };
}

const greet = hello();
greet();

/*
🔄 Tip:
- This is a common pattern for closures and higher-order functions.
- Useful in event handling, currying, and creating private variables.
*/

// =========================
// 📌 Event Handler Example
// =========================

// Select the button element from the DOM
const button = document.getElementById("button");

// Define the event handler function
function hello(){
    console.log("Hello World");
}

// Attach the event handler to the button's click event
button.addEventListener("click", hello);

/*
✅ What’s Happening:
- You're selecting an HTML element with the id "button".
- You define a function called `hello`.
- You use `addEventListener` to run `hello` when the button is clicked.

🧠 Why use addEventListener?
- It allows multiple event listeners on the same element.
- More flexible than using onclick (inline or DOM property).
*/

// ✅ Equivalent HTML (for demo/testing):
// <button id="button">Click Me</button>


// ===============================
// 🌟 Primitive Type Example
// ===============================
let x = 5;
let y = 6;

x = y;   // x gets a copy of y's value (6)
y = 7;   // only y is updated

console.log(x); // 6
console.log(y); // 7

/*
✅ Explanation:
- Primitive types (Number, String, Boolean, null, undefined, Symbol, BigInt) are **copied by value**.
- When you assign x = y, x gets a **new copy** of y's value.
- Changing y later does **not affect** x.

💡 Tip:
Primitive values are stored in the stack, and each variable keeps its own copy.
*/
// ===============================
// 🌟 Reference Type Example
// ===============================
let a = ["JS", "Python"];
let b = ["HTML", "CSS"];

b = a; // b now points to the same array as a

console.log(a); // ["JS", "Python"]
console.log(b); // ["JS", "Python"]

a.push("Go"); // Modifies the shared array

console.log(a); // ["JS", "Python", "Go"]
console.log(b); // ["JS", "Python", "Go"]

/*
✅ Explanation:
- Arrays (and objects) are **reference types**.
- When you do b = a, both variables point to the **same memory location**.
- Any change via one reference reflects in the other.

📌 Important:
Reference types are stored in the heap. The variable holds a **reference (pointer)** to the memory location.

🚨 Warning:
If you need a copy of an array/object, use spread operator or slice:
   let copy = [...a];   OR   let copy = a.slice();
*/

// ==========================
// ✅ Array Methods Explained
// ==========================

const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];

// 1️⃣ find()
const found = fruits.find(f => f === "Orange");
console.log(found); // Output: Orange

/*
🧠 `find()` returns the **first** element that matches the condition.
Returns `undefined` if no match is found.
*/

// 2️⃣ findIndex()
const foundIndex = fruits.findIndex(f => f === "Orange");
console.log(foundIndex); // Output: 1

/*
💡 `findIndex()` returns the index of the first matching element.
*/

// 3️⃣ filter()
const filtered = fruits.filter(f => f === "Orange" || f === "Mango");
console.log(filtered); // Output: ["Orange", "Mango"]

/*
💡 `filter()` returns **all** elements that match the condition.
Always returns a new array.
*/

// 4️⃣ slice()
const sliced = fruits.slice(2, 4);
console.log(sliced); // Output: ["Lemon", "Apple"]

/*
🧠 `slice(start, end)` extracts a section of the array (non-destructive).
Returns a new array.
*/

// 5️⃣ splice()
const spliced = fruits.splice(2, 2);
console.log(spliced); // Output: ["Lemon", "Apple"]
console.log(fruits);  // Modified array: ["Banana", "Orange", "Mango"]

/*
⚠️ `splice()` **modifies** the original array and returns the removed items.
*/

// 6️⃣ concat()
const concatResult = fruits.concat("Fruit 1", "Fruit 2");
console.log(concatResult); // ["Banana", "Orange", "Mango", "Fruit 1", "Fruit 2"]

/*
✅ `concat()` returns a new array, does not change original.
*/

// 7️⃣ push()
const pushResult = fruits.push("Fruit 1", "Fruit 2");
console.log(pushResult); // Output: new length of array
console.log(fruits);     // Array is modified

/*
🧠 `push()` adds items to the end of the array, modifies original, and returns new length.
*/

// 8️⃣ map()
const mapResult = fruits.map(f => {
    if (f === "Apple") {
        return "Apple";
    } else {
        return "N/A";
    }
});
console.log(mapResult);

/*
✅ `map()` returns a new array after applying a function to each element.
Very useful for transformations.
*/
const numbers = [1, 2, 3, 4, 5];

const total = numbers.reduce((acc, curr) => {
    return acc + curr; // Must return the result!
}, 0);

console.log(total); // Output: 15

/*
⚠️ Common mistake: forgetting to return inside reduce().
*/
// ✅ for...of (used for arrays)
for (const num of numbers) {
    console.log(num);
}
// ✅ forEach() (also for arrays)
numbers.forEach(num => {
    console.log(num);
});
// ✅ for...in (used for objects)
const lang = {
    name: "js",
    year: 1995,
    creator: "Me"
};

for (const key in lang) {
    console.log(lang[key]); // prints values
}



