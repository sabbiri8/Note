```markdown
# 📘 জাভাস্ক্রিপ্টের মূল ধারণা

এই ডকুমেন্টে আলোচনা করা হয়েছে জাভাস্ক্রিপ্টের গুরুত্বপূর্ণ কিছু মৌলিক ধারণা যেমন: স্কোপ, ফাংশনের ধরন, ইভেন্ট হ্যান্ডলিং, প্রিমিটিভ ও রেফারেন্স টাইপ, এবং সাধারণ অ্যারের মেথড।

---

## 🔍 স্কোপ (Scope)

স্কোপ মানে ভ্যারিয়েবল কোথায় অ্যাক্সেসযোগ্য — এটি নির্ভর করে আপনি কীভাবে ও কোথায় ভ্যারিয়েবলটি ডিক্লেয়ার করেছেন।

```javascript
var lang = "Bangla";

function learn(topic){
    var lang = topic;
    console.log(`আমি ${topic} শিখছি`);
}

learn("Javascript");
console.log(`আমি ${lang} জানি`);
```

📌 **মনে রাখবেন:**
- `var` ফাংশন-স্কোপড, ব্লক-স্কোপড নয়।
- আধুনিক জাভাস্ক্রিপ্টে `let` ও `const` ব্যবহার করা উত্তম।
- `let` ও `const` ব্লক-স্কোপড ও হোয়িস্টেড হলেও টেম্পোরাল ডেড জোন থাকে।

---

## 🧠 ফাংশনের প্রকারভেদ

জাভাস্ক্রিপ্টে ফাংশন লেখার একাধিক উপায় রয়েছে।

### ✅ ১. রেগুলার ফাংশন (Function Declaration)

```javascript
function hello(){
    console.log("হ্যালো ওয়ার্ল্ড");
}
hello();
```

✔️ হোয়িস্টেড হয় — আগে ডিফাইন না করেও কল করা যায়।

---

### ✅ ২. ফাংশন এক্সপ্রেশন

```javascript
const hello = function(){
    console.log("হ্যালো ওয়ার্ল্ড");
};
hello();
```

⚠️ হোয়িস্টেড নয় — ডিফাইন করার আগে কল করলে এরর দিবে।

---

### ✅ ৩. নেমড ফাংশন এক্সপ্রেশন

```javascript
const hello = function hello(){
    console.log("হ্যালো ওয়ার্ল্ড");
};
hello();
```

📌 ভিতরের `hello` নামটি শুধুমাত্র ফাংশনের ভিতরেই কাজ করে।

---

### ✅ ৪. অ্যারো ফাংশন (Arrow Function)

```javascript
const hello = () => {
    console.log("হ্যালো ওয়ার্ল্ড");
};
hello();
```

💡 সংক্ষিপ্ত এবং নিজস্ব `this` নেই। উপযুক্ত ছোট কলব্যাকের জন্য।

---

### ✅ ৫. অবজেক্ট রিটার্ন করা অ্যারো ফাংশন

```javascript
const hello = () => ({ a: 5, b: 6 });
console.log(hello());
```

⚠️ অবজেক্ট রিটার্ন করতে হলে `{}` ব্র্যাকেট প্রয়োজন।

---

### ✅ ৬. হাই-অর্ডার ফাংশন (ফাংশন থেকে ফাংশন রিটার্ন)

```javascript
function hello(){
    return function(){
        console.log("হ্যালো ওয়ার্ল্ড");
    };
}
const greet = hello();
greet();
```

📌 ক্লোজার, কারিইং ও প্রাইভেট ডেটা তৈরির জন্য ব্যবহৃত হয়।

---

## 🖱️ ইভেন্ট হ্যান্ডলিং (Event Handling)

```javascript
const button = document.getElementById("button");

function hello(){
    console.log("হ্যালো ওয়ার্ল্ড");
}

if (button) {
    button.addEventListener("click", hello);
}
```

📌 `addEventListener` ব্যবহার করলে একাধিক ইভেন্ট হ্যান্ডলার যোগ করা যায়।

🔗 সমতুল্য HTML:
```html
<button id="button">আমাকে ক্লিক করুন</button>
```

---

## 📦 প্রিমিটিভ বনাম রেফারেন্স টাইপ

### 🧊 প্রিমিটিভ টাইপ

```javascript
let x = 5;
let y = x;
y = 10;

