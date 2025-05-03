

---

# 📘 React.js সহজ ভাষায় নোটস (বাংলায়)

---

## 🔷 React কী?

**React** হলো JavaScript-এর একটা লাইব্রেরি, যেটা দিয়ে **ইন্টারঅ্যাকটিভ (চলন্ত, স্মার্ট) ওয়েব অ্যাপ** তৈরি করা যায়। ফেসবুক তৈরি করেছে, এখন সারা দুনিয়া ব্যবহার করে।

🧠 ভাবো, ওয়েবসাইটটা অনেকগুলো ছোট ছোট খেলনা অংশ দিয়ে বানানো—React দিয়ে আমরা ঠিক এভাবেই কাজ করি।

---

## ❓ কেন React শিখব?

✅ ছোট ছোট component দিয়ে বড় অ্যাপ বানানো যায়
✅ বারবার কোড না লিখে পুনঃব্যবহারযোগ্য জিনিস বানানো যায়
✅ সহজে মেইনটেইন করা যায়
✅ চাকরির বাজারে React-এর চাহিদা অনেক
✅ ফেসবুক, Netflix, Instagram - এরা সবাই React ব্যবহার করে

---

## ⚙️ JSX (JavaScript + XML)

➡ JSX হলো JavaScript-এর মধ্যে HTML-এর মতো কোড লেখার উপায়
➡ ব্রাউজার সরাসরি বুঝতে পারে না—Babel ট্রান্সপাইল করে

```jsx
const name = "Tina";
return <h1>Hello, {name}</h1>;
```

---

## 🧩 Component

➡ React অ্যাপ ছোট ছোট **component** দিয়ে তৈরি হয়
➡ প্রতিটা অংশ (যেমন header, button, footer) আলাদা component
➡ Component ২ ধরনের হয়:

* **Function Component** (সবচেয়ে বেশি ব্যবহৃত)
* **Class Component** (পুরানো স্টাইল)

---

## 🔹 Function Component

➡ সাধারণ JavaScript ফাংশনের মতো
➡ props নেয়, JSX রিটার্ন করে

```jsx
function Hello(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

✅ ছোট, পরিষ্কার, ও দ্রুত

---

## 🧠 State

➡ Component-এর ভিতরের পরিবর্তনশীল অবস্থা
➡ `useState` হুক দিয়ে ব্যবহার করা হয়

```jsx
const [count, setCount] = useState(0);
```

➡ ইউজারের অ্যাকশনে `state` আপডেট হয়, UI আবার রেন্ডার হয়

---

## 🪄 Fragment

➡ Component-এর ভেতরে একাধিক JSX এলিমেন্ট **wrap** করতে হয়
➡ না চাইলে অপ্রয়োজনীয় DOM তৈরি করতে না চাইলে `<></>` ব্যবহার করা যায়

```jsx
<>
  <h1>Hello</h1>
  <p>Welcome</p>
</>
```

---

## ⚗️ Transpiler (Babel)

➡ JSX → JavaScript-এ রূপান্তরের জন্য
➡ React নিজে বুঝে, কিন্তু ব্রাউজার বুঝে না
➡ Babel এই কাজ করে দেয় behind the scenes

---

## 🖥️ ReactDOM

➡ JSX কে **বাস্তব HTML** এ রূপান্তর করে
➡ মূলত ব্রাউজারে React অ্যাপকে দেখায়

```jsx
ReactDOM.render(<App />, document.getElementById('root'));
```

---

## ✅ React-এর সুবিধা (Benefits)

1. ♻️ Reusable Component
2. ⚡ Virtual DOM – দ্রুত রেন্ডারিং
3. 🧠 Smart UI with State & Props
4. 🔧 Code Maintain করা সহজ
5. 🌍 বড় বড় কোম্পানি ব্যবহার করে
6. 💼 ক্যারিয়ারে বড় সুযোগ

---

## 📌 Summary Tree

```
React
├── JSX
├── Component
│   ├── Function Component
│   ├── Fragment
│   └── State
├── Transpiler (Babel)
├── ReactDOM
└── Benefits
    ├── Reusable
    ├── Fast
    ├── Easy to Maintain
    └── Career Friendly
