

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

