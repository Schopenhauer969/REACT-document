# ⚛️ React — Beginner to Advanced

A complete React learning and reference guide from **Beginner → Intermediate → Advanced**.

> 🇬🇧 **English:** Learn React step by step with practical examples.
> 🇰🇭 **ខ្មែរ:** រៀន React ពីមូលដ្ឋានរហូតដល់កម្រិត Advanced ជាមួយ code ដែលអាចយកទៅប្រើបានពិតប្រាកដ។

---

## 📚 Table of Contents

* [1. What is React?](#1-what-is-react)
* [2. Why Learn React?](#2-why-learn-react)
* [3. React Requirements](#3-react-requirements)
* [4. Create a React Project](#4-create-a-react-project)
* [5. Project Structure](#5-project-structure)
* [6. Your First React Component](#6-your-first-react-component)
* [7. JSX](#7-jsx)
* [8. Components](#8-components)
* [9. Props](#9-props)
* [10. State](#10-state)
* [11. Events](#11-events)
* [12. Conditional Rendering](#12-conditional-rendering)
* [13. Rendering Lists](#13-rendering-lists)
* [14. Forms](#14-forms)
* [15. useEffect](#15-useeffect)
* [16. Fetching API Data](#16-fetching-api-data)
* [17. Loading and Error States](#17-loading-and-error-states)
* [18. useRef](#18-useref)
* [19. useMemo](#19-usememo)
* [20. useCallback](#20-usecallback)
* [21. Custom Hooks](#21-custom-hooks)
* [22. Context API](#22-context-api)
* [23. useReducer](#23-usereducer)
* [24. React Router](#24-react-router)
* [25. Authentication Example](#25-authentication-example)
* [26. Local Storage](#26-local-storage)
* [27. TypeScript with React](#27-typescript-with-react)
* [28. Error Handling](#28-error-handling)
* [29. Performance Optimization](#29-performance-optimization)
* [30. Lazy Loading](#30-lazy-loading)
* [31. Suspense](#31-suspense)
* [32. React.memo](#32-reactmemo)
* [33. Component Architecture](#33-component-architecture)
* [34. Advanced Project Structure](#34-advanced-project-structure)
* [35. Environment Variables](#35-environment-variables)
* [36. Security](#36-security)
* [37. Testing](#37-testing)
* [38. Production Build](#38-production-build)
* [39. Best Practices](#39-best-practices)
* [40. Complete React Example](#40-complete-react-example)
* [41. Learning Roadmap](#41-learning-roadmap)

---

# 1. What is React?

## 🇬🇧 English

React is a JavaScript library for building user interfaces.

React is commonly used to create:

* Websites
* Dashboards
* Admin panels
* E-commerce applications
* Social applications
* Single Page Applications
* Interactive web applications

React applications are built using **components**.

## 🇰🇭 ខ្មែរ

React គឺជា JavaScript library សម្រាប់បង្កើត **User Interface (UI)**។

React អាចប្រើសម្រាប់បង្កើត៖

* Website
* Dashboard
* Admin Panel
* E-commerce
* Social Media Application
* Single Page Application
* Web Application ដែលមាន interaction ខ្ពស់

React ប្រើ **Component** ជាផ្នែកសំខាន់ក្នុងការបង្កើត UI។

---

# 2. Why Learn React?

## 🇬🇧 English

React provides:

* Component-based architecture
* Reusable UI
* State management
* Event handling
* Fast UI updates
* Large ecosystem
* Strong community
* Easy integration with APIs

## 🇰🇭 ខ្មែរ

React មានអត្ថប្រយោជន៍៖

* បែងចែក UI ជា Component
* អាចប្រើ Component ម្តងហើយម្តងទៀត
* គ្រប់គ្រង State
* Handle Events
* Update UI បានលឿន
* Ecosystem ធំ
* Community ធំ
* ងាយភ្ជាប់ API

---

# 3. React Requirements

Before learning React, you should know:

```text
HTML
CSS
JavaScript
ES6+
DOM
Promises
Async/Await
Fetch API
Modules
```

## Recommended knowledge

```text
JavaScript Variables
Functions
Arrays
Objects
Destructuring
Spread Operator
Map
Filter
Reduce
Arrow Functions
Modules
Promises
Async/Await
```

---

# 4. Create a React Project

The recommended modern approach is to use a modern React build tool such as Vite.

## Create project

```bash
npm create vite@latest my-react-app
```

Select:

```text
Framework: React
Variant: JavaScript
```

Then:

```bash
cd my-react-app
npm install
npm run dev
```

Your development server will start.

---

## TypeScript

You can also create a TypeScript project:

```bash
npm create vite@latest my-react-app
```

Select:

```text
Framework: React
Variant: TypeScript
```

Then:

```bash
cd my-react-app
npm install
npm run dev
```

---

# 5. Project Structure

A basic project can look like:

```text
my-react-app/
│
├── public/
│
├── src/
│   ├── assets/
│   ├── components/
│   ├── pages/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── .gitignore
├── index.html
├── package.json
└── vite.config.js
```

## 🇰🇭 ខ្មែរ

* `public/` → ឯកសារ static
* `src/` → source code សំខាន់
* `components/` → reusable components
* `pages/` → pages
* `App.jsx` → root component
* `main.jsx` → application entry point
* `index.css` → global CSS

---

# 6. Your First React Component

Create:

```text
src/App.jsx
```

```jsx
function App() {
  return (
    <div>
      <h1>Hello React</h1>
      <p>My first React application.</p>
    </div>
  );
}

export default App;
```

## 🇬🇧 English

A React component is usually a JavaScript function that returns JSX.

## 🇰🇭 ខ្មែរ

React Component ជាទូទៅគឺជា JavaScript function ដែល return JSX។

---

# 7. JSX

JSX allows us to write HTML-like syntax inside JavaScript.

```jsx
function App() {
  const name = "Heng";

  return (
    <div>
      <h1>Hello {name}</h1>
      <p>Welcome to React.</p>
    </div>
  );
}

export default App;
```

The expression:

```jsx
{name}
```

inserts JavaScript data into JSX.

---

## JavaScript expression

```jsx
function App() {
  const age = 20;

  return (
    <div>
      <h1>Age: {age}</h1>
      <p>Next year: {age + 1}</p>
    </div>
  );
}

export default App;
```

---

## JSX className

Use:

```jsx
className
```

instead of:

```html
class
```

Example:

```jsx
function App() {
  return (
    <div className="container">
      <h1>Hello React</h1>
    </div>
  );
}

export default App;
```

---

# 8. Components

Components allow us to split the application into reusable pieces.

## Header.jsx

```jsx
function Header() {
  return (
    <header>
      <h1>My Website</h1>
    </header>
  );
}

export default Header;
```

## App.jsx

```jsx
import Header from "./Header";

function App() {
  return (
    <div>
      <Header />

      <main>
        <h2>Home Page</h2>
      </main>
    </div>
  );
}

export default App;
```

---

# 9. Props

Props allow a parent component to send data to a child component.

## User.jsx

```jsx
function User({ name, age }) {
  return (
    <div>
      <h2>Name: {name}</h2>
      <p>Age: {age}</p>
    </div>
  );
}

export default User;
```

## App.jsx

```jsx
import User from "./User";

function App() {
  return (
    <div>
      <User name="Heng" age={20} />
      <User name="Dara" age={25} />
    </div>
  );
}

export default App;
```

## 🇰🇭 ខ្មែរ

`props` គឺជា data ដែល Parent Component ផ្ញើទៅ Child Component។

```text
Parent
   ↓
Props
   ↓
Child
```

---

# 10. State

State stores data that can change during the lifetime of a component.

Use:

```jsx
useState
```

Example:

```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>Count: {count}</h1>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default App;
```

## Explanation

```jsx
const [count, setCount] = useState(0);
```

Means:

```text
count     = current value
setCount  = function to update value
0         = initial value
```

## ខ្មែរ

`useState` ប្រើសម្រាប់រក្សាទុក data ដែលអាចផ្លាស់ប្តូរ។

---

# 11. Events

React supports events such as:

```text
onClick
onChange
onSubmit
onMouseEnter
onMouseLeave
onKeyDown
onKeyUp
```

Example:

```jsx
function App() {
  function handleClick() {
    alert("Button clicked!");
  }

  return (
    <button onClick={handleClick}>
      Click Me
    </button>
  );
}

export default App;
```

---

## Input event

```jsx
import { useState } from "react";

function App() {
  const [name, setName] = useState("");

  return (
    <div>
      <input
        type="text"
        value={name}
        onChange={(event) => setName(event.target.value)}
        placeholder="Enter your name"
      />

      <h2>Hello {name}</h2>
    </div>
  );
}

export default App;
```

---

# 12. Conditional Rendering

You can display different UI depending on state.

## Ternary

```jsx
function App() {
  const isLoggedIn = true;

  return (
    <div>
      {isLoggedIn ? (
        <h1>Welcome back!</h1>
      ) : (
        <h1>Please login.</h1>
      )}
    </div>
  );
}

export default App;
```

---

## && operator

```jsx
function App() {
  const isAdmin = true;

  return (
    <div>
      {isAdmin && <button>Admin Panel</button>}
    </div>
  );
}

export default App;
```

---

# 13. Rendering Lists

Use `map()` to render arrays.

```jsx
function App() {
  const users = [
    { id: 1, name: "Heng" },
    { id: 2, name: "Dara" },
    { id: 3, name: "Sokha" },
  ];

  return (
    <div>
      <h1>Users</h1>

      <ul>
        {users.map((user) => (
          <li key={user.id}>
            {user.name}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

## Important

Always provide a stable `key`.

Good:

```jsx
key={user.id}
```

Avoid using array index when a stable ID exists.

---

# 14. Forms

React commonly uses controlled inputs.

```jsx
import { useState } from "react";

function App() {
  const [form, setForm] = useState({
    name: "",
    email: "",
  });

  function handleChange(event) {
    const { name, value } = event.target;

    setForm((previous) => ({
      ...previous,
      [name]: value,
    }));
  }

  function handleSubmit(event) {
    event.preventDefault();

    console.log(form);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        name="name"
        value={form.name}
        onChange={handleChange}
        placeholder="Name"
      />

      <input
        name="email"
        type="email"
        value={form.email}
        onChange={handleChange}
        placeholder="Email"
      />

      <button type="submit">
        Submit
      </button>
    </form>
  );
}

export default App;
```

---

# 15. useEffect

`useEffect` is used for side effects.

Common examples:

* API requests
* Event listeners
* Timers
* Synchronizing with external systems

Example:

```jsx
import { useEffect, useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <h1>{count}</h1>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default App;
```

The dependency:

```jsx
[count]
```

means the effect runs when `count` changes.

---

# 16. Fetching API Data

Example using the browser `fetch()` API:

```jsx
import { useEffect, useState } from "react";

function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    async function loadUsers() {
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/users"
      );

      const data = await response.json();

      setUsers(data);
    }

    loadUsers();
  }, []);

  return (
    <div>
      <h1>Users</h1>

      {users.map((user) => (
        <div key={user.id}>
          <h2>{user.name}</h2>
          <p>{user.email}</p>
        </div>
      ))}
    </div>
  );
}

export default App;
```

---

# 17. Loading and Error States

A production application should handle:

```text
Loading
Success
Error
Empty
```

Example:

```jsx
import { useEffect, useState } from "react";

function App() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState("");

  useEffect(() => {
    async function loadUsers() {
      try {
        setLoading(true);
        setError("");

        const response = await fetch(
          "https://jsonplaceholder.typicode.com/users"
        );

        if (!response.ok) {
          throw new Error("Failed to load users.");
        }

        const data = await response.json();

        setUsers(data);
      } catch (error) {
        setError(error.message);
      } finally {
        setLoading(false);
      }
    }

    loadUsers();
  }, []);

  if (loading) {
    return <h1>Loading...</h1>;
  }

  if (error) {
    return <h1>Error: {error}</h1>;
  }

  if (users.length === 0) {
    return <h1>No users found.</h1>;
  }

  return (
    <div>
      <h1>Users</h1>

      {users.map((user) => (
        <article key={user.id}>
          <h2>{user.name}</h2>
          <p>{user.email}</p>
        </article>
      ))}
    </div>
  );
}

export default App;
```

---

# 18. useRef

`useRef` stores a mutable value without causing a re-render.

It is also commonly used to access DOM elements.

```jsx
import { useRef } from "react";

function App() {
  const inputRef = useRef(null);

  function focusInput() {
    inputRef.current?.focus();
  }

  return (
    <div>
      <input
        ref={inputRef}
        placeholder="Enter something"
      />

      <button onClick={focusInput}>
        Focus Input
      </button>
    </div>
  );
}

export default App;
```

---

# 19. useMemo

`useMemo` can cache the result of an expensive calculation.

```jsx
import { useMemo, useState } from "react";

function App() {
  const [number, setNumber] = useState(10);
  const [name, setName] = useState("");

  const doubled = useMemo(() => {
    return number * 2;
  }, [number]);

  return (
    <div>
      <input
        value={name}
        onChange={(event) => setName(event.target.value)}
        placeholder="Name"
      />

      <h2>Number: {number}</h2>
      <h2>Doubled: {doubled}</h2>

      <button onClick={() => setNumber(number + 1)}>
        Increase
      </button>
    </div>
  );
}

export default App;
```

## Important

Do not use `useMemo` everywhere.

Use it when memoization actually provides a benefit.

---

# 20. useCallback

`useCallback` caches a function reference.

```jsx
import { useCallback, useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    console.log("Clicked");
  }, []);

  return (
    <div>
      <h1>{count}</h1>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>

      <button onClick={handleClick}>
        Log
      </button>
    </div>
  );
}

export default App;
```

`useCallback` is most useful when passing callbacks to memoized child components or when function identity matters.

---

# 21. Custom Hooks

Custom hooks allow you to reuse stateful logic.

Create:

```text
src/hooks/useCounter.js
```

```jsx
import { useState } from "react";

export function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);

  function increment() {
    setCount((value) => value + 1);
  }

  function decrement() {
    setCount((value) => value - 1);
  }

  function reset() {
    setCount(initialValue);
  }

  return {
    count,
    increment,
    decrement,
    reset,
  };
}
```

Use it:

```jsx
import { useCounter } from "./hooks/useCounter";

function App() {
  const {
    count,
    increment,
    decrement,
    reset,
  } = useCounter(10);

  return (
    <div>
      <h1>{count}</h1>

      <button onClick={increment}>
        +
      </button>

      <button onClick={decrement}>
        -
      </button>

      <button onClick={reset}>
        Reset
      </button>
    </div>
  );
}

export default App;
```

---

# 22. Context API

Context allows data to be shared without passing props through every level.

## ThemeContext.jsx

```jsx
import { createContext, useContext, useState } from "react";

const ThemeContext = createContext(null);

export function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");

  function toggleTheme() {
    setTheme((current) =>
      current === "light" ? "dark" : "light"
    );
  }

  return (
    <ThemeContext.Provider
      value={{
        theme,
        toggleTheme,
      }}
    >
      {children}
    </ThemeContext.Provider>
  );
}

export function useTheme() {
  const context = useContext(ThemeContext);

  if (!context) {
    throw new Error(
      "useTheme must be used inside ThemeProvider"
    );
  }

  return context;
}
```

## App.jsx

```jsx
import {
  ThemeProvider,
  useTheme,
} from "./ThemeContext";

function Content() {
  const { theme, toggleTheme } = useTheme();

  return (
    <div>
      <h1>Theme: {theme}</h1>

      <button onClick={toggleTheme}>
        Toggle Theme
      </button>
    </div>
  );
}

function App() {
  return (
    <ThemeProvider>
      <Content />
    </ThemeProvider>
  );
}

export default App;
```

## 🇰🇭 ខ្មែរ

Context API មានប្រយោជន៍នៅពេល data ត្រូវ share ទៅ Component ជាច្រើន ដោយមិនចង់បញ្ជូន Props តាម Component កណ្ដាលជាច្រើនជាន់។

---

# 23. useReducer

`useReducer` is useful for complex state logic.

```jsx
import { useReducer } from "react";

const initialState = {
  count: 0,
};

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return {
        ...state,
        count: state.count + 1,
      };

    case "decrement":
      return {
        ...state,
        count: state.count - 1,
      };

    case "reset":
      return initialState;

    default:
      throw new Error(
        `Unknown action: ${action.type}`
      );
  }
}

function App() {
  const [state, dispatch] = useReducer(
    reducer,
    initialState
  );

  return (
    <div>
      <h1>{state.count}</h1>

      <button
        onClick={() => dispatch({ type: "increment" })}
      >
        +
      </button>

      <button
        onClick={() => dispatch({ type: "decrement" })}
      >
        -
      </button>

      <button
        onClick={() => dispatch({ type: "reset" })}
      >
        Reset
      </button>
    </div>
  );
}

export default App;
```

---

# 24. React Router

For applications with multiple pages, React Router is commonly used.

Install:

```bash
npm install react-router-dom
```

## App.jsx

```jsx
import {
  BrowserRouter,
  Routes,
  Route,
  Link,
} from "react-router-dom";

function Home() {
  return <h1>Home Page</h1>;
}

function About() {
  return <h1>About Page</h1>;
}

function Contact() {
  return <h1>Contact Page</h1>;
}

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link>{" "}
        <Link to="/about">About</Link>{" "}
        <Link to="/contact">Contact</Link>
      </nav>

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

---

# 25. Authentication Example

A simple client-side authentication state can look like this:

```jsx
import { useState } from "react";

function App() {
  const [user, setUser] = useState(null);

  function login() {
    setUser({
      id: 1,
      name: "Heng",
    });
  }

  function logout() {
    setUser(null);
  }

  if (!user) {
    return (
      <div>
        <h1>Please Login</h1>

        <button onClick={login}>
          Login
        </button>
      </div>
    );
  }

  return (
    <div>
      <h1>
        Welcome, {user.name}
      </h1>

      <button onClick={logout}>
        Logout
      </button>
    </div>
  );
}

export default App;
```

> ⚠️ This is only UI state. Real authentication should be implemented with a secure backend/session/token strategy.

---

# 26. Local Storage

You can persist non-sensitive client-side data using `localStorage`.

```jsx
import { useEffect, useState } from "react";

function App() {
  const [name, setName] = useState(() => {
    return localStorage.getItem("name") || "";
  });

  useEffect(() => {
    if (name) {
      localStorage.setItem("name", name);
    } else {
      localStorage.removeItem("name");
    }
  }, [name]);

  return (
    <div>
      <input
        value={name}
        onChange={(event) =>
          setName(event.target.value)
        }
        placeholder="Enter name"
      />

      <h1>Hello {name}</h1>
    </div>
  );
}

export default App;
```

## Security warning

Do not store highly sensitive secrets in `localStorage`.

For example, do not blindly store:

```text
Passwords
Private keys
Highly sensitive credentials
```

---

# 27. TypeScript with React

TypeScript makes React applications easier to type safely.

Example:

```tsx
type UserProps = {
  name: string;
  age: number;
};

function User({ name, age }: UserProps) {
  return (
    <div>
      <h2>{name}</h2>
      <p>{age}</p>
    </div>
  );
}

export default User;
```

Use:

```tsx
<User name="Heng" age={20} />
```

---

## Typed State

```tsx
import { useState } from "react";

type User = {
  id: number;
  name: string;
};

function App() {
  const [user, setUser] = useState<User | null>(null);

  function login() {
    setUser({
      id: 1,
      name: "Heng",
    });
  }

  return (
    <div>
      {user ? (
        <h1>{user.name}</h1>
      ) : (
        <button onClick={login}>
          Login
        </button>
      )}
    </div>
  );
}

export default App;
```

---

# 28. Error Handling

API operations should handle errors.

```jsx
import { useEffect, useState } from "react";

function App() {
  const [data, setData] = useState(null);
  const [error, setError] = useState(null);

  useEffect(() => {
    async function fetchData() {
      try {
        const response = await fetch(
          "https://jsonplaceholder.typicode.com/users/1"
        );

        if (!response.ok) {
          throw new Error(
            `HTTP error: ${response.status}`
          );
        }

        const result = await response.json();

        setData(result);
      } catch (error) {
        setError(error.message);
      }
    }

    fetchData();
  }, []);

  if (error) {
    return <p>Error: {error}</p>;
  }

  if (!data) {
    return <p>Loading...</p>;
  }

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.email}</p>
    </div>
  );
}

export default App;
```

---

# 29. Performance Optimization

Common optimization techniques:

```text
React.memo
useMemo
useCallback
Code Splitting
Lazy Loading
Virtualization
Avoid unnecessary renders
Optimize images
Reduce network requests
Cache server data
```

## Important principle

Do not optimize everything prematurely.

First:

```text
Measure
↓
Find bottleneck
↓
Optimize
↓
Measure again
```

---

# 30. Lazy Loading

React supports lazy loading components.

```jsx
import {
  lazy,
  Suspense,
} from "react";

const About = lazy(() => import("./About"));

function App() {
  return (
    <Suspense fallback={<p>Loading...</p>}>
      <About />
    </Suspense>
  );
}

export default App;
```

This can reduce the initial JavaScript required to load a page.

---

# 31. Suspense

`Suspense` provides fallback UI while a suspended component is loading.

```jsx
import {
  lazy,
  Suspense,
} from "react";

const Dashboard = lazy(
  () => import("./Dashboard")
);

function App() {
  return (
    <Suspense fallback={<h1>Loading...</h1>}>
      <Dashboard />
    </Suspense>
  );
}

export default App;
```

---

# 32. React.memo

`React.memo` can prevent unnecessary child renders when props have not changed.

## User.jsx

```jsx
import { memo } from "react";

function User({ name }) {
  console.log("User rendered");

  return <h2>{name}</h2>;
}

export default memo(User);
```

## App.jsx

```jsx
import { useState } from "react";
import User from "./User";

function App() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <User name="Heng" />

      <h1>{count}</h1>

      <button
        onClick={() => setCount(count + 1)}
      >
        Increase
      </button>
    </div>
  );
}

export default App;
```

---

# 33. Component Architecture

A clean React application can separate components by responsibility.

Example:

```text
src/
│
├── components/
│   ├── Button.jsx
│   ├── Input.jsx
│   ├── Navbar.jsx
│   └── Modal.jsx
│
├── pages/
│   ├── Home.jsx
│   ├── Login.jsx
│   ├── Dashboard.jsx
│   └── Profile.jsx
│
├── hooks/
│   ├── useAuth.js
│   └── useFetch.js
│
├── context/
│   └── AuthContext.jsx
│
├── services/
│   └── api.js
│
├── utils/
│   └── formatDate.js
│
├── App.jsx
├── main.jsx
└── index.css
```

---

# 34. Advanced Project Structure

For a larger application, feature-based organization can be useful.

```text
src/
│
├── app/
│   ├── App.jsx
│   └── router.jsx
│
├── features/
│   ├── auth/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   └── auth.js
│   │
│   ├── users/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   └── services/
│   │
│   └── products/
│       ├── components/
│       ├── hooks/
│       ├── pages/
│       └── services/
│
├── components/
│   ├── Button.jsx
│   ├── Modal.jsx
│   └── Spinner.jsx
│
├── hooks/
│
├── lib/
│
├── services/
│
├── utils/
│
├── assets/
│
└── main.jsx
```

## 🇰🇭 ខ្មែរ

Project តូចអាចប្រើ structure ធម្មតា។

Project ធំគួររៀបចំតាម **feature/domain** ដើម្បីងាយ maintain និង scale។

---

# 35. Environment Variables

With Vite, client-exposed environment variables use the `VITE_` prefix.

Example:

```text
.env
```

```env
VITE_API_URL=https://api.example.com
```

Use it:

```jsx
const apiUrl = import.meta.env.VITE_API_URL;

console.log(apiUrl);
```

## Important security rule

Anything exposed to frontend JavaScript should be considered public.

Do NOT put private server secrets into:

```env
VITE_SECRET_KEY=...
```

because the value can be exposed to users.

---

# 36. Security

Important React security practices:

## 1. Never trust user input

Bad:

```jsx
<div
  dangerouslySetInnerHTML={{
    __html: userInput,
  }}
/>
```

Avoid this unless you fully understand and sanitize the HTML.

Normally prefer:

```jsx
<div>{userInput}</div>
```

React escapes normal text rendering.

---

## 2. Protect authentication on the server

Frontend route protection alone is not security.

The backend must verify authorization.

Example concept:

```text
React
  ↓
API Request
  ↓
Backend Authentication
  ↓
Backend Authorization
  ↓
Database
```

---

# 37. Testing

A React application should be tested.

Typical testing categories:

```text
Unit Tests
Component Tests
Integration Tests
End-to-End Tests
```

Example component:

```jsx
function Button({ onClick }) {
  return (
    <button onClick={onClick}>
      Click
    </button>
  );
}

export default Button;
```

The important idea is to test behavior:

```text
Render component
↓
Find button
↓
Click button
↓
Verify expected result
```

---

# 38. Production Build

Build the application:

```bash
npm run build
```

Preview the production build locally:

```bash
npm run preview
```

Typical flow:

```text
Development
    ↓
npm run build
    ↓
Production files
    ↓
Deploy
```

---

# 39. Best Practices

## 1. Use small components

Good:

```text
Navbar
Sidebar
UserCard
ProductCard
Button
Modal
```

Avoid one giant component.

---

## 2. Keep components focused

A component should have a clear responsibility.

---

## 3. Use meaningful names

Good:

```jsx
const userProfile = ...
```

Bad:

```jsx
const x = ...
```

---

## 4. Avoid duplicated code

Create reusable components and functions.

---

## 5. Keep state as local as possible

Do not put every piece of state into global state.

---

## 6. Use stable keys

Good:

```jsx
key={user.id}
```

---

## 7. Handle loading and errors

API UI should usually handle:

```text
Loading
Success
Error
Empty
```

---

## 8. Keep API logic separate

For larger applications, consider:

```text
components/
services/
hooks/
pages/
```

---

## 9. Do not overuse hooks

Do not add:

```text
useMemo
useCallback
useEffect
```

unless they solve a real problem.

---

## 10. Keep secrets on the server

Frontend code is visible to users.

---

# 40. Complete React Example

Here is a small but complete React application demonstrating:

* Components
* Props
* State
* Events
* Forms
* Lists
* Filtering
* Delete
* Add
* Conditional rendering

## App.jsx

```jsx
import { useState } from "react";

function UserForm({ onAdd }) {
  const [name, setName] = useState("");

  function handleSubmit(event) {
    event.preventDefault();

    const trimmedName = name.trim();

    if (!trimmedName) {
      return;
    }

    onAdd(trimmedName);
    setName("");
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={name}
        onChange={(event) =>
          setName(event.target.value)
        }
        placeholder="Enter user name"
      />

      <button type="submit">
        Add User
      </button>
    </form>
  );
}

function UserList({ users, onDelete }) {
  if (users.length === 0) {
    return <p>No users found.</p>;
  }

  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>
          {user.name}

          <button
            onClick={() => onDelete(user.id)}
          >
            Delete
          </button>
        </li>
      ))}
    </ul>
  );
}

function App() {
  const [users, setUsers] = useState([
    {
      id: 1,
      name: "Heng",
    },
    {
      id: 2,
      name: "Dara",
    },
    {
      id: 3,
      name: "Sokha",
    },
  ]);

  const [search, setSearch] = useState("");

  function addUser(name) {
    const newUser = {
      id: crypto.randomUUID(),
      name,
    };

    setUsers((currentUsers) => [
      ...currentUsers,
      newUser,
    ]);
  }

  function deleteUser(id) {
    setUsers((currentUsers) =>
      currentUsers.filter(
        (user) => user.id !== id
      )
    );
  }

  const filteredUsers = users.filter((user) =>
    user.name
      .toLowerCase()
      .includes(search.toLowerCase())
  );

  return (
    <main>
      <h1>User Management</h1>

      <UserForm onAdd={addUser} />

      <hr />

      <input
        value={search}
        onChange={(event) =>
          setSearch(event.target.value)
        }
        placeholder="Search users"
      />

      <p>
        Total Users: {filteredUsers.length}
      </p>

      <UserList
        users={filteredUsers}
        onDelete={deleteUser}
      />
    </main>
  );
}

export default App;
```

---

# 41. Learning Roadmap

A recommended React learning order:

```text
                    REACT
                      │
                      ▼
              ┌───────────────┐
              │ JavaScript    │
              │ ES6+          │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ JSX           │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Components    │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Props         │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ State         │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Events        │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Forms         │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ useEffect     │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ API / Fetch   │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ React Router  │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Context       │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Custom Hooks  │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ useReducer    │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ TypeScript    │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Performance   │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Testing       │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ Production    │
              └───────────────┘
```

---

# 🎯 React Skill Levels

## 🟢 Beginner

Learn:

```text
JavaScript
↓
JSX
↓
Components
↓
Props
↓
State
↓
Events
↓
Conditional Rendering
↓
Lists
↓
Forms
```

---

## 🟡 Intermediate

Learn:

```text
useEffect
↓
API Requests
↓
Custom Hooks
↓
Context
↓
useReducer
↓
React Router
↓
Local Storage
↓
Authentication
```

---

## 🔴 Advanced

Learn:

```text
TypeScript
↓
Architecture
↓
Performance
↓
Lazy Loading
↓
Suspense
↓
Testing
↓
Security
↓
Production Deployment
↓
Large-scale Application Architecture
```

---

# 🧠 React Mental Model

A useful way to think about React is:

```text
STATE
  ↓
RENDER
  ↓
USER INTERACTION
  ↓
STATE UPDATE
  ↓
RENDER AGAIN
```

For example:

```text
count = 0
   ↓
UI shows 0
   ↓
User clicks button
   ↓
setCount(1)
   ↓
React renders again
   ↓
UI shows 1
```

---

# 🔥 Important React Concepts

| Concept      | Purpose                               |
| ------------ | ------------------------------------- |
| JSX          | Write UI syntax                       |
| Component    | Reusable UI                           |
| Props        | Parent → Child data                   |
| State        | Component data that changes           |
| useState     | Manage state                          |
| useEffect    | Synchronize with external systems     |
| useRef       | Keep mutable values / DOM references  |
| useMemo      | Cache calculated values               |
| useCallback  | Cache function references             |
| Context      | Share values through a component tree |
| useReducer   | Manage complex state transitions      |
| Custom Hook  | Reuse stateful logic                  |
| React Router | Client-side routing                   |
| Suspense     | Coordinate loading UI                 |
| lazy         | Lazy-load components                  |
| memo         | Skip unnecessary child renders        |

---

# 🏆 Recommended React Project Progression

Build projects in this order:

## Project 1 — Counter

Learn:

```text
useState
Events
Components
```

## Project 2 — Todo App

Learn:

```text
State
Forms
Lists
Props
Delete
Update
```

## Project 3 — Weather App

Learn:

```text
API
fetch
useEffect
Loading
Error
```

## Project 4 — Blog

Learn:

```text
Routing
API
Forms
CRUD
Reusable Components
```

## Project 5 — E-Commerce

Learn:

```text
Products
Cart
Authentication
Routing
API
State Management
```

## Project 6 — Admin Dashboard

Learn:

```text
Authentication
Authorization
Charts
Tables
Pagination
Filtering
Search
API
Reusable Components
```

## Project 7 — Full Stack Application

Learn:

```text
React
   ↓
REST API
   ↓
Backend
   ↓
Database
```

Example:

```text
React
  │
  │ HTTP
  ▼
Express / Spring Boot / Laravel
  │
  │ SQL / ORM
  ▼
PostgreSQL / MySQL
```

---

# 📝 Quick Reference

## Create React project

```bash
npm create vite@latest my-app
cd my-app
npm install
npm run dev
```

## Install React Router

```bash
npm install react-router-dom
```

## Run development server

```bash
npm run dev
```

## Build

```bash
npm run build
```

## Preview production build

```bash
npm run preview
```

---

# 🇰🇭 សង្ខេបជាភាសាខ្មែរ

React គឺជា library សម្រាប់បង្កើត UI ដោយប្រើ Component។

លំដាប់ដែលគួររៀន៖

```text
JavaScript
   ↓
JSX
   ↓
Component
   ↓
Props
   ↓
useState
   ↓
Events
   ↓
Forms
   ↓
useEffect
   ↓
API
   ↓
Router
   ↓
Context
   ↓
Custom Hooks
   ↓
useReducer
   ↓
TypeScript
   ↓
Performance
   ↓
Testing
   ↓
Production
```

ចំណុចសំខាន់បំផុតគឺកុំរៀនតែ syntax។ ត្រូវបង្កើត project ពិតប្រាកដ ដើម្បីយល់ពីរបៀបដែល React application ដំណើរការ។

---

# 🚀 Final Goal

After completing this guide, you should be able to build applications such as:

```text
✅ Todo Application
✅ Blog
✅ Dashboard
✅ Admin Panel
✅ E-Commerce
✅ Authentication System
✅ CRUD Application
✅ API-based Application
✅ Large React Application
```

A strong React developer should understand:

```text
UI
+
Components
+
State
+
Data Flow
+
API
+
Routing
+
Authentication
+
Architecture
+
Performance
+
Testing
+
Security
```

---

# 📌 Conclusion

React is easiest to understand when you think in terms of:

```text
Components
     +
Props
     +
State
     +
Events
     +
Data
     ↓
User Interface
```

Start small, build projects, and gradually move toward larger applications.

**Happy Coding! 🚀**