```

---

---

## 🧱 Is DOM Slow?

➡️ **DOM (Document Object Model)** হচ্ছে HTML elements-এর একটা গাছের মতো স্ট্রাকচার (tree structure), যেটা ব্রাউজার মেমোরিতে ধরে রাখে।

🔻 **Yes, DOM ধীরগতি (slow)** হতে পারে কারণ:

* এটা **বড় এবং ভারি** (heavy) structure
* **প্রতিটি পরিবর্তনে ব্রাউজারকে রি-রেন্ডার** করতে হয়
* একাধিক DOM Update → **Reflow/Repaint**, যা performance খেয়ে ফেলে

---

## 🔗 DOM Node কী?

➡️ HTML-এর প্রতিটি element = একেকটা **DOM Node**
🧱 যেমন:

```html
<div>Hello</div>
```

এখানে `<div>` হলো একটা DOM Node।

---

## 🚀 Vanilla JS দিয়ে Performance Improve করার টিপস:

✅ ১. **Batch DOM updates** – একসাথে সব পরিবর্তন করো
✅ ২. **Avoid unnecessary reflows** – style পরিবর্তনের সময়
✅ ৩. **Use `documentFragment`** – DOM-এ insert করার আগে ভার্চুয়ালি তৈরি করো
✅ ৪. **Event Delegation** – parent-এ event handle করো
✅ ৫. **Throttling & Debouncing** – scroll বা input event-এ
✅ ৬. **Minimize DOM access** – DOM থেকে data বারবার না নেওয়া
✅ ৭. **Use `requestAnimationFrame()`** – smooth rendering-এর জন্য

---

## 💻 Virtual DOM কী?

➡️ Virtual DOM (V-DOM) হলো **DOM-এর এক কপি** যেটা **মেমোরিতে** রাখা হয়
➡️ React এটা ব্যবহার করে

### 🤖 কীভাবে কাজ করে?

1. ইউজার কিছু পরিবর্তন করে (যেমন টাইপিং)
2. React নতুন Virtual DOM তৈরি করে
3. **Diffing Algorithm** চালিয়ে আগের Virtual DOM এর সাথে তুলনা করে
4. যে জিনিসগুলো বদলেছে **সেগুলোকেই শুধু প্রকৃত DOM-এ আপডেট করে**

✅ এই কারণেই React এত দ্রুত এবং স্মার্ট!

---

## 🧠 Diffing Algorithm কী?

➡️ **React-এর core algorithm**, যা আগের Virtual DOM আর নতুন Virtual DOM এর মধ্যে **কী পরিবর্তন হয়েছে** সেটা খুঁজে বের করে

🔍 কাজ করে:

* একই tag থাকলে শুধু content/props update করে
* ভিন্ন tag হলে পুরোটাই replace করে
* key ব্যবহার করলে list element দ্রুত update হয়

---

## ❓Is Virtual DOM Slow?

❌ না, Virtual DOM আসলে **fast**, কারণ:

* এটা শুধু **memory-তে তৈরি structure**
* এটা **DOM এর তুলনায় অনেক হালকা**
* ব্রাউজার DOM manipulation এর আগে এটা **পরীক্ষা করে optimized update দেয়**

📌 তবে, **Virtual DOM নিজেও একধরনের Computation করে**, তাই খুব বড় অ্যাপ হলে optimization দরকার

---

## 🆚 jQuery vs Vanilla JS vs React

| 🔍 Feature            | 🟦 jQuery          | 🟨 Vanilla JS           | 🟩 React                     |
| --------------------- | ------------------ | ----------------------- | ---------------------------- |
| Syntax Simplicity     | ✅ সহজ              | ⚠️ কিছুটা verbosy       | ✅ Component-based            |
| DOM Manipulation      | ✅ সহজ              | ✅ Full Control          | ❌ Direct নয় (React নিজে করে) |
| Performance           | ❌ ধীর (Direct DOM) | ✅ সবচেয়ে দ্রুত          | ✅ Virtual DOM + smart update |
| Learning Curve        | ✅ সহজ              | ⚠️ Low-level            | ❌ কিছুটা বেশি                |
| Reusability           | ❌ না               | ⚠️ Library বানাতে হয়    | ✅ Component-based reuse      |
| Structure/Maintenance | ❌ নাই              | ❌ নিজে করতে হয়          | ✅ পুরো App structuring       |
| Modern Development    | ❌ পুরানো স্টাইল    | ⚠️ শুরু শেখার জন্য ভালো | ✅ Industry standard          |

---

## 📝 Summary:

* DOM আসলেই ধীর হতে পারে, কিন্তু ঠিকমতো ব্যবহার করলে দ্রুতও হতে পারে
* Virtual DOM হল ব্রাউজার DOM এর স্মার্ট ভার্সন
* React-এর diffing algorithm শুধু দরকারি জিনিস বদলায়
* Vanilla JS = Powerful but manual
* jQuery = Easy but outdated
* React = Smart, Maintainable, Future-proof

---



---

## 📘 React: UI বর্ণনা করা (Describing the UI)

### 🧩 Component কী?

React-এ, UI তৈরি করা হয় ছোট ছোট অংশ বা "components" দিয়ে। প্রতিটি component একটি JavaScript ফাংশন যা কিছু JSX (JavaScript XML) রিটার্ন করে। উদাহরণস্বরূপ:

```jsx
function Profile() {
  return (
    <img
      src="https://i.imgur.com/MK3eW3As.jpg"
      alt="Katherine Johnson"
    />
  );
}
```



এই `Profile` component একটি ছবি প্রদর্শন করে।

### 🧱 Component গুলো কিভাবে একত্রিত হয়?

একাধিক component একত্রিত করে একটি বড় UI গঠন করা যায়। উদাহরণস্বরূপ:

```jsx
function Gallery() {
  return (
    <section>
      <h1>Amazing scientists</h1>
      <Profile />
      <Profile />
      <Profile />
    </section>
  );
}
```



এখানে, `Gallery` component তিনটি `Profile` component ব্যবহার করে একটি সেকশন তৈরি করছে।

### 📝 JSX কী?

JSX হলো JavaScript-এর একটি syntax extension যা HTML-এর মতো দেখতে। এটি component-এর মধ্যে markup লেখার একটি উপায়। উদাহরণস্বরূপ:

```jsx
const name = 'Katherine Johnson';
const element = <h1>Hello, {name}</h1>;
```



এখানে, `{name}` এর মান `Katherine Johnson` হয়ে যাবে।

### 🔄 Props কী?

Props (properties) হলো component-এ ডেটা পাঠানোর উপায়। উদাহরণস্বরূপ:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

<Welcome name="Sara" />
```



