# ⚛️ React — មគ្គុទ្ទេសក៍ពេញលេញ (ចាប់ពីដំបូងដល់កម្រិតខ្ពស់)

> **កម្រិត:** Beginner → Advanced | **បច្ចុប្បន្នភាព:** React 18+

---

## 📋 តារាងមាតិកា

- [១. React គឺជាអ្វី?](#១-react-គឺជាអ្វី)
- [២. ការដំឡើង Environment](#២-ការដំឡើង-environment)
- [៣. JSX — វាក្យសម្ព័ន្ធពិសេស](#៣-jsx--វាក្យសម្ព័ន្ធពិសេស)
- [៤. Components](#៤-components)
- [៥. Props](#៥-props)
- [៦. State និង useState](#៦-state-និង-usestate)
- [៧. Event Handling](#៧-event-handling)
- [៨. Conditional Rendering](#៨-conditional-rendering)
- [៩. Lists និង Keys](#៩-lists-និង-keys)
- [១០. useEffect](#១០-useeffect)
- [១១. useRef](#១១-useref)
- [១២. useContext](#១២-usecontext)
- [១៣. useReducer](#១៣-usereducer)
- [១៤. Custom Hooks](#១៤-custom-hooks)
- [១៥. useMemo និង useCallback](#១៥-usememo-និង-usecallback)
- [១៦. React Router](#១៦-react-router)
- [១៧. Fetching Data (API)](#១៧-fetching-data-api)
- [១៨. Error Boundaries](#១៨-error-boundaries)
- [១៩. Performance Optimization](#១៩-performance-optimization)
- [២០. Best Practices](#២០-best-practices)

---

## ១. React គឺជាអ្វី?

**React** គឺជា JavaScript Library ដែលបង្កើតដោយ **Meta (Facebook)** សម្រាប់សង់ User Interface (UI) ។

### 🎯 ហេតុអ្វីត្រូវប្រើ React?

| លក្ខណៈ | ការពន្យល់ |
|--------|-----------|
| **Component-Based** | បែងចែក UI ជាផ្នែកៗតូចៗ ដើម្បីងាយ reuse |
| **Virtual DOM** | Render លឿនជាងធម្មតាដោយប្រើ Virtual DOM |
| **Declarative** | សរសេរ code ដោយប្រាប់ *"អ្វី"* ដែលចង់បង្ហាញ មិនមែន *"យ៉ាងដូចម្តេច"* |
| **One-way Data Flow** | Data ហូរពី Parent → Child ធ្វើឱ្យ debug ងាយ |
| **Large Ecosystem** | Community ធំ, libraries ច្រើន |

---

## ២. ការដំឡើង Environment

### 📦 វិធីទី១ — Create React App (CRA)

```bash
# ដំឡើង Node.js មុន (https://nodejs.org)
node --version   # v18+ ត្រូវការ

# បង្កើត project ថ្មី
npx create-react-app my-app

# ចូលទៅក្នុង folder
cd my-app

# រត់ development server
npm start
```

### ⚡ វិធីទី២ — Vite (ណែនាំ — លឿនជាង)

```bash
# បង្កើត project ជាមួយ Vite
npm create vite@latest my-app -- --template react

cd my-app
npm install
npm run dev
```

### 📁 Structure នៃ Project

```
my-app/
├── public/
│   └── index.html          ← HTML template
├── src/
│   ├── App.jsx             ← Component ចម្បង
│   ├── main.jsx            ← Entry point
│   └── index.css           ← Global styles
├── package.json
└── vite.config.js
```

---

## ៣. JSX — វាក្យសម្ព័ន្ធពិសេស

**JSX** (JavaScript XML) អនុញ្ញាតឱ្យសរសេរ HTML នៅក្នុង JavaScript ។

### ✅ ច្បាប់ JSX សំខាន់ៗ

```jsx
// ✅ ត្រឹមត្រូវ — ត្រូវ return element តែ១
function App() {
  return (
    <div>
      <h1>សួស្តី React!</h1>
      <p>នេះគឺជា JSX</p>
    </div>
  );
}

// ✅ ប្រើ Fragment ប្រសិនបើមិនចង់ wrapper div
function App() {
  return (
    <>
      <h1>សួស្តី!</h1>
      <p>React Fragment</p>
    </>
  );
}
```

### 🔤 ភាពខុសគ្នា JSX vs HTML

```jsx
// HTML                         JSX
// class="box"          →      className="box"
// for="name"           →      htmlFor="name"
// <br>                 →      <br />
// onclick="fn()"       →      onClick={fn}
// style="color:red"    →      style={{ color: 'red' }}

function Example() {
  return (
    <div className="box" style={{ color: 'red', fontSize: 16 }}>
      <label htmlFor="name">ឈ្មោះ</label>
      <input id="name" type="text" />
      <br />
    </div>
  );
}
```

### 🔧 JavaScript Expression ក្នុង JSX

```jsx
function Greeting() {
  const name = "សុខា";
  const age = 25;
  const isLoggedIn = true;

  return (
    <div>
      {/* ប្រើ {} ដើម្បីបញ្ចូល JavaScript */}
      <h1>សួស្តី, {name}!</h1>
      <p>អាយុ: {age} ឆ្នាំ</p>
      <p>ស្ថានភាព: {isLoggedIn ? "បានចូល" : "មិនទាន់ចូល"}</p>
      <p>គណនា: {age * 2}</p>
    </div>
  );
}
```

---

## ៤. Components

**Component** គឺជា JavaScript function ដែល return JSX ។

### 🏗️ Function Component (ណែនាំ)

```jsx
// Component ធម្មតា
function Welcome() {
  return <h1>សួស្តីមកកាន់ React!</h1>;
}

// Arrow Function Component
const Welcome = () => {
  return <h1>សួស្តីមកកាន់ React!</h1>;
};

// Arrow Function ខ្លី (implicit return)
const Welcome = () => <h1>សួស្តីមកកាន់ React!</h1>;
```

### 📐 ការរៀបចំ Component ឱ្យបានត្រឹមត្រូវ

```jsx
// ✅ ល្អ — ឈ្មោះ Component ចាប់ផ្តើមដោយអក្សរធំ (PascalCase)
function UserCard() {
  return (
    <div className="card">
      <h2>ព័ត៌មានអ្នកប្រើ</h2>
    </div>
  );
}

// ✅ ល្អ — Export component
export default UserCard;

// នៅក្នុង App.jsx
import UserCard from './UserCard';

function App() {
  return (
    <div>
      <UserCard />   {/* ប្រើ Component ដូចជា HTML tag */}
      <UserCard />   {/* Reuse បានជាច្រើនដង */}
    </div>
  );
}
```

### 🗂️ Component Composition

```jsx
// Header Component
function Header() {
  return (
    <header>
      <nav>
        <Logo />
        <Navigation />
      </nav>
    </header>
  );
}

// Logo Component
function Logo() {
  return <img src="/logo.png" alt="Logo" />;
}

// Navigation Component
function Navigation() {
  return (
    <ul>
      <li>ទំព័រដើម</li>
      <li>អំពីយើង</li>
      <li>ទំនាក់ទំនង</li>
    </ul>
  );
}
```

---

## ៥. Props

**Props** (Properties) ជា parameter ដែលបញ្ជូន data ពី Parent Component ទៅ Child Component ។

### 📨 ការប្រើ Props មូលដ្ឋាន

```jsx
// Child Component — ទទួល props
function Greeting({ name, age }) {
  return (
    <div>
      <h1>សួស្តី, {name}!</h1>
      <p>អាយុ: {age} ឆ្នាំ</p>
    </div>
  );
}

// Parent Component — ផ្ញើ props
function App() {
  return (
    <div>
      <Greeting name="សុខា" age={25} />
      <Greeting name="ចន្ទ" age={30} />
    </div>
  );
}
```

### 🎁 Props Types ផ្សេងៗ

```jsx
function UserProfile({
  name,           // string
  age,            // number
  isActive,       // boolean
  hobbies,        // array
  address,        // object
  onClick,        // function
  children,       // JSX content
}) {
  return (
    <div>
      <h2>{name}</h2>
      <p>អាយុ: {age}</p>
      <p>ស្ថានភាព: {isActive ? "✅ សកម្ម" : "❌ អសកម្ម"}</p>
      <ul>
        {hobbies.map((hobby, i) => <li key={i}>{hobby}</li>)}
      </ul>
      <p>ក្រុង: {address.city}</p>
      <button onClick={onClick}>ចុច</button>
      {children}  {/* JSX children */}
    </div>
  );
}

// ការប្រើ
function App() {
  return (
    <UserProfile
      name="ដារ៉ា"
      age={28}
      isActive={true}
      hobbies={["អានសៀវភៅ", "លេងកីឡា"]}
      address={{ city: "ភ្នំពេញ", country: "កម្ពុជា" }}
      onClick={() => alert("ចុចហើយ!")}
    >
      <p>នេះគឺ children content</p>
    </UserProfile>
  );
}
```

### 🛡️ Default Props

```jsx
function Button({ text = "ចុច", color = "blue", size = "medium" }) {
  return (
    <button
      className={`btn btn-${color} btn-${size}`}
    >
      {text}
    </button>
  );
}

// ប្រើដោយមិនបញ្ជាក់ props — នឹងប្រើ default
<Button />                        // text="ចុច", color="blue", size="medium"
<Button text="រក្សាទុក" color="green" />   // override ផ្នែក
```

---

## ៦. State និង useState

**State** ជា data ដែលប្រែប្រួលបាន នៅពេល user interact ។ ពេល state ផ្លាស់ប្តូរ, React **re-render** component ។

### 🔄 useState មូលដ្ឋាន

```jsx
import { useState } from 'react';

function Counter() {
  // useState(initialValue) → [currentValue, setterFunction]
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>រាប់: {count}</h2>
      <button onClick={() => setCount(count + 1)}>➕ បន្ថែម</button>
      <button onClick={() => setCount(count - 1)}>➖ ដកចេញ</button>
      <button onClick={() => setCount(0)}>🔄 Reset</button>
    </div>
  );
}
```

### 📝 State ជាមួយ String

```jsx
function NameInput() {
  const [name, setName] = useState("");

  return (
    <div>
      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
        placeholder="បញ្ចូលឈ្មោះ..."
      />
      <p>ឈ្មោះ: {name || "នៅទទេ"}</p>
      <p>ប្រវែង: {name.length} តួអក្សរ</p>
    </div>
  );
}
```

### 🗃️ State ជាមួយ Object

```jsx
function UserForm() {
  const [user, setUser] = useState({
    name: "",
    email: "",
    age: 0,
  });

  // ✅ ល្អ — Spread ដើម្បីរក្សា fields ផ្សេង
  const updateField = (field, value) => {
    setUser(prev => ({ ...prev, [field]: value }));
  };

  return (
    <form>
      <input
        value={user.name}
        onChange={(e) => updateField('name', e.target.value)}
        placeholder="ឈ្មោះ"
      />
      <input
        value={user.email}
        onChange={(e) => updateField('email', e.target.value)}
        placeholder="អ៊ីមែល"
      />
      <p>ព័ត៌មាន: {user.name} ({user.email})</p>
    </form>
  );
}
```

### 📋 State ជាមួយ Array

```jsx
function TodoList() {
  const [todos, setTodos] = useState([]);
  const [input, setInput] = useState("");

  // ✅ បន្ថែម item
  const addTodo = () => {
    if (!input.trim()) return;
    setTodos(prev => [...prev, { id: Date.now(), text: input, done: false }]);
    setInput("");
  };

  // ✅ លុប item
  const removeTodo = (id) => {
    setTodos(prev => prev.filter(todo => todo.id !== id));
  };

  // ✅ Toggle done
  const toggleTodo = (id) => {
    setTodos(prev =>
      prev.map(todo =>
        todo.id === id ? { ...todo, done: !todo.done } : todo
      )
    );
  };

  return (
    <div>
      <input
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="បន្ថែមការងារ..."
      />
      <button onClick={addTodo}>បន្ថែម</button>

      <ul>
        {todos.map(todo => (
          <li key={todo.id}>
            <span
              style={{ textDecoration: todo.done ? 'line-through' : 'none' }}
              onClick={() => toggleTodo(todo.id)}
            >
              {todo.text}
            </span>
            <button onClick={() => removeTodo(todo.id)}>🗑️</button>
          </li>
        ))}
      </ul>

      <p>សរុប: {todos.length} | រួចរាល់: {todos.filter(t => t.done).length}</p>
    </div>
  );
}
```

---

## ៧. Event Handling

React ប្រើ **Synthetic Events** ដែលមានដំណើរការដូចគ្នានៅគ្រប់ browser ។

```jsx
function EventExamples() {
  // onClick
  const handleClick = () => alert("ចុចហើយ!");

  // onChange
  const handleChange = (e) => console.log(e.target.value);

  // onSubmit
  const handleSubmit = (e) => {
    e.preventDefault(); // ⛔ រារាំង browser reload
    console.log("Form submitted");
  };

  // onMouseEnter / onMouseLeave
  const handleHover = () => console.log("Mouse hover!");

  // onKeyDown
  const handleKeyDown = (e) => {
    if (e.key === 'Enter') console.log("Enter pressed");
  };

  return (
    <div>
      <button onClick={handleClick}>Click</button>
      <button onClick={() => alert("Inline!")}>Inline Click</button>

      <input onChange={handleChange} onKeyDown={handleKeyDown} />

      <form onSubmit={handleSubmit}>
        <button type="submit">Submit</button>
      </form>

      <div onMouseEnter={handleHover}>Hover me</div>
    </div>
  );
}
```

### 🎯 ការបញ្ជូន Argument ទៅ Event Handler

```jsx
function ItemList() {
  const items = ["ផ្លែប៉ោម", "ផ្លែចេក", "ផ្លែក្រូច"];

  const handleDelete = (itemName) => {
    alert(`លុប: ${itemName}`);
  };

  return (
    <ul>
      {items.map((item) => (
        <li key={item}>
          {item}
          {/* ✅ ប្រើ arrow function ដើម្បីបញ្ជូន argument */}
          <button onClick={() => handleDelete(item)}>លុប</button>
        </li>
      ))}
    </ul>
  );
}
```

---

## ៨. Conditional Rendering

```jsx
function Dashboard({ isLoggedIn, userRole, notifications }) {
  // វិធី ១ — if/else statement
  if (!isLoggedIn) {
    return <LoginPage />;
  }

  return (
    <div>
      {/* វិធី ២ — Ternary operator */}
      <h1>{isLoggedIn ? "សួស្តីមកវិញ!" : "សូមចូល"}</h1>

      {/* វិធី ៣ — && operator (render ប្រសិនបើ true) */}
      {notifications > 0 && (
        <span className="badge">{notifications}</span>
      )}

      {/* វិធី ៤ — Nested ternary (កុំប្រើច្រើន) */}
      <p>
        {userRole === 'admin'
          ? "👑 អ្នកគ្រប់គ្រង"
          : userRole === 'editor'
          ? "✏️ អ្នកកែ"
          : "👤 អ្នកប្រើ"}
      </p>

      {/* វិធី ៥ — Switch ជាមួយ helper function */}
      {renderRoleBadge(userRole)}
    </div>
  );
}

// ✅ Helper function ច្បាស់ជាង nested ternary
function renderRoleBadge(role) {
  switch (role) {
    case 'admin':   return <span className="badge-admin">Admin</span>;
    case 'editor':  return <span className="badge-editor">Editor</span>;
    default:        return <span className="badge-user">User</span>;
  }
}
```

---

## ៩. Lists និង Keys

```jsx
function ProductList() {
  const products = [
    { id: 1, name: "កាហ្វេ", price: 2000, inStock: true },
    { id: 2, name: "តែ", price: 1500, inStock: false },
    { id: 3, name: "ទឹកផ្លែឈើ", price: 2500, inStock: true },
  ];

  return (
    <ul>
      {products.map((product) => (
        // ✅ key ត្រូវតែ unique ហើយ stable (ប្រើ id, មិនមែន index)
        <li key={product.id}>
          <strong>{product.name}</strong> — {product.price}រៀល
          {product.inStock
            ? <span style={{ color: 'green' }}> ✅ មានស្ត็រ</span>
            : <span style={{ color: 'red' }}> ❌ អស់ស្ត็រ</span>
          }
        </li>
      ))}
    </ul>
  );
}
```

### ⚠️ ហេតុអ្វីត្រូវប្រើ key?

```jsx
// ❌ មិនល្អ — ប្រើ index ជា key (problem ពេល reorder/delete)
{items.map((item, index) => <li key={index}>{item}</li>)}

// ✅ ល្អ — ប្រើ unique ID
{items.map((item) => <li key={item.id}>{item.name}</li>)}

// ✅ ល្អ — ប្រើ string unique ប្រសិនបើគ្មាន id
{items.map((item) => <li key={item.slug}>{item.name}</li>)}
```

---

## ១០. useEffect

**useEffect** ជា Hook ដើម្បីដំណើរការ **side effects**: fetch data, subscriptions, timer, DOM manipulation ។

### 🕐 Dependency Array

```jsx
import { useState, useEffect } from 'react';

function Examples() {
  const [count, setCount] = useState(0);
  const [userId, setUserId] = useState(1);

  // ▶️ រត់ ពេលដំបូង និងគ្រប់ re-render
  useEffect(() => {
    console.log("render ម្តងៗ");
  }); // គ្មាន dependency array

  // ▶️ រត់ ម្តងប៉ុណ្ណោះ (component mount)
  useEffect(() => {
    console.log("mount ម្តង");
  }, []); // array ទទេ

  // ▶️ រត់ ពេល count ផ្លាស់ប្តូរ
  useEffect(() => {
    console.log("count: ", count);
  }, [count]);

  // ▶️ Cleanup function (unmount ឬ dependency ផ្លាស់ប្តូរ)
  useEffect(() => {
    const timer = setInterval(() => {
      console.log("tick");
    }, 1000);

    return () => clearInterval(timer); // ✅ Cleanup
  }, []);
}
```

### 🌐 Fetch Data ជាមួយ useEffect

```jsx
function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    // ✅ abort controller ដើម្បីបញ្ឈប់ request ចាស់
    const controller = new AbortController();

    const fetchUser = async () => {
      try {
        setLoading(true);
        setError(null);

        const res = await fetch(
          `https://jsonplaceholder.typicode.com/users/${userId}`,
          { signal: controller.signal }
        );

        if (!res.ok) throw new Error("មិនអាច load ទិន្នន័យ");

        const data = await res.json();
        setUser(data);
      } catch (err) {
        if (err.name !== 'AbortError') {
          setError(err.message);
        }
      } finally {
        setLoading(false);
      }
    };

    fetchUser();

    return () => controller.abort(); // ✅ Cleanup
  }, [userId]); // re-fetch ពេល userId ផ្លាស់ប្តូរ

  if (loading) return <p>⏳ កំពុង Load...</p>;
  if (error)   return <p>❌ Error: {error}</p>;
  if (!user)   return null;

  return (
    <div>
      <h2>{user.name}</h2>
      <p>📧 {user.email}</p>
      <p>📞 {user.phone}</p>
    </div>
  );
}
```

---

## ១១. useRef

**useRef** ប្រើសម្រាប់: ១) access DOM element ២) រក្សា mutable value ដោយមិន re-render ។

```jsx
import { useRef, useState, useEffect } from 'react';

function RefExamples() {
  // ១. DOM Access
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus(); // focus input element
  };

  const clearInput = () => {
    inputRef.current.value = ""; // ផ្លាស់ប្ដូរ DOM ដោយផ្ទាល់
    inputRef.current.focus();
  };

  // ២. Mutable Value (មិន trigger re-render)
  const renderCount = useRef(0);
  const [state, setState] = useState(0);

  useEffect(() => {
    renderCount.current += 1;
    console.log(`Render #${renderCount.current}`);
  });

  // ៣. Store previous value
  const prevState = useRef(state);
  useEffect(() => {
    prevState.current = state;
  }, [state]);

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="ជ្រើសរើស..." />
      <button onClick={focusInput}>Focus</button>
      <button onClick={clearInput}>Clear</button>

      <p>State: {state} | មុន: {prevState.current}</p>
      <button onClick={() => setState(s => s + 1)}>Update State</button>
      <p>Renders: {renderCount.current}</p>
    </div>
  );
}
```

---

## ១២. useContext

**useContext** ដោះស្រាយបញ្ហា **Prop Drilling** ដោយប្រើ global state ។

```jsx
import { createContext, useContext, useState } from 'react';

// ១. បង្កើត Context
const ThemeContext = createContext(null);

// ២. បង្កើត Provider
function ThemeProvider({ children }) {
  const [theme, setTheme] = useState('light');

  const toggleTheme = () => {
    setTheme(prev => prev === 'light' ? 'dark' : 'light');
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

// ✅ Custom hook ដើម្បីងាយប្រើ
function useTheme() {
  const context = useContext(ThemeContext);
  if (!context) throw new Error("useTheme ត្រូវប្រើនៅក្នុង ThemeProvider");
  return context;
}

// ៣. ប្រើ Context នៅ Component ណាក៏បាន
function Navbar() {
  const { theme, toggleTheme } = useTheme();
  return (
    <nav style={{ background: theme === 'light' ? '#fff' : '#333' }}>
      <h1>Logo</h1>
      <button onClick={toggleTheme}>
        {theme === 'light' ? '🌙 Dark' : '☀️ Light'}
      </button>
    </nav>
  );
}

function Page() {
  const { theme } = useTheme();
  return (
    <div style={{ color: theme === 'light' ? '#000' : '#fff' }}>
      <p>Theme បច្ចុប្បន្ន: {theme}</p>
    </div>
  );
}

// ៤. Wrap App ជាមួយ Provider
function App() {
  return (
    <ThemeProvider>
      <Navbar />
      <Page />
    </ThemeProvider>
  );
}
```

---

## ១៣. useReducer

**useReducer** ជាជម្រើសល្អជាង useState ពេល state logic ស្មុគស្មាញ ។

```jsx
import { useReducer } from 'react';

// ១. Define initial state
const initialState = {
  items: [],
  total: 0,
  loading: false,
};

// ២. Define reducer function
function cartReducer(state, action) {
  switch (action.type) {
    case 'ADD_ITEM': {
      const exists = state.items.find(i => i.id === action.item.id);
      const items = exists
        ? state.items.map(i =>
            i.id === action.item.id
              ? { ...i, qty: i.qty + 1 }
              : i
          )
        : [...state.items, { ...action.item, qty: 1 }];

      return {
        ...state,
        items,
        total: state.total + action.item.price,
      };
    }

    case 'REMOVE_ITEM': {
      const item = state.items.find(i => i.id === action.id);
      return {
        ...state,
        items: state.items.filter(i => i.id !== action.id),
        total: state.total - (item ? item.price * item.qty : 0),
      };
    }

    case 'CLEAR_CART':
      return initialState;

    default:
      throw new Error(`Action មិនស្គាល់: ${action.type}`);
  }
}

// ៣. ប្រើ useReducer
function ShoppingCart() {
  const [state, dispatch] = useReducer(cartReducer, initialState);

  const products = [
    { id: 1, name: "ភីហ្សា", price: 15000 },
    { id: 2, name: "ហាំបឺហ្គ័រ", price: 12000 },
  ];

  return (
    <div>
      <h2>📦 ហាង</h2>
      {products.map(p => (
        <div key={p.id}>
          <span>{p.name} — {p.price}រៀល</span>
          <button onClick={() => dispatch({ type: 'ADD_ITEM', item: p })}>
            ➕ បន្ថែម
          </button>
        </div>
      ))}

      <h2>🛒 កន្ត្រក ({state.items.length} ប្រភេទ)</h2>
      {state.items.map(item => (
        <div key={item.id}>
          {item.name} x{item.qty}
          <button onClick={() => dispatch({ type: 'REMOVE_ITEM', id: item.id })}>
            🗑️
          </button>
        </div>
      ))}

      <p>💰 សរុប: {state.total.toLocaleString()}រៀល</p>
      <button onClick={() => dispatch({ type: 'CLEAR_CART' })}>
        🧹 លុបទាំងអស់
      </button>
    </div>
  );
}
```

---

## ១៤. Custom Hooks

**Custom Hooks** ជា function ដែលចាប់ផ្តើមដោយ `use` ហើយ reuse logic បាន ។

### 🪝 useLocalStorage

```jsx
import { useState, useEffect } from 'react';

function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    try {
      const stored = localStorage.getItem(key);
      return stored ? JSON.parse(stored) : initialValue;
    } catch {
      return initialValue;
    }
  });

  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [key, value]);

  return [value, setValue];
}

// ការប្រើ
function Settings() {
  const [theme, setTheme] = useLocalStorage('theme', 'light');
  const [language, setLanguage] = useLocalStorage('lang', 'km');

  return (
    <div>
      <button onClick={() => setTheme(t => t === 'light' ? 'dark' : 'light')}>
        Theme: {theme}
      </button>
      <button onClick={() => setLanguage(l => l === 'km' ? 'en' : 'km')}>
        ភាសា: {language}
      </button>
    </div>
  );
}
```

### 🌐 useFetch

```jsx
import { useState, useEffect, useCallback } from 'react';

function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  const fetchData = useCallback(async () => {
    const controller = new AbortController();

    try {
      setLoading(true);
      setError(null);

      const res = await fetch(url, { signal: controller.signal });
      if (!res.ok) throw new Error(`HTTP ${res.status}`);

      const json = await res.json();
      setData(json);
    } catch (err) {
      if (err.name !== 'AbortError') setError(err.message);
    } finally {
      setLoading(false);
    }

    return () => controller.abort();
  }, [url]);

  useEffect(() => {
    fetchData();
  }, [fetchData]);

  return { data, loading, error, refetch: fetchData };
}

// ការប្រើ
function PostsList() {
  const { data, loading, error, refetch } = useFetch(
    'https://jsonplaceholder.typicode.com/posts?_limit=5'
  );

  if (loading) return <p>⏳ Loading...</p>;
  if (error)   return <p>❌ {error} <button onClick={refetch}>ព្យាយាមម្ដងទៀត</button></p>;

  return (
    <ul>
      {data?.map(post => <li key={post.id}>{post.title}</li>)}
    </ul>
  );
}
```

### ⏱️ useDebounce

```jsx
import { useState, useEffect } from 'react';

function useDebounce(value, delay = 500) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => clearTimeout(timer); // cancel ប្រសិនបើ value ផ្លាស់ប្ដូរ
  }, [value, delay]);

  return debouncedValue;
}

// ការប្រើ — Search ពី API ដោយ delay
function SearchBar() {
  const [query, setQuery] = useState('');
  const debouncedQuery = useDebounce(query, 300);

  useEffect(() => {
    if (debouncedQuery) {
      console.log(`🔍 Search: ${debouncedQuery}`);
      // fetch search results...
    }
  }, [debouncedQuery]);

  return (
    <input
      value={query}
      onChange={(e) => setQuery(e.target.value)}
      placeholder="ស្វែងរក..."
    />
  );
}
```

---

## ១៥. useMemo និង useCallback

ប្រើ Hooks ទាំងនេះ ដើម្បី **optimize performance** ។

### 🧮 useMemo — Cache computation result

```jsx
import { useState, useMemo } from 'react';

function ExpensiveCalculation({ numbers, filter }) {
  const [count, setCount] = useState(0);

  // ✅ useMemo — compute ម្តងប៉ុណ្ណោះ ពេល numbers ឬ filter ផ្លាស់ប្ដូរ
  const filteredNumbers = useMemo(() => {
    console.log("🔄 Computing...");
    return numbers
      .filter(n => n > filter)
      .sort((a, b) => a - b);
  }, [numbers, filter]); // dependencies

  return (
    <div>
      <p>លទ្ធផល: {filteredNumbers.join(', ')}</p>
      {/* re-render count ប៉ុន្តែ computation មិនរត់ */}
      <button onClick={() => setCount(c => c + 1)}>Rerender ({count})</button>
    </div>
  );
}
```

### 🔁 useCallback — Cache function reference

```jsx
import { useState, useCallback, memo } from 'react';

// React.memo — skip re-render ប្រសិនបើ props មិនផ្លាស់ប្ដូរ
const ExpensiveChild = memo(function ExpensiveChild({ onClick }) {
  console.log("Child renders");
  return <button onClick={onClick}>Child Button</button>;
});

function Parent() {
  const [count, setCount] = useState(0);
  const [text, setText] = useState('');

  // ✅ useCallback — function reference ដដែល លុះត្រា count ផ្លាស់ប្ដូរ
  const handleClick = useCallback(() => {
    setCount(c => c + 1);
  }, []); // stable reference

  return (
    <div>
      <input value={text} onChange={(e) => setText(e.target.value)} />
      <p>Count: {count}</p>
      {/* ExpensiveChild មិន re-render ពេល text ផ្លាស់ប្ដូរ */}
      <ExpensiveChild onClick={handleClick} />
    </div>
  );
}
```

> **💡 ចំណាំ:** កុំ overuse useMemo/useCallback — ប្រើតែពេល performance ពិតជាជាបញ្ហា ។

---

## ១៦. React Router

**React Router v6+** ដើម្បីបង្កើត navigation ។

```bash
npm install react-router-dom
```

```jsx
import {
  BrowserRouter,
  Routes,
  Route,
  Link,
  NavLink,
  useNavigate,
  useParams,
  useSearchParams,
} from 'react-router-dom';

// Pages
function Home()     { return <h1>🏠 ទំព័រដើម</h1>; }
function About()    { return <h1>ℹ️ អំពីយើង</h1>; }
function NotFound() { return <h1>❌ 404 - រកមិនឃើញ</h1>; }

// Dynamic route — /users/:id
function UserDetail() {
  const { id } = useParams();
  return <h1>👤 User #{id}</h1>;
}

// Search params — /search?q=react
function Search() {
  const [searchParams, setSearchParams] = useSearchParams();
  const query = searchParams.get('q') || '';

  return (
    <div>
      <input
        value={query}
        onChange={(e) => setSearchParams({ q: e.target.value })}
      />
      <p>ស្វែងរក: {query}</p>
    </div>
  );
}

// Navigation
function Navbar() {
  const navigate = useNavigate();

  return (
    <nav>
      <Link to="/">ដើម</Link>
      <Link to="/about">អំពី</Link>
      {/* NavLink — add active class automatically */}
      <NavLink to="/search" className={({ isActive }) => isActive ? 'active' : ''}>
        ស្វែងរក
      </NavLink>
      <button onClick={() => navigate('/about')}>Programmatic Nav</button>
    </nav>
  );
}

// App Router setup
function App() {
  return (
    <BrowserRouter>
      <Navbar />
      <Routes>
        <Route path="/"           element={<Home />} />
        <Route path="/about"      element={<About />} />
        <Route path="/users/:id"  element={<UserDetail />} />
        <Route path="/search"     element={<Search />} />
        <Route path="*"           element={<NotFound />} />
      </Routes>
    </BrowserRouter>
  );
}
```

---

## ១៧. Fetching Data (API)

### 🔷 ជាមួយ Fetch API + Custom Hook

```jsx
// hooks/useApi.js
import { useState, useCallback } from 'react';

export function useApi() {
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const request = useCallback(async (url, options = {}) => {
    try {
      setLoading(true);
      setError(null);

      const res = await fetch(url, {
        headers: { 'Content-Type': 'application/json' },
        ...options,
      });

      if (!res.ok) throw new Error(`Error ${res.status}`);
      return await res.json();
    } catch (err) {
      setError(err.message);
      throw err;
    } finally {
      setLoading(false);
    }
  }, []);

  return { loading, error, request };
}

// ការប្រើ
function CreatePost() {
  const { loading, error, request } = useApi();
  const [title, setTitle] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      const post = await request('https://jsonplaceholder.typicode.com/posts', {
        method: 'POST',
        body: JSON.stringify({ title, userId: 1 }),
      });
      alert(`✅ បានបង្កើត post #${post.id}`);
    } catch {
      // error handled by hook
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input value={title} onChange={e => setTitle(e.target.value)} />
      <button type="submit" disabled={loading}>
        {loading ? '⏳ Loading...' : '📤 Submit'}
      </button>
      {error && <p style={{ color: 'red' }}>❌ {error}</p>}
    </form>
  );
}
```

---

## ១៨. Error Boundaries

**Error Boundaries** ចាប់ JavaScript errors ហើយបង្ហាញ fallback UI ។

```jsx
import { Component } from 'react';

// ⚠️ Error Boundaries ត្រូវប្រើ Class Component
class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false, error: null };
  }

  // ចាប់ error ហើយ update state
  static getDerivedStateFromError(error) {
    return { hasError: true, error };
  }

  // log error
  componentDidCatch(error, errorInfo) {
    console.error('Error caught:', error, errorInfo);
    // ផ្ញើ error ទៅ logging service...
  }

  render() {
    if (this.state.hasError) {
      return (
        <div style={{ padding: 20, border: '1px solid red', borderRadius: 8 }}>
          <h2>⚠️ មានបញ្ហាបច្ចេកទេស</h2>
          <p>{this.state.error?.message}</p>
          <button onClick={() => this.setState({ hasError: false, error: null })}>
            🔄 ព្យាយាមម្ដងទៀត
          </button>
        </div>
      );
    }

    return this.props.children;
  }
}

// ការប្រើ
function App() {
  return (
    <ErrorBoundary>
      <Header />
      <ErrorBoundary>
        {/* Component ក្នុង nested boundary */}
        <RiskyComponent />
      </ErrorBoundary>
      <Footer />
    </ErrorBoundary>
  );
}
```

---

## ១៩. Performance Optimization

### 🚀 React.memo

```jsx
import { memo } from 'react';

// ✅ Component នឹង re-render លុះណាតែ props ផ្លាស់ប្ដូរ
const UserCard = memo(function UserCard({ user, onSelect }) {
  console.log(`Rendering: ${user.name}`);
  return (
    <div onClick={() => onSelect(user.id)}>
      <h3>{user.name}</h3>
      <p>{user.email}</p>
    </div>
  );
});

// Custom comparison function
const UserCard = memo(
  function UserCard({ user }) { ... },
  (prevProps, nextProps) => prevProps.user.id === nextProps.user.id
);
```

### 💤 Lazy Loading

```jsx
import { lazy, Suspense } from 'react';

// ✅ Load component ពេលត្រូវការប៉ុណ្ណោះ (code splitting)
const HeavyChart     = lazy(() => import('./HeavyChart'));
const AdminDashboard = lazy(() => import('./AdminDashboard'));

function App() {
  return (
    <Suspense fallback={<div>⏳ Loading component...</div>}>
      <HeavyChart />
    </Suspense>
  );
}
```

### 🖼️ Virtualization (Lists ធំ)

```bash
npm install react-window
```

```jsx
import { FixedSizeList } from 'react-window';

// ✅ render តែ rows ដែល visible ប៉ុណ្ណោះ (ល្អសម្រាប់ list ១០,០០០+ items)
function HugeList({ items }) {
  const Row = ({ index, style }) => (
    <div style={style}>{items[index].name}</div>
  );

  return (
    <FixedSizeList
      height={400}
      width="100%"
      itemCount={items.length}
      itemSize={50}
    >
      {Row}
    </FixedSizeList>
  );
}
```

---

## ២០. Best Practices

### ✅ ច្បាប់ Code ល្អ

```jsx
// ✅ ១. ឈ្មោះ Component — PascalCase
function UserProfile() { ... }

// ✅ ២. ឈ្មោះ Hook — camelCase ចាប់ផ្តើម use
function useAuth() { ... }

// ✅ ៣. ឈ្មោះ Event Handler — handle + EventName
const handleSubmit = () => { ... };
const handleInputChange = () => { ... };

// ✅ ៤. ចែក Component ឱ្យតូច (Single Responsibility)
// ❌ មិនល្អ — Component ធំ ១ ដែលធ្វើអ្វីៗទាំងអស់
function BigPage() { /* 500+ lines */ }

// ✅ ល្អ — ចែកជា components តូចៗ
function Page() {
  return (
    <>
      <PageHeader />
      <PageContent />
      <PageFooter />
    </>
  );
}

// ✅ ៥. Custom Hooks ដើម្បី reuse logic
function useForm(initialValues) { ... }
function useAuth() { ... }

// ✅ ៦. Constants ខ្ពស់ (UPPER_SNAKE_CASE)
const MAX_RETRY_COUNT = 3;
const API_BASE_URL = 'https://api.example.com';

// ✅ ៧. Early return ដើម្បីកាត់ nesting
function UserPage({ userId }) {
  const { user, loading, error } = useFetch(`/api/users/${userId}`);

  if (loading) return <Spinner />;
  if (error)   return <ErrorMessage error={error} />;
  if (!user)   return <NotFound />;

  return <UserDetails user={user} />;
}
```

### 📁 Project Structure (ណែនាំ)

```
src/
├── components/          ← Reusable components
│   ├── Button/
│   │   ├── Button.jsx
│   │   ├── Button.module.css
│   │   └── index.js
│   └── Modal/
├── pages/               ← Page components (React Router)
│   ├── Home.jsx
│   └── About.jsx
├── hooks/               ← Custom hooks
│   ├── useAuth.js
│   └── useFetch.js
├── context/             ← Context providers
│   └── AuthContext.jsx
├── services/            ← API calls
│   └── api.js
├── utils/               ← Helper functions
│   └── formatDate.js
├── constants/           ← Constants
│   └── routes.js
└── App.jsx
```

---

## 🎓 សង្ខេបចំណេះដឹង

| Topic | Hook/Concept | ការប្រើ |
|-------|-------------|---------|
| Local state | `useState` | ទំនាក់ទំនងរវាង UI state |
| Side effects | `useEffect` | Fetch, timer, subscriptions |
| DOM access | `useRef` | Focus, scroll, mutable values |
| Global state | `useContext` | Theme, auth, language |
| Complex state | `useReducer` | Shopping cart, forms |
| Performance | `useMemo`, `useCallback`, `memo` | Expensive calculations |
| Routing | React Router | Navigation, URL params |
| Code splitting | `lazy`, `Suspense` | Load pages on demand |

---

## 📚 ធនធានបន្ថែម

- 📖 [React Official Docs](https://react.dev) — ឯកសារផ្លូវការ
- 🎮 [React Tutorial](https://react.dev/learn) — Tutorial ជាជំហានៗ
- 🔧 [React DevTools](https://react.dev/learn/react-developer-tools) — Debug tool
- 📦 [npm Packages](https://npmjs.com) — Libraries

---

<div align="center">

**🇰🇭 បង្កើតដោយ ❤️ សម្រាប់ Developer ខ្មែរ**

*React — Learn once, write anywhere*

</div>