console.log(x); // 5
console.log(y); // 10
```

✔️ ভ্যালু কপি হয়।

---

### 🧠 রেফারেন্স টাইপ

```javascript
let a = ["JS", "Python"];
let b = a;

a.push("Go");

console.log(b); // ["JS", "Python", "Go"]
```

⚠️ রেফারেন্স কপি হয়। একটি পরিবর্তন হলে আরেকটিও পরিবর্তিত হয়।

✅ কপি করতে:
```javascript
let copy = [...a];
// অথবা
let copy = a.slice();
```

---


---

## 🧾 জাভাস্ক্রিপ্ট অ্যারে

অ্যারে হলো একধরনের ডেটা স্ট্রাকচার যেখানে একাধিক ভ্যালু একটি তালিকার আকারে রাখা যায়। জাভাস্ক্রিপ্ট অ্যারে `[]` ব্র্যাকেট দিয়ে তৈরি হয় এবং বিভিন্ন ডেটা টাইপ এর মধ্যে রাখা যায়।

```javascript
const fruits = ["Apple", "Mango", "Banana"];
```

### 🔍 অ্যারে সম্পর্কিত মূল বিষয়গুলো:
- অ্যারে **0-ভিত্তিক ইনডেক্সড**: অর্থাৎ প্রথম আইটেমের ইনডেক্স 0।
- অ্যারে **অর্ডারড**: ইনপুট অনুযায়ী এলিমেন্ট সাজানো থাকে।
- অ্যারে **মিউটেবল**: এর ভ্যালু পরিবর্তন বা নতুন ভ্যালু যোগ করা যায়।

---

### ✅ অ্যারের গুরুত্বপূর্ণ মেথডসমূহ 

---

#### 1️⃣ **`find()`**

**ব্যবহার:** শর্তের সাথে প্রথম ম্যাচিং আইটেম রিটার্ন করে।

```javascript
const fruits = ["Banana", "Orange", "Apple"];
const found = fruits.find(fruit => fruit === "Apple");
console.log(found); // আউটপুট: Apple
```

🔎 **বিস্তারিত:**
- প্রথম ম্যাচ পেলে থেমে যায়।
- যদি কিছু না মেলে, `undefined` রিটার্ন করে।

---

#### 2️⃣ **`findIndex()`**

**ব্যবহার:** শর্তের সাথে মিলে এমন প্রথম আইটেমের ইনডেক্স রিটার্ন করে।

```javascript
const index = fruits.findIndex(fruit => fruit === "Orange");
console.log(index); // আউটপুট: 1
```

📌 **উপকারিতা:** ইনডেক্স জানার প্রয়োজন হলে এটি ব্যবহার করা হয়।

---

#### 3️⃣ **`filter()`**

**ব্যবহার:** শর্ত পূরণ করে এমন সব এলিমেন্টের একটি নতুন অ্যারে রিটার্ন করে।

```javascript
const selected = fruits.filter(fruit => fruit.includes("a"));
console.log(selected); // আউটপুট: ["Banana", "Orange"]
```

🌱 **টিপস:** সব মিল থাকা আইটেমের লিস্ট দরকার হলে `filter()` ব্যবহার করুন।

---

#### 4️⃣ **`slice()`**

**ব্যবহার:** নির্দিষ্ট অংশের একটি কপি তৈরি করে (মূল অ্যারে অপরিবর্তিত থাকে)।

```javascript
const sliced = fruits.slice(1, 3);
console.log(sliced); // আউটপুট: ["Orange", "Apple"]
```

📌 **মনে রাখুন:**
- `start` ইনডেক্স থেকে শুরু হয়।
- `end` ইনডেক্স পর্যন্ত নেয় না (excludes it)।

---

#### 5️⃣ **`splice()`**

**ব্যবহার:** মূল অ্যারে থেকে এলিমেন্ট সরানো বা যোগ করার জন্য।

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const removed = fruits.splice(1, 2);
console.log(removed); // ["Orange", "Apple"]
console.log(fruits);  // ["Banana", "Mango"]
```

⚠️ **সতর্কতা:** এটি **মূল অ্যারে পরিবর্তন করে**।

---

#### 6️⃣ **`concat()`**

**ব্যবহার:** দুটি বা ততোধিক অ্যারে/আইটেম একত্র করে একটি নতুন অ্যারে তৈরি করে।