এখানে, `Welcome` component-এ `name` props পাঠানো হয়েছে, যার মান `Sara`।

### 🔀 Conditional Rendering

React-এ, শর্ত অনুযায়ী component রেন্ডার করা যায়। উদাহরণস্বরূপ:

```jsx
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  }
  return <h1>Please sign up.</h1>;
}
```



এখানে, `isLoggedIn` এর মান অনুযায়ী ভিন্ন ভিন্ন বার্তা প্রদর্শন করা হবে।

### 📚 Component গুলো আলাদা ফাইলে রাখা

বড় অ্যাপ্লিকেশন তৈরি করার সময়, component গুলো আলাদা ফাইলে রাখা ভালো। উদাহরণস্বরূপ:

**Profile.js**

```jsx
function Profile() {
  return (
    <img
      src="https://i.imgur.com/MK3eW3As.jpg"
      alt="Katherine Johnson"
    />
  );
}

export default Profile;
```



**Gallery.js**

```jsx
import Profile from './Profile';

function Gallery() {
  return (
    <section>
      <h1>Amazing scientists</h1>
      <Profile />
      <Profile />
      <Profile />
    </section>
  );
}

export default Gallery;
```



এভাবে, component গুলোকে মডুলার করে রাখা যায়, যা রক্ষণাবেক্ষণ সহজ করে।

---

---

## 📦 Importing and Exporting Components (React ডকুমেন্টেশন থেকে)

### 🔹 আপনি কী শিখবেন?

React কম্পোনেন্ট এক ফাইল থেকে অন্য ফাইলে **import** ও **export** করার নিয়ম।

---

### 1️⃣ একটি ফাইল থেকে কম্পোনেন্ট **export** করা

React কম্পোনেন্ট সাধারণত আলাদা ফাইলে রাখা হয়। প্রতিটি কম্পোনেন্ট হলো একটি function যা JSX রিটার্ন করে।

```jsx
// Gallery.js

function Profile() {
  return (
    <img
      src="https://i.imgur.com/MK3eW3As.jpg"
      alt="Katherine Johnson"
    />
  );
}

export default function Gallery() {
  return (
    <section>
      <h1>Amazing scientists</h1>
      <Profile />
      <Profile />
      <Profile />
    </section>
  );
}
```

🧠 এখানে `Gallery` কম্পোনেন্টকে `export default` করা হয়েছে, এবং `Profile` কম্পোনেন্ট শুধুমাত্র এই ফাইলে ব্যবহার করা হচ্ছে।

