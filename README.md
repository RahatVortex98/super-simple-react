# React Beginner to Pro

My personal learning repo following the **SuperSimpleDev React Tutorial Full Course - Beginner to Pro (React 19, 2025)** on YouTube.

📺 Course link: [https://www.youtube.com/watch?v=TtPXvEcE11E](https://www.youtube.com/watch?v=TtPXvEcE11E)  
Official course repo (solutions & code copies): [https://github.com/SuperSimpleDev/react-course](https://github.com/SuperSimpleDev/react-course)

Building two main projects:
- Interactive Chatbot (state, events, conditional rendering)
- E-commerce Store (products listing, cart, routing with React Router)

## Tech Stack
- React 19
- Vite (fast dev setup)
- React Router v6+
- Modern hooks (useState, useEffect, useRef, etc.)
- CSS / Tailwind (optional styling)

## How to Run Locally
```bash
  git clone https://github.com/RahatVortex98/super-simple-react.git
  cd super-simple-react
  npm install
  npm run dev
```

## Progress

Tracking my completion of the SuperSimpleDev React course  
(Update by editing this file or clicking checkboxes on GitHub)

- [ ] 0:00 – Introduction & Setup (Vite project creation)
- [ ] React Basics & JSX
- [ ] Components & Props (start Chatbot project)
- [ ] State & Event Handlers (Chatbot features)
- [ ] Conditional Rendering & Lists (.map())
- [ ] Forms & Controlled Inputs
- [ ] useEffect & Data Fetching
- [ ] useRef & More Hooks
- [ ] Lifting State Up
- [ ] Finish Chatbot Project
- [ ] React Router Setup
- [ ] E-commerce Project: Product Listing & Details
- [ ] Cart Functionality
- [ ] Styling & Polish
- [ ] Final Review & Optimizations
- [ ] Deploy to Vercel/Netlify/Render (bonus)

---

# ⚛️ Lesson 1: React Basics

**React** is an external JavaScript library that helps us build user interfaces and websites more easily.

---

## 📦 Why are there 2 external libraries for React?

React is split into two libraries to separate shared logic from platform-specific logic.

### 1. React
- Contains shared/core features
- Used for both web and mobile apps
- Handles components, state, props, hooks, etc.

### 2. ReactDOM
- Contains features specific to the web
- Responsible for rendering React components into the browser DOM

### Usage

- **To create websites**
  - Load `React` + `ReactDOM`

- **To create mobile apps**
  - Load `React` + `React Native`

---

## 🔄 What is Babel?

**Babel** is a JavaScript compiler.

- Converts modern JavaScript into browser-compatible JavaScript
- Translates JSX into plain JavaScript
- Allows us to use latest JS features safely

---

## 🧩 What is JSX?

**JSX (JavaScript XML)** is a syntax extension for JavaScript.

- Looks like HTML
- Written directly inside JavaScript
- Makes UI code easier to read and write

### Example

```jsx
const button = <button>hello</button>;
```
### Problems
- Our browser doesn't understand JSX. Here comes Babel, which translates the JSX.
```jsx
<script src="http://unpkg.com/supersimpledev/babel.js></script>"
<script type="text/babel">
```

## 🧩 How We Display Elements in React

---

### 📌 Example

---

### ▶️ Displaying a Single Element

```js
const paragraph = <p>paragraph of text</p>;

const container = document.querySelector('.js-container');
ReactDOM.createRoot(container).render(paragraph);
```
### ▶️ Displaying Multiple Elements
❌ We can’t pass multiple elements into render()

```JS
.render(paragraph, hello);
```
❌ We can’t store multiple JSX elements directly in a single variable

```JS
const elements =
  <button>hello</button>
  <p>paragraph of text</p>;
```
✅ What We Can Do

- A <div> is a container element.
- Even if it contains multiple elements, React treats it as one element.

```JS
const div = <div>
  <button>hello</button>
  <p>paragraph of text</p>
</div>;
```
- ✨ Cleaned-Up Version (Recommended)

Using parentheses makes JSX cleaner and more readable.

```JS
const div = (
  <div>
    <button>hello</button>
    <p>paragraph of text</p>
  </div>
);

```
### ⚛️ Why React?

React is an external library that helps us create websites more easily.

- Advantages:

1. A more natural way to build UI
2. Create as many elements as you want. Then give them to React to render
3. Easier to find errors.Allows inserting JavaScript code directly inside elements (JSX)


# ⚛️ Lesson 2:Components & Props (start Chatbot project)