```javascript
const moreFruits = fruits.concat("Guava", "Papaya");
console.log(moreFruits);
```

✅ **টিপস:** মূল অ্যারে অপরিবর্তিত থাকে।

---

#### 7️⃣ **`push()`**

**ব্যবহার:** অ্যারের শেষে নতুন আইটেম যোগ করে।

```javascript
fruits.push("Litchi");
console.log(fruits);
```

🧠 **মনে রাখুন:** এটি মূল অ্যারেটিকে পরিবর্তন করে এবং নতুন দৈর্ঘ্য রিটার্ন করে।

---

#### 8️⃣ **`map()`**

**ব্যবহার:** প্রতিটি এলিমেন্টের উপর অপারেশন করে একটি নতুন অ্যারে তৈরি করে।

```javascript
const upper = fruits.map(f => f.toUpperCase());
console.log(upper); // ["BANANA", "ORANGE", ...]
```

📘 **ব্যবহার:** ডেটা রূপান্তরের জন্য উপযুক্ত।

---

#### 9️⃣ **`reduce()`**

**ব্যবহার:** একটি অ্যারে থেকে একক ভ্যালু তৈরি করে।

```javascript
const nums = [1, 2, 3, 4];
const sum = nums.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 10
```

⚠️ **সতর্কতা:** `return` না করলে `undefined` আসবে।

---

#### 🔟 **`forEach()` vs `for...of` vs `for...in`**

```javascript
const items = ["JS", "HTML", "CSS"];

// forEach
items.forEach(item => console.log(item));

// for...of
for (let item of items) {
    console.log(item);
}

// for...in (object-এর জন্য উপযুক্ত)
const obj = { lang: "JS", year: 1995 };
for (let key in obj) {
    console.log(key, obj[key]);
}
```

📌 **টিপস:**
- `forEach()` শুধুমাত্র অ্যারের জন্য।
- `for...of` ইটারেবল ডেটার জন্য।
- `for...in` অবজেক্ট প্রপার্টির জন্য।

---

### 🎯 অ্যারে কপি করার উপায়

```javascript
const arr = ["a", "b"];
const shallowCopy1 = [...arr];
const shallowCopy2 = arr.slice();
```

✅ **কারণ:** `=` ব্যবহার করলে রেফারেন্স কপি হয়, যার ফলে মূল অ্যারেও পরিবর্তিত হয়।

---

### 📦 সংক্ষেপে রেফারেন্স টাইপ বনাম প্রিমিটিভ টাইপ

| টাইপ | কপি হয় কীভাবে | সংরক্ষিত হয় | উদাহরণ |
|------|----------------|--------------|---------|
| প্রিমিটিভ | ভ্যালু কপি | Stack | Number, String |
| রেফারেন্স | রেফারেন্স কপি | Heap | Array, Object |

---

---

## 📦 অবজেক্ট (Object)

অবজেক্ট হলো কী-ভ্যালু পেয়ার-ভিত্তিক একটি ডেটা স্ট্রাকচার। জাভাস্ক্রিপ্টে অবজেক্ট ব্যবহার করে কোনো একটি জিনিসের বৈশিষ্ট্য ও মান সংরক্ষণ করা হয়।

```javascript
const language = {
    name: "JS",
    year: 1995,
    creator: "Me"
};
```

### 🔍 অবজেক্টের সাধারণ মেথডসমূহ:

```javascript
console.log(Object.keys(language));     // 🔑 ["name", "year", "creator"]
console.log(Object.values(language));   // 📦 ["JS", 1995, "Me"]
console.log(Object.entries(language));  // 🧾 [["name", "JS"], ["year", 1995], ...]
```

### ➕ নতুন প্রপার্টি যোগ করা:
```javascript
language.popular = "100";
console.log(language);
```

🧠 **নোট:**
- নতুন প্রপার্টি যোগ করা যায় `dot notation` বা `bracket notation` ব্যবহার করে।
- অবজেক্টের প্রপার্টি পরিবর্তন করাও সম্ভব।

---

## 🌟 Spread এবং Rest অপারেটর

### ✅ Spread অপারেটর `...`  
একটি অ্যারে বা অবজেক্টের **shallow copy** তৈরি করতে বা আইটেমগুলোকে আলাদা করতে ব্যবহৃত হয়।

