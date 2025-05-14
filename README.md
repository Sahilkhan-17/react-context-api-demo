# React Context Api

The Context API is like a "global bulletin board" for your React app where you can pin information that many components need, without passing it through every level manually.

## Why Use Context? 
- Normally, data is passed from parent to child via props (like a bucket brigade)
- For data needed by many components, this becomes messy (prop drilling)
- Context lets you share data globally without passing props

## How It Works 🔧

1. **Create the Context** (The bulletin board):
   ```javascript
   const UserContext = React.createContext();
   ```

2. **Provide the Data** (Pin info to the board):
   ```jsx
   <UserContext.Provider value={{name: "John"}}>
     <YourApp />
   </UserContext.Provider>
   ```

3. **Consume the Data** (Read the pinned info):
   ```jsx
   function Component() {
     const user = React.useContext(UserContext);
     return <h1>Welcome, {user.name}!</h1>;
   }
   ```

## When to Use It ✅
- Theme preferences (light/dark mode)
- User authentication data
- Preferred language (i18n)
- Any global settings

## Simple Example 🌟
```jsx
// 1. Create context
const ThemeContext = React.createContext();

function App() {
  // 2. Provide value
  return (
    <ThemeContext.Provider value="dark">
      <Header />
    </ThemeContext.Provider>
  );
}

function Header() {
  // 3. Consume value
  const theme = React.useContext(ThemeContext);
  return <div className={theme}>Current theme: {theme}</div>;
}
```

  