---

### 2️⃣ অন্য ফাইলে সেই কম্পোনেন্ট **import** করা

```jsx
// App.js

import Gallery from './Gallery.js';

export default function App() {
  return <Gallery />;
}
```

🟢 ডিফল্ট export হলে import করার সময় `{}` ব্যবহার করতে হয় না, আর নাম পরিবর্তনও করা যায়।

---

### 🔁 Named Export ব্যবহার করা (একাধিক কম্পোনেন্ট একসাথে)

```jsx
// Gallery.js

export function Profile() {
  return (
    <img
      src="https://i.imgur.com/MK3eW3As.jpg"
      alt="Katherine Johnson"
    />
  );
}

export function Gallery() {
  return (
    <section>
      <h1>Amazing scientists</h1>
      <Profile />
      <Profile />
      <Profile />
    </section>
  );
}
```

**Import করার সময়:**

```jsx
import { Gallery, Profile } from './Gallery.js';
```

🟡 যখন named export ব্যবহার করা হয়, তখন import করার সময় `{ }` দিয়ে নির্দিষ্ট নাম লিখতে হয়।

---

### ✅ সংক্ষিপ্ত নিয়ম

| Export Style | Export Syntax                 | Import Syntax                          |
| ------------ | ----------------------------- | -------------------------------------- |
| Default      | `export default MyComponent`  | `import MyComponent from './file'`     |
| Named        | `export function MyComponent` | `import { MyComponent } from './file'` |

---

### 💡 ভালো অভ্যাস

* একটি কম্পোনেন্ট = একটি ফাইল (default export)
* যদি অনেক helper ফাংশন থাকে = named export
* ফাইলের নাম ও কম্পোনেন্টের নাম এক রাখলে কোড পড়া সহজ হয়

---
---

## 🎨 JSX দিয়ে মার্কআপ লেখা 

### 🐣 JSX কী?

**JSX** মানে হলো **JavaScript XML**।

➡️ এটা এমন একটা জিনিস, যেটা দেখতে HTML-এর মতো,
➡️ কিন্তু ভিতরে JavaScript-এর মত কাজ করে।

যেমন ধরো, তুমি HTML-এ লিখতে:

```html
<h1>Hello World!</h1>
```

JSX-এ ঠিক একইভাবে লিখবে, কিন্তু JavaScript কোডের ভিতরে।

```jsx
function MyComponent() {
  return <h1>Hello World!</h1>;
}
```

JSX আমাদের React-এ HTML-এর মতো দেখতে কোড লিখতে দেয়, কিন্তু এটা আসলে JavaScript!

---

### 🎭 JSX কেন মজার?

JSX-এ আমরা চাইলে JavaScript-এর ভ্যালু, ভেরিয়েবল সবকিছু HTML-এর ভেতরে ঢুকিয়ে ফেলতে পারি। কিভাবে? শুধু `{}` ব্যবহার করলেই হলো।

```jsx
const name = 'Nadia';
return <h1>Hello, {name}!</h1>;
```

🧠 এখানে `name` মানে Nadia, আর JSX বুঝে নিচ্ছে সেটা দেখাতে হবে `<h1>` এর মধ্যে।

---

### 📚 কিছু গুরুত্বপূর্ণ নিয়ম (JSX এর Grammar)

#### 1. সব JSX কোড একটা Parent Tag-এর মধ্যে থাকতে হবে:

❌ ভুল:

```jsx
return <h1>Hello</h1>
       <p>World</p>;
```

✅ ঠিক:

```jsx
return (
  <div>
    <h1>Hello</h1>
    <p>World</p>
  </div>
);
```

#### 2. JavaScript এর কীওয়ার্ডগুলো `<class>` হিসাবে ব্যবহার করা যায় না, তাই `<className>` ব্যবহার করি:

```jsx
return <p className="red-text">Hi</p>;
```

#### 3. JSX-এ `if` ব্যবহার করা যায় না সরাসরি, কিন্তু আমরা `{}` এর মধ্যে short trick দিয়ে করতে পারি:

```jsx
const isLoggedIn = true;
return <p>{isLoggedIn ? 'Welcome!' : 'Please login'}</p>;
```

---

### 🧩 JSX = HTML + JavaScript