```javascript
const fruits = ["abc", "cde"];
const result = [...fruits];
result.push("efg");

console.log(result); // ["abc", "cde", "efg"]
console.log(fruits); // ["abc", "cde"]
```

📌 Spread অপারেটর কপি করে, মূল ডেটা পরিবর্তন করে না।

---

## 🍎 Array of Object (অবজেক্টের অ্যারে)

```javascript
const fruit = [
    { name: "sabbie" },
    { name: "taki" }
];

const res = [...fruit];
console.log(res);
```

🧠 **গুরুত্বপূর্ণ:**  
এখানে `res` এবং `fruit` এর মধ্যে শ্যালো কপি হয়েছে। মানে:
- অ্যারেটি আলাদা কপি হলেও,
- প্রতিটি অবজেক্টের রেফারেন্স একই রয়ে যায়।

🔍 উদাহরণ:

```javascript
res[0].name = "modified";
console.log(fruit[0].name); // Output: "modified"
```

🎯 যদি সম্পূর্ণ deep copy দরকার হয়, তাহলে JSON কৌশল ব্যবহার করা যায়:

```javascript
const deepCopy = JSON.parse(JSON.stringify(fruit));
```

---

## ⚙️ arguments এবং rest parameter

### 1️⃣ পুরাতন পদ্ধতি: `arguments` অবজেক্ট

```javascript
function sum(a, b) {
    console.log(arguments); // array-like object
    return a + b;
}
sum(3, 4);
```

⚠️ **মনে রাখো:**  
`arguments` কেবল **regular function** এ কাজ করে, **arrow function** এ নয়।

---

### 2️⃣ আধুনিক পদ্ধতি: `rest parameter`

```javascript
function sum(text, ...rest) {
    const result = rest.reduce((sum, curr) => sum + curr, 0);
    console.log(`${text} ${result}`);
}

sum("THE SUM IS:", 3, 4, 5, 6, 7, 8, 9);
```

🧠 **বুঝে রাখো:**  
- `...rest` প্যারামিটারগুলিকে একটি অ্যারে হিসেবে ধরে।
- এটি একাধিক আর্গুমেন্ট হ্যান্ডল করতে কাজে লাগে।

---

### 🔄 Spread vs Rest: পার্থক্য

| চিহ্ন | নাম         | উদ্দেশ্য                         | ব্যবহারের উদাহরণ |
|------|-------------|-----------------------------------|------------------|
| `...`| Spread       | মানগুলো আলাদা করে ফেলে বা কপি করে | `...array`       |
| `...`| Rest         | মানগুলো একত্র করে একটি array বানায় | `function(...args)` |

---

---

## ✅ Truthy এবং Falsy মান

জাভাস্ক্রিপ্টে কিছু মান `if` শর্তে **false** হিসাবে বিবেচিত হয়, যেগুলোকে **Falsy Values** বলে।

### 🔻 Falsy Values:
```js
false
0
''
null
undefined
NaN
```

এই মানগুলো `if` শর্তে `false` হিসাবে বিবেচিত হবে।

### উদাহরণ:

```js
const result = NaN;

if (!result) {
    console.log("Falsy Value");  // ✅ এটি চলবে
} else {
    console.log("Truthy Value");
}
```

🔍 `!result` মানে হচ্ছে "result যদি falsy হয়" — এখানে `NaN` হচ্ছে falsy, তাই প্রথম ব্লকটি চলবে।

---

## 🎯 Truthy মান:

Falsy ছাড়া বাকি সব কিছুই truthy — যেমন:

```js
true
1
'hello'
[]
{}
function(){}
```

---

## ✅ Ternary Operator

এটি একটি শর্টকাট `if...else` এর মত।

### গঠন:

```js
condition ? true_value : false_value
```

### উদাহরণ:

```js
const a = 6;
let result = a % 2 === 0 ? "Even" : "Odd";
console.log(result); // Even
```

📌 এখানে `a % 2 === 0` হল শর্ত, যদি সত্য হয় তাহলে `"Even"` রিটার্ন করবে, না হলে `"Odd"`।

---

## 🔁 সমগ্র কোড (পরিষ্কারভাবে):

