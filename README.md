## What does `{}` do in JSX?

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

## What's wrong with this JSX: `<img src="{imageUrl}" alt="descriptive text" />`?

```jsx
const fileName = "puppy"
const imageUrl = `${fileName}.jpg`

const someImage = <img src={imageUrl} alt="descriptive text" />
```

## How you do you include a component in a JSX template?

```jsx
import SomeComponent from "./SomeComponent"

const SomeOtherComponent = () => {
  return (
    <p>
      <SomeComponent />
    </p>
  )
}
```

## What is a prop?

## What is the syntax for giving a component a prop?

## What is the syntax for receiving a prop from a component?

* Short for property
* Property of the component (HTML has attributes)
* To pass values to a component

```jsx
import Modal from "./Modal"
import WarningForm from "./WarningForm"

const SomeOtherComponent = () => {
  return (
    <p>
      <Modal content={WarningForm} />
    </p>
  )
}

//

const Modal = ({ content, name } ) => {
  return (
    <dialog className="pop-up">
      {content}
    </dialog>
  )
}
```


## What is the purpose of destructuring?

Create less variables and less code to write

```jsx
const Modal = ({ content, name } ) => {
  return (
    <dialog className="pop-up">
      {content}
    </dialog>
  )
}

const Modal = (props) => {
  const content = props.content
  const name = props.name

  return (
    <dialog className="pop-up">
      {content}
    </dialog>
  )
}
```

```jsx
const Modal = (props) => {
  const [ isOpen, setIsOpen ] = useState(false)
  //
  const statefulHook = useState(false)
  const isOpen = statefulHook[0]
  const setIsOpen = statefulHook[1]
}
```

## How do you export a module from a file?

```jsx
export default SomeComponent

export const methodOne = function(){}
export const methodTwo = function(){}

import { methodOne, methodTwo } from "./SomeComponent"
import {useState, useEffect} from "react"
import SomeComponent, { methodOne, methodTwo } from "./SomeComponent"
```

## When does an arrow function need to wrap its parameters in parentheses?

* No parameter
* More than one parameter

```js
const someFunction = () => {}
const someOtherFunction = oneParameter => {}
const yetAnotherFunction = (oneParameter, twoParameter) => {}
```

## When can an arrow function wrap its parameters in parentheses?

Anytime!

## What is a ternary expression?

* Three arguments, separated by ? and :
* Different way to write if/else

```js
if (someCondition){
  someStatement()
} else {
  anotherStatement()
}

const result = someCondition
  ? someStatement()
  : anotherStatement()
```

```jsx
const SomeComponent = ({ isSunny, isWarm }) => {
  return (
    <div>
      {
        isSunny
          ? isWarm
            ? <p>The weather is sunny and warm!</p>
            : <p>What gives, it's sunny but not warm!</p>
          : <p>The weather is BAD!</p>
      }
      {
        isSunny
          ? <p>The weather is sunny and warm!</p>
          : <p>The weather is BAD!</p>
      }
    </div>
  )
}
```

## What is spreading?

`...`

Enumerate an array or object

```js
const someArray = [1, 2, 3]
...someArray // 1, 2, 3
[...someArray, someNewValue]
[someNewValue, ...someArray]
{...someObject}

const someObject = {
  a: "1",
  b: "2",
  c: "3",
}

const someObjectWithNewValueForC = {
  ...someObject,
  c: "4", // "Clobbering"
  a: "5",
}

const someCombinedObject = {
  ...objectOne,
  ...objectTwo,
  ...objectThree,
}
const someCombinedObject = "hi" // Error!
```

## What are keys used for in JSX?
## Why can't indexes be used as keys in JSX?

* Specific to arrays
* Provide a unique identifier!

## How do you turn a list of items into a list of JSX elements?

```js
const someNumbers = [1, 2, 3]
const someDoubledNumbers = someNumbers.map(someNumber => {
  return someNumber * 2
}) // [2, 4, 6]
```

```jsx
const DogsList = () => {
  const dogs = [{
    id: 1,
    name: "Bixby",
  },{
    id: 2,
    name: "Harmony",
  },{
    id: 3,
    name: "Mesa",
  }]

  // const $dogs = dogs.map(dog => {
  //  return <li id={`dog-${dog.id}`} key={dog.id}>{dog.name}</li>
  // })

  return (
    <ul>
      {
        dogs.map(dog => (
          <li id={`dog-${dog.id}`} key={dog.id}>{dog.name}</li>
        ))
      }
    </ul>
  )
}
```

```jsx
<ul>
{
  primaryNavLinks.map(({id, url, text}) => (
      <li key={id}>
        <PrimaryNavigationLink
          url={url}
          text={text}
        />
      </li>
  ))
}
</ul>
```