তুমি HTML-এর মতোই সব লিখতে পারো, কিন্তু JavaScript এর সাথে মিশিয়ে আরও শক্তিশালী জিনিস বানাতে পারো। JSX React-কে বোঝায়, “এই জিনিসটা UI-তে কেমন করে দেখাবে।”

---

### 🎁 এক লাইনে মনে রাখার মত:

> JSX হলো HTML-এর মতো দেখতে জাদুর বাক্স, যেটার ভিতরে JavaScript চলতে পারে!

---


---

## 🎈 JSX-এ `{}` বন্ধনী ব্যবহার করে JavaScript – একেবারে সহজভাবে

---

### 🐥 JSX মানে কী?

JSX মানে HTML-এর মতো দেখতে, কিন্তু JavaScript-এর ভিতরে লেখা যায়।

➡️ তুমি যখন `<h1>Hello</h1>` লিখো, এটা দেখতে HTML-এর মতো।

কিন্তু...

### 🪄 যদি আমরা চাই JavaScript-এর ভ্যালু বা expression HTML-এর মধ্যে ঢুকাতে — তখন ব্যবহার করি `{}` (Curly Braces)

---

## 🔍 উদাহরণ ১: ভেরিয়েবল দেখানো

```jsx
const name = "Sumi";
return <h1>Hello, {name}</h1>;
```

🧠 এখানে `{name}` মানে: "এই জায়গায় name ভেরিয়েবলের ভ্যালু বসাও"

---

## 🧠 উদাহরণ ২: ক্যালকুলেশন করা

```jsx
return <p>2 + 3 = {2 + 3}</p>;
```

🧮 রেজাল্ট হবে: `2 + 3 = 5`

তুমি যেকোনো JavaScript expression বসাতে পারো `{}` এর ভেতর:

* ভেরিয়েবল
* ফাংশনের রেজাল্ট
* কন্ডিশন
* লিস্ট মাপা
* লুপ

---

## ❓ Expression আর Statement-এর পার্থক্য

> JSX-এ শুধু **expression** বসানো যায়, **statement** না।

✅ Expression মানে: কিছু রেজাল্ট দেয় (return হয়)
❌ Statement মানে: শুধু কাজ করে, কিছু রিটার্ন করে না

### ✔️ Expression (চলে):

```jsx
{user.age > 18 ? "Adult" : "Child"}
```

### ❌ Statement (চলে না):

```jsx
{if (user.age > 18) { return "Adult"; }}
```

---

## 🛠️ Example: Function Call

```jsx
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = { firstName: "Luna", lastName: "Lovegood" };

return <h2>Hello, {formatName(user)}!</h2>;
```

➡️ রেজাল্ট: **Hello, Luna Lovegood!**

---

## 🧩 Recap: কখন `{}` ব্যবহার করবো?

| JSX এ তুমি `{}` এর মধ্যে বসাতে পারো | উদাহরণ                      |
| ----------------------------------- | --------------------------- |
| ভেরিয়েবল                            | `{name}`                    |
| ক্যালকুলেশন                         | `{2 + 2}`                   |
| ফাংশন কল                            | `{getUser()}`               |
| টার্নারি কন্ডিশন                    | `{loggedIn ? "Hi" : "Bye"}` |
| অ্যারে ম্যাপ                        | `{items.map(...)}`          |

---

## 🎯 মনে রাখো:

> JSX এর ভিতরে `{}` মানে: "এই জায়গায় JavaScript চালাও!"

---
---

## 🎁 React-এ Props পাঠানো — ছোটদের মতো সহজ করে!

---

### 🔍 Props মানে কী?

**Props** মানে হলো — “properties”।
➡️ ঠিক যেমন খেলনার গায়ে লেবেল থাকে — “রঙ: লাল, আকার: বড়”
➡️ তেমনি React-এ এক কম্পোনেন্টের ভিতরে ডেটা পাঠাতে হলে আমরা **props** ব্যবহার করি।

🟢 তুমি ভাবতে পারো props হলো “কম্পোনেন্টের ইনপুট”।

---

### 🎨 উদাহরণ ১: একটি কম্পোনেন্টে নাম পাঠানো

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default function App() {
  return <Welcome name="Amina" />;
}
```

🧠 এখানে কী হচ্ছে?

* `App` কম্পোনেন্ট `Welcome`-কে `name="Amina"` পাঠিয়েছে
* `Welcome` কম্পোনেন্ট `props.name` দিয়ে সেটা ব্যবহার করেছে

---

### 🧩 Props কীভাবে কাজ করে?

1. তুমি যেই কম্পোনেন্টে data পাঠাতে চাও, সেখানে `<Component propName="value" />` লিখো
2. সেই কম্পোনেন্টের function-এর ভিতরে `props.propName` দিয়ে access করো

---

### 🧃 উদাহরণ ২: একাধিক props

```jsx
function UserInfo(props) {
  return (
    <p>
      Name: {props.name}, Age: {props.age}
    </p>
  );
}