```js
// ✅ Truthy এবং Falsy মান

const result = NaN;

if (!result) {
    console.log("Falsy Value"); // ✅ এটি দেখাবে
} else {
    console.log("Truthy Value");
}

/*
Falsy Values:
- false
- 0
- ''
- null
- undefined
- NaN
*/

// ✅ Ternary Operator ব্যবহার

const a = 6;
let output = a % 2 === 0 ? "Even" : "Odd";
console.log(output); // Even
```

---


---

## 📦 Object Destructuring (অবজেক্ট ভেঙে মান বের করা)

```js
const user = {
    id: 334,
    name: "ali",
    age: 43,
    education: {
        degree: "Graduate",
        school: {
            name: "Name"
        }
    }
};
```

---

### ✅ সরল Destructuring:

```js
const { name, age } = user;
console.log(name, age); // ali 43
```

এখানে আমরা `user` অবজেক্ট থেকে সরাসরি `name` ও `age` বের করেছি।

---

### ✅ Nested Destructuring:

```js
const {
    education: {
        degree
    }
} = user;

console.log(degree); // Graduate
```

এখানে `education` অবজেক্টের ভিতরের `degree` কে destructure করা হয়েছে।

---

### ⚠️ Problematic Destructuring with Default Value:

```js
const {
    education: {
        degree
    } = {}
} = user;

console.log(degree); // Graduate
```

🔴 এটি আসলে ঝুঁকিপূর্ণ সিনট্যাক্স।

এটি তখনই ঠিকমতো কাজ করে যখন `education` ফিল্ডটি না থাকে। কিন্তু যদি `education` থাকে, কিন্তু `degree` না থাকে, তাহলে error আসবে না – কিন্তু `degree` হবে `undefined`।

যদি তুমি `education` না থাকার সম্ভাবনা বিবেচনা করো, তাহলে এমনভাবে লেখা উচিত:

---

### ✅ নিরাপদ Nested Destructuring with Optional Chaining:

```js
const degree = user.education?.degree;
console.log(degree); // Graduate
```

অথবা:

```js
const degree = user.education && user.education.degree;
```

---

### ⚠️ Variable Name Conflict:

```js
const {
    education: {
        school: name
    } = {}
} = user;
```

এই লাইনে `name` নামে ভেরিয়েবল আগেই ব্যবহার করা হয়েছে। এখন আবার `name` কে `school` এর ভেতর থেকে destructure করে `name` নামে রাখলে আগের `name` ওভাররাইট হয়ে যাবে।

### ✅ তাই এখানে alias ব্যবহার করা উচিৎ:

```js
const {
    education: {
        school: { name: schoolName }
    }
} = user;

console.log(schoolName); // Name
```

---

## 🧠 সংক্ষিপ্ত নোটস:

```js
// 1️⃣ সরাসরি মান বের করা
const { name, age } = user;

// 2️⃣ Nested মান বের করা
const { education: { degree } } = user;

// 3️⃣ alias দিয়ে নাম বদলানো
const { education: { school: { name: schoolName } } } = user;

// 4️⃣ Optional chaining ব্যবহার করে নিরাপদভাবে মান বের করা
const degree = user.education?.degree;
```

---
---

## 🔄 Nullish Coalescing, OR, AND অপারেটর

```js
let lang = null;

console.log(lang ?? "Javascript"); // ✅ Javascript
console.log(lang || "Javascript"); // ✅ Javascript
console.log(lang && "Javascript"); // ❌ null
```

### 🔹 `??` (Nullish Coalescing)
এটি `null` বা `undefined` হলে ডান পাশের মান নেয়।

```js
let lang = null;
console.log(lang ?? "Javascript"); // "Javascript"
```

---

### 🔹 `||` (Logical OR)
এটি falsy value (`false`, `0`, `''`, `null`, `undefined`, `NaN`) পেলে ডান পাশের মান নেয়।

```js
let lang = ""; 
console.log(lang || "JS"); // "JS"
```

> `""` একটি falsy value, তাই `JS` প্রিন্ট হয়।

---

### 🔹 `&&` (Logical AND)
এটি truthy হলে ডান পাশের মান রিটার্ন করে, নয়তো বাম পাশের মানই ফেরত দেয়।

```js
let lang = null;
console.log(lang && "JS"); // null
```

---

## ⚡ Short Circuit ব্যাখ্যা

Short-circuit মানে হচ্ছে JavaScript অপারেটরগুলো (যেমন `&&`, `||`) প্রয়োজনে সব অংশ execute না করে মাঝপথেই থেমে যায়।

