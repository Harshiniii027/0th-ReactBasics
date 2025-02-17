# React Prop Drilling Example

This project demonstrates **Prop Drilling** in React, where props are passed through several layers of components down to a child component.

## How It Works

- **Main** component receives a message (`msg`) as a prop and passes it down through **Header** and **Wrapper** to the **Button** component.
- The **Button** component uses the prop to display an alert with the message.

### Example Code:

```jsx
function Main(props) {
  return <Header msg={props.msg} />;
}

function Header(props) {
  return (
    <div style={{ border: "10px solid whitesmoke" }}>
      <h1>Header here</h1>
      <Wrapper msg={props.msg} />
    </div>
  );
}

function Wrapper(props) {
  return (
    <div style={{ border: "10px solid lightgray" }}>
      <h2>Wrapper here</h2>
      <Button msg={props.msg} />
    </div>
  );
}

function Button(props) {
  return (
    <div style={{ border: "20px solid orange" }}>
      <h3>This is the Button component</h3>
      <button onClick={() => alert(props.msg)}>Click me!</button>
    </div>
  );
}

function App() {
  return (
    <Main
      msg="I passed through the Header and the Wrapper and I reached the Button component"
    />
  );
}

export default App;
```

### To Run:

1. Clone the repository.
2. Install dependencies using `npm install`.
3. Run the app with `npm start`.

---