export default function App() {
  return <UserInfo name="Tuhin" age={10} />;
}
```

📦 এখানে `name` আর `age` দুটো props পাঠানো হয়েছে।

---

### 🧠 Advanced: Destructuring করে লেখা

```jsx
function UserInfo({ name, age }) {
  return <p>{name} is {age} years old.</p>;
}
```

✅ এটা হলো একই জিনিস, কিন্তু সরাসরি props থেকে name আর age বের করে নেওয়া হয়েছে।

---

### 💡 কেন props দরকার?

| কারণ              | ব্যাখ্যা                                        |
| ----------------- | ----------------------------------------------- |
| ♻️ Reuse          | একই কম্পোনেন্ট আলাদা ডেটা দিয়ে বারবার ব্যবহার   |
| 📦 Data flow      | এক কম্পোনেন্ট থেকে অন্য কম্পোনেন্টে info পাঠাতে |
| 👪 Parent → Child | বাবা কম্পোনেন্ট বাচ্চাকে data দেয়               |

---

### 🎯 মনে রাখো:

> Props মানে — **কম্পোনেন্টকে তার কাজ করার জন্য দরকারি উপাদান দেওয়া!**

---

### 🧪 Mini Exercise:

```jsx
function Greet({ name }) {
  return <h2>Hi {name}!</h2>;
}

export default function App() {
  return (
    <>
      <Greet name="Tania" />
      <Greet name="Naim" />
      <Greet name="Liton" />
    </>
  );
}
```

❓ কত বার Greet কল হলো?
❓ কী ভ্যালু print হবে?

---

---

## 🎭 Conditional Rendering — সহজ ভাষায় বোঝা

---

### 🐣 “Conditional Rendering” মানে কী?

"Conditional Rendering" মানে হলো — **যদি এটা হয়, তাহলে এটা দেখাও, নাহলে ওটা দেখাও।**

➡️ একদম আমাদের দৈনন্দিন জীবনের মতো:
**যদি বাইরে বৃষ্টি পড়ে, তাহলে ছাতা নাও। নইলে নাও না।**

React-এ ঠিক এভাবেই UI শর্ত অনুযায়ী দেখানো যায়।

---

## 🧩 উদাহরণ ১: `if` ব্যবহার করে শর্ত অনুযায়ী JSX দেখানো

```jsx
function Greeting({ isLoggedIn }) {
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please log in.</h1>;
  }
}
```

📦 এখানে `isLoggedIn` যদি `true` হয়, তাহলে "Welcome back!" দেখাবে, না হলে "Please log in."

---

## 🧃 উদাহরণ ২: Ternary Operator (`? :`) দিয়ে

```jsx
function Greeting({ isLoggedIn }) {
  return (
    <h1>
      {isLoggedIn ? 'Welcome back!' : 'Please log in.'}
    </h1>
  );
}
```

✅ এটাও একই কাজ করে, তবে এক লাইনে।

---

## ✅ উদাহরণ ৩: `&&` দিয়ে কেবল কিছু না দেখানোর কৌশল

```jsx
function Mailbox({ unreadMessages }) {
  return (
    <div>
      <h1>Hello!</h1>
      {unreadMessages.length > 0 && (
        <p>You have {unreadMessages.length} unread messages.</p>
      )}
    </div>
  );
}
```

📌 যদি `unreadMessages.length` শূন্যের বেশি হয়, তবেই প্যারাগ্রাফটি দেখা যাবে।

---

## 🧠 Bonus: Component ভিতরে Condition

```jsx
function Button({ isLoggedIn }) {
  if (isLoggedIn) {
    return <LogoutButton />;
  }
  return <LoginButton />;
}
```

🔁 এক কম্পোনেন্টের ভিতরে অন্য কম্পোনেন্ট শর্ত অনুযায়ী রেন্ডার করা যায়।

---

## 🎯 মনে রাখো:

> **React-এ তুমি চাইলে যা দেখাতে চাও, তা শর্ত অনুযায়ী রেন্ডার করতে পারো।**
> এটা ঠিক যেন UI-র পেছনে ছোট্ট এক বুদ্ধিমান রোবট কাজ করে।

---

## 📌 শর্ত দেখানোর ৩টা কৌশল:

| পদ্ধতি          | উদাহরণ                               | কবে ব্যবহার করবো?  |
| --------------- | ------------------------------------ | ------------------ |
| `if...else`     | বড় decision নেওয়ার জন্য             | একাধিক return লাগে |
| `? :` (ternary) | ছোট ছোট শর্ত, দুইটা অপশন             | ১ লাইনে            |
| `&&`            | কিছু না দেখানোর জন্য (ছোট condition) | একটাই অপশন দরকার   |

?
```