```js
false && anything // ❌ সরাসরি false রিটার্ন
true || anything  // ✅ সরাসরি true রিটার্ন
```

---

## ⏳ Async/Await & API Call

```js
async function getData() {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos/1");
    const data = await response.json();
    console.log(data);
}

getData();
```

### 🔹 ব্যাখ্যা:
- `fetch()` দিয়ে API কল করা হয়।
- `await` দিয়ে async অপারেশন শেষ না হওয়া পর্যন্ত অপেক্ষা করা হয়।
- `.json()` মেথড দিয়ে JSON ডেটা পড়া হয়।

### 📦 আউটপুট:
```js
{
  userId: 1,
  id: 1,
  title: "delectus aut autem",
  completed: false
}
```

---

## 🔄 Promise Return Example

```js
function fetchData() {
    return fetch("https://jsonplaceholder.typicode.com/todos/1")
        .then(response => response.json())
        .then(data => console.log(data));
}

fetchData();
```

### ✅ ব্যাখ্যা:
এখানে `fetchData()` একটি Promise রিটার্ন করে এবং `.then()` চেইন করে আমরা ডেটা প্রিন্ট করি।

---

## 📚 সংক্ষেপে:

| অপারেটর | কাজ |
|---------|------|
| `??` | null/undefined হলে fallback দেয় |
| `||` | falsy হলে fallback দেয় |
| `&&` | truthy হলে পরের মান দেয় |
| `async/await` | asynchronous কাজকে সহজ করে |
| `fetch` | API থেকে ডেটা আনার জন্য |

---

---

## 🚀 `async` ফাংশন কী?

`async` একটি কীওয়ার্ড যা JavaScript-এ ফাংশনের আগে ব্যবহার করা হয়। এটি বলে দেয় যে ফাংশনটি **অ্যাসিনক্রোনাস (asynchronous)** হবে এবং এটি **একটি Promise রিটার্ন করবে**।

```js
async function getData() {
    return "Hello";
}

console.log(getData()); // 👉 Promise { 'Hello' }
```

যেহেতু `getData()` একটি Promise রিটার্ন করে, তাই এর রেজাল্ট পেতে হলে `await` বা `.then()` ব্যবহার করতে হবে।

---

## 🕒 `await` কী?

`await` কেবল `async` ফাংশনের ভিতরে ব্যবহার করা যায়। এটি বলে দেয়—"এই লাইনে অপেক্ষা করো যতক্ষণ না Promise resolve হয়।"

---

## ✅ ব্যবহারিক উদাহরণ:

### 📦 ১. API কল করে ডেটা আনা

```js
async function fetchTodo() {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos/1");
    const data = await response.json();
    console.log(data);
}

fetchTodo();
```

### 🔍 ব্যাখ্যা:

| লাইন | কাজ |
|------|-----|
| `await fetch(...)` | API থেকে ডেটা আসা পর্যন্ত অপেক্ষা করে |
| `await response.json()` | JSON এ রূপান্তর হওয়া পর্যন্ত অপেক্ষা করে |
| `console.log(data)` | ডেটা কনসোলে দেখায় |

---

## 🔄 async ফাংশন এর ভেতরে অন্য ফাংশন কল করা

তুমি `async` ফাংশনের ভিতর `await` দিয়ে অন্য `async` ফাংশনকেও কল করতে পারো।

```js
async function getTodoData(id) {
    const res = await fetch(`https://jsonplaceholder.typicode.com/todos/${id}`);
    const data = await res.json();
    return data;
}

async function showTodo() {
    const todo = await getTodoData(2);
    console.log(todo);
}

showTodo();
```

---

## ❗ যদি await ছাড়া async ফাংশন কল করো

```js
const data = getTodoData(2); // ❌ এটা একটা Promise
console.log(data); // 👉 Promise {...}
```

তাই সবসময় `await` বা `.then()` ব্যবহার করতে হবে।

---

## 🔐 সংক্ষেপে মনে রাখো:

| টার্ম | কাজ |
|------|-----|
| `async` | ফাংশনকে asynchronous করে, Promise রিটার্ন করে |
| `await` | Promise resolve না হওয়া পর্যন্ত কোডকে থামিয়ে রাখে |
| `.then()` | Promise এর রেজাল্ট পেতে ব্যবহৃত হয় (বিকল্প `await`) |

---


