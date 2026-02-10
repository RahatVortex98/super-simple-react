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

- A "div" is a container element.
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

- Functionality:
  1. Get today's date.
  2. Flip a coin.
  3. Roll a dice.

### Boilerplate:

```JSX
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ChatBot</title>

    <!-- React 18 CDNs + Babel Standalone -->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>

    <!-- ALL React/JSX code MUST go here -->
    <script type="text/babel">
        // Example starting JSX (replace with your ChatInput or whatever the video asks)
        const element = (
            <div>
                <h1>Welcome to ChatBot!</h1>
                <p>This is the starting boilerplate.</p>
                {/* Your component or content goes here */}
            </div>
        );

        // Render it
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(element);
    </script>
</body>
</html>
```
### Component => a piece of the website.

- When building websites:
 1. It's better to split up the website into pieces.
 2. So, we can work on a small piece of the website at a time.

### Creating 1st component:

- Rules:
  1. The Component name must start with a  capital letter.(PascalCase)

     ```JS
      function ChatInput(){
     
     };
     ```
  2. JSX is more strict than normal HTML; all elements need a closing tag.
    ```HTML
      <input></input>
    
          Use this instead of this,

       <input />
    ```

  3. We can create our own HTML element.
     ```HTML
      <ChatInput> </ChatInput> 
     ```

  4. Up until now, we used div to make a group, but there is another way to make a group, called fragment "<></>"
     - What is fragment => group elements together, without creating an extra div.
     - using div
       ```JSX
        function ChatInput() {
            return (
                <div>
                    {/* Input field for typing messages */}
                    <input />

                    {/* Button to send message */}
                    <button>Send</button>
                </div>
            );
        }
       ```
       - using fragment
      ```JSX
        function ChatInput() {
            return (
                <>
                    {/* Input field for typing messages */}
                    <input />

                    {/* Button to send message */}
                    <button>Send</button>
                </>
            );
        }
       ```

### ChatInput 1st element :

```JSX
<script type="text/babel">
       /*
          ChatInput Component
          - This is a React function component
          - It returns JSX (HTML-like syntax)
        */
        function ChatInput() {
            return (
                <>
                    {/* Input field for typing messages */}
                    <input placeholder="Send a message to chatbot" size="30"/>

                    {/* Button to send message */}
                    <button>Send</button>
                </>
            );
        }

        /*
          JSX Element
          - We call the ChatInput component
          - Components return elements, which React can render
        */
        const app = (
            <>
              <ChatInput />
            </>
        );

        /*
          Create React root
          - Connect React to the real DOM
        */
        const root = ReactDOM.createRoot(
            document.getElementById('root')
        );

        /*
          Render JSX into the browser
        */
        root.render(app);
    </script>

```


### Props =>Properties

- Make our component reusable.

```JS
function ChatMessage(props){
            const message =props.message;

            return(
                <div>
                    {message}
                    <img src="user.png" width="50"/>
                </div>
            );
        }

//message comes from render ,

 <ChatMessage message="hello chatbot"/>
```

### Shortcuts in React
1. 
```JS
const message = props.message;
const sender = props.sender;

//shortcut form -destructuring

const {message,sender}=props;

```
2. more shorter way:
```JS
 function ChatMessage({message,sender}){
            //const message =props.message;
            //const sender = props.sender;

            //const {message,sender}=props; 
```

3. if statement directly into JSX:
  - Guard Operator:

  - Syntax:
    ```JS
      condition && doSomething();
      {isLoading && <p>Loading...</p>}
    ```
    ```JS
      const result = value1 && value2;
    # if value1 is true, the result will be value2,
    # this works like an if statement
    ```

    ```JS
     <div>
    {sender==="robot"&&<img src="robot.png" width="50" />}
    {message}
    {sender==="user"&& <img src="user.png" width="50" />}
    </div>
    ```
4. Use a component to create the app:

   ```JS
     function App(){
                return(
                         <>
              <ChatInput />
              <ChatMessage message="hello chatbot"sender="user"/>
              <ChatMessage message="Hello! How can i help you?" sender="robot"/>
              <ChatMessage message="Can you get me todays date?" sender="user"/>
              <ChatMessage message="Today is September27" sender="robot"/>
            </>
                );

            }

                 & render this way,
   root.render(<App />);
   ```
   5. Best practice: Use a component (App) to create the website.

    ```JS
     function App()
      root.render(<App />);
    ```
# ⚛️ Lesson 3:State, Event Handlers, chatbot project feature

### State: Make our website interactive

- Up until now, we used a manual msg systen; now we will use JS to generate these components.
  step1: Save the data,

  step2: Generate the HTML,