---

## 📜 Rendering Lists in React — সহজভাবে শেখা

---

### 🧠 কেন দরকার?

ধরো তোমার কাছে অনেক নাম আছে, যেমন:

```js
const students = ['Tania', 'Rafi', 'Shuvo'];
```
---
তুমি চাও সবাইকে `<li>` হিসেবে দেখাতে।
আমরা কি বারবার `<li>` লিখবো? না! আমরা **loop** ব্যবহার করবো।
---

### 🔁 React-এ `.map()` দিয়ে লিস্ট বানানো হয়

```jsx
const students = ['Tania', 'Rafi', 'Shuvo'];

function StudentList() {
  return (
    <ul>
      {students.map(name => <li>{name}</li>)}
    </ul>
  );
}
```

🧠 এখানে কী হলো?

* `students.map(...)` মানে:
  → প্রতিটা `name` এর জন্য একটা `<li>` বানাও
* JSX-এর মধ্যে আমরা `{}` ব্যবহার করি JavaScript চালানোর জন্য

---

### 🔑 Key কেন দরকার?

React-কে বোঝাতে হয়: কোন আইটেমটা বদলেছে, কোনটা নতুন, কোনটা আগের।

✅ এজন্য আমরা `key` ব্যবহার করি:

```jsx
{students.map(name => <li key={name}>{name}</li>)}
```

🔐 এই `key` React-কে বলে: "এই আইটেমটা ইউনিক", যেন performance ভালো হয়।

---

### 🧩 যদি অবজেক্টের লিস্ট হয়?

```jsx
const users = [
  { id: 1, name: 'Rima' },
  { id: 2, name: 'Farhan' },
];

function UserList() {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

📦 এখানে `key={user.id}` — কারণ `id` হচ্ছে প্রতিটি ইউজারের ইউনিক পরিচয়।

---

### 💡 Recap:

| কাজ                    | কিভাবে করবো                     |
| ---------------------- | ------------------------------- |
| লিস্ট দেখানো           | `.map()` দিয়ে JSX বানাও         |
| React বুঝবে কোনটা নতুন | `key` দিতে হবে প্রতিটি আইটেমে   |
| যদি object থাকে        | `item.property` দিয়ে data দেখাও |

---

### 🧪 Mini Practice:

```jsx
const books = [
  { id: 101, title: 'Harry Potter' },
  { id: 102, title: 'The Hobbit' },
];

