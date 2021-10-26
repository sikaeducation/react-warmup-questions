* What does `{}` do in JSX?

Insert JS into JSX elements

```jsx
const SomeComponent = () => {
  const someArray = ["a", "b", "c"]
  return (
    <ul>
      {
        someArray.map(someItem => (
          <li>{someItem}</li>
        ))
      }
    </ul>
  )
}
```

* What's wrong with this JSX: `<img src="{imageUrl}" alt="descriptive text" />`?

```jsx
const fileName = "puppy"
const imageUrl = `${fileName}.jpg`

const someImage = <img src={imageUrl} alt="descriptive text" />
```

* How you do you include a component in a JSX template?
* What is a prop?
* What is the syntax for giving a component a prop?
* What is the syntax for receiving a prop from a component?
* What is the purpose of destructuring?
* How do you export a module from a file?
* What is the purpose of destructuring?
* When does an arrow function need to wrap its parameters in parentheses?
* When can an arrow function wrap its parameters in parentheses?
* What is a ternary expression?
* What is spreading?
* What are keys used for in JSX?
* Why can't indexes be used as keys in JSX?
* How do you turn a list of items into a list of JSX elements?
