

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