function BookList() {
  return (
    <ul>
      {books.map(book => <li key={book.id}>{book.title}</li>)}
    </ul>
  );
}
```


---

## 🌊 React-এ Pure Component রাখা – বাচ্চাদের মতো বুঝি

---

### 🧼 “Pure” মানে কী?

**Pure** মানে: পরিষ্কার, নির্ভরযোগ্য, আর একরকম আচরণ করে।

🧠 React-এ একটা **Pure Component** এমন একটি ফাংশন:

> ➕ "একই ইনপুট দিলে সবসময় একই আউটপুট দেয়"

---

### ✅ উদাহরণ: একটি Pure Component

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

➡️ এখানে `name` যদি `"Tania"` হয়, তাহলে **সবসময়** দেখা যাবে: `Hello, Tania!`
এটা হচ্ছে একদম "Pure"।

---

### ❌ Impure Component কেমন?

```jsx
function Greeting({ name }) {
  alert('Hello!');
  return <h1>Hello, {name}!</h1>;
}
```

😬 সমস্যা:

* প্রতি বার এই কম্পোনেন্ট render হলে `alert()` চলে
* ইউজারের অভিজ্ঞতা খারাপ হয়
* এটা একটা **side effect** (অপ্রত্যাশিত আচরণ)

---

### 📌 React কেন Pure Component চায়?

React এর **Virtual DOM** কাজ করে এই ধারণার উপর:

> “যদি ইনপুট বদলায় না, তাহলে আউটপুটও বদলায় না।”

➡️ তাই pure component হলে React খুব সহজে বুঝে যায়:
→ "এইটা বদলায়নি, রি-রেন্ডার করার দরকার নাই!"

✅ এতে performance ভালো হয়
✅ কোড debug করা সহজ হয়

---

### 🧠 Impure Component এর আরও কিছু Example

```jsx
function Clock() {
  const now = new Date().toLocaleTimeString();
  return <p>It is {now}</p>;
}
```

➡️ এটা impure, কারণ প্রতি বার render হলে ভিন্ন সময় দেখায়।

---

### 💡 কখন Side Effect দরকার হয়?

যখন তুমি চাইছো:

* API কল করো
* টাইমার চালাও
* DOM এ কিছু পরিবর্তন করো

➡️ এসব কাজ করার জন্য React বলে: “তুমি `useEffect()` হুক ব্যবহার করো।”

---

### 🔍 Recap: Pure vs Impure

| Aspect              | Pure Component | Impure Component                     |
| ------------------- | -------------- | ------------------------------------ |
| Predictable         | ✅ হ্যাঁ        | ❌ না                                 |
| Same input → output | ✅ সবসময় এক     | ❌ ভিন্ন হতে পারে                     |
| Side effect         | ❌ নেই          | ✅ থাকে (alert, API call, timer etc.) |
| Performance         | ✅ দ্রুত        | ❌ ধীর                                |

---

### 🎯 মনে রাখো:

> "একটা Pure কম্পোনেন্ট হলো ঠিক একটা ক্যালকুলেটরের মত—তুমি 2+2 দিলে সে সবসময় 4-ই দেবে।"

---
---

## 🌳 React UI Tree — বাচ্চাদের মতো বোঝা সহজ

---

### 🧸 কল্পনা করো তোমার একটা **গাছ** আছে

* গাছের **মূল** বা **Root** হচ্ছে `App` কম্পোনেন্ট
* এরপর ওই গাছ থেকে শাখা-প্রশাখা বের হয় — এগুলো হলো **Child Components**
* একেকটা ডাল থেকে আরও ছোট ডাল বের হয় — এগুলো হলো **Nested Components**

🎯 React পুরো UI-কে ঠিক এইভাবে চিন্তা করে — **একটা বড় কম্পোনেন্টের ভিতরে ছোট ছোট কম্পোনেন্ট গেঁথে থাকে।**

---

### 🔍 উদাহরণ দেখে বোঝো:

```jsx
function App() {
  return (
    <Page />
  );
}

function Page() {
  return (
    <Header />
  );
}

function Header() {
  return (
    <h1>Hello React!</h1>
  );
}
```

🧠 এই UI টা দেখতে:

```
App
└── Page
    └── Header
        └── <h1>Hello React!</h1>
```

এইভাবে React পুরো UI-কে একটা **গাছের মতো** রূপে সাজায়।

---

### 🤔 Tree কেন দরকার?

React এর **Virtual DOM** ও **Re-render Logic** এই Tree ধরনার উপর কাজ করে:

* যদি এক জায়গায় পরিবর্তন হয়, তখন React শুধু ওই ডালটুকুই আপডেট করে
* পুরো গাছ নাড়ানোর দরকার পড়ে না

✅ এটা করে Performance খুব ভালো হয়

---

### 🧠 Tree মানে সহজে বুঝি:

| গাছের অংশ  | React Component  |
| ---------- | ---------------- |
| মূল (root) | App              |
| ডাল        | Child Components |
| পাতাগুলো   | JSX elements     |

---

### 📦 Nesting মানে?

এক কম্পোনেন্ট আরেকটার ভিতরে থাকলে তাকে **Nested** বলে।

```jsx
function Page() {
  return (
    <div>
      <Header />
      <Content />
      <Footer />
    </div>
  );
}
```

➡️ `Page` হল Root, বাকি তিনটা Child।

---

### 🎯 মনে রাখো:

> "React-এর চোখে UI মানে একটা গাছ — যার প্রতিটা ডাল হলো একেকটা Component!"

* রুট থেকে শুরু হয় সব
* একে অপরের মধ্যে Nest করা থাকে
* পরিবর্তন হলে শুধু সংশ্লিষ্ট শাখা বদলায়

---

