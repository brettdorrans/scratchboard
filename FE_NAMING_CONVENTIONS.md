# JavaScript Naming Conventions

## General rules

* Avoid single letter variable names. All variables and functions should be descriptive.

```js
// bad
const x = 'hello world';
const a = () => x;

// good
const defaultGreeting = 'hello world';
const getDefaultGreeting = () => defaultGreeting;
```

* Avoid contractions entirely.

```js
// bad
const onClk = () => {};
const btnElement = document.querySelector('button');

// good
const onClick = () => {};
const buttonElement = document.querySelector('button');
```

* Prefer verbosity to conciseness. Variables and methods should fully describe their intended use.

```js
// bad
const id = 1;
const getId = () => id;
const formatDate = (response) => format(response.date);

// good
const caseId = 1;
const getCaseId = () => caseId;
const formatDateFromResponse = (response) => formatDate(date.response);
```

* Use camelCase when naming objects, scoped variables and functions.

```js
// bad
const HelloWorld = {};
const hello_world = {};
const Hello = () => {};

// good
const helloWorld = {};
const hello = () => {};
```

* Use PascalCase for React components or class constructors.

```jsx
// bad
const mycomponent = () => <p>hello world</p>;
const myComponent = () => <p>hello world</p>;
const myInstance = new myInstance();
  
// good
const MyComponent = () => <p>hello world</p>;
const myInstance = new MyInstance();
```

* Use SNAKE_CASE for exported constants.

```js
// bad
const sharedConstant = 'hello world';
const shared_constant = 'hello world';
const SharedContent = 'hello world';
const SHARED_CONSTANT = 'hello world';

// good
export const SHARED_CONSTANT = 'hello world';
```

* Acronyms should be in a consistent case, regardless of other conventions.

```js
// bad
const HttpRequestComponent = () => <p>hello world</p>;
const getHttpRequest = () => {};

// good
const HTTPRequestComponent = () => <p>hello world</p>;
const getHTTPRequest = () => {};
```

* Match case to canonical service name.

```js
// bad
const CreditSafeHeader = () => <p>hello world</p>;
  
// good
const CreditsafeHeader = () => <p>hello world</p>;
```

* Match pluralisation to the quantity of items returned.

```js
// bad
const getApplications = () => { id: 1 };
const getApplication = () => [{ id: 1 }, { id: 2 }];

// good 
const getApplication = () => { id: 1 };
const getApplications = () => [{ id: 1 }, { id: 2 }];
```

* Avoid duplicating context.

```js
// bad
const MenuItem = () => {
  const handleMenuItemClick = () => {};
};

// good
const MenuItem = () => {
  const handleClick = () => {};
};
```

* Reflect the expected result and don't invert logic.

```js
// bad
const isEnabled = items.length > 1;
return <button disabled={!isEnabled} />

// good
const isDisabled = items.length <= 1;
return <button disabled={isDisabled} />
```

* Avoid redundancy.

```js
// bad
const filterItemsArray = (items) => items.filter((item) => item !== null); 

// good
const filterItems = (items) => items.filter((item) => item !== null);
```

* Avoid prefixing private methods or variables with an underscore. Use scopes to determine visibility.

```js
// bad
const _myPrivateVariable = {};
const _myPrivateMethod = () => {};

// good
const myPrivateVariable = {};
const myPrivateMethod = () => {};
```

## Verbs

* When converting data from one format to another, use the `convertTo` verb prefix.

```js
// bad
const celsius = (fahrenheit) => {};

// good
const convertToCelsius = (fahrenheit) => {}; 
```

* When getting computed data, use the `get` verb prefix.

```js
// bad
const computedData = () => {};

// good
const getComputedData = () => {};
```

* When setting in a declarative way, use the `set` verb prefix.

```js
// bad
const numberOfElementsToShow = (numberOfElements) => {};

// good
const setNumberOfElementsToShow = (numberOfElements) => {};
```

* When fetching from an API, use the `fetch` verb prefix.

```js
// bad
const dataFromAPI = () => {};
const getDataFromAPI = () => {};

// good
const fetchDataFromAPI = () => {};
```

* When determining whether something should render, use the `should` verb prefix.

```js
// bad
const canRender = false;
const displayLink = true;

// good
const shouldRender = false;
const shouldDisplayLink = true;
```

* When determining a boolean state, prefer the `is` verb prefix.

```js
// bad
const loading = false;
const [loading, setLoading] = useState(false);

// good
const isLoading = false;
const [isLoading, setIsLoading] = useState(false);
```

* When determining a boolean conditional, prefer the `has` verb prefix.

```js
// bad
const isValidRole = (role) => roles.includes(role);
const validRole = (role) => roles.includes(role);
const [validRole, setValidRole] = useState(null);

// good
const hasValidRole = (role) => roles.includes(role);
const [hasValidRole, setHasValidRole] = useState(null);
```

* When writing a function to handle events or user actions, prefer the `handle` verb prefix.

```js
// bad
const onClick = () => {};
const onError = () => {};

// good
const handleOnClick = () => {};
const handleOnError = () => {};
```

* When resetting data, use the `reset` verb prefix.

```js
// bad
const reinitializeData = () => {};
const setInitialState = () => {};

// good
const resetData = () => {};
const resetState = () => {};
```

* When removing something from a set, use the `remove` verb prefix.

```js
// bad
const deleteFromSet = (data, itemToRemove) => data.filter((item) => item !== itemToRemove);

// good
const removeFromSet = (data, itemToRemove) => data.filter((item) => item !== itemToRemove);
```

* When composing or combining data, use the `compose` verb prefix.

```js
// bad
const getFormattedAddress = (firstLine, secondLine) => {
  return `${firstLine}, ${secondLine}`;
};

// good
const composeFormattedAddress = (firstLine, secondLine) => {
  return `${firstLine}, ${secondLine}`;
};
```

* When setting the initial state, use the `initial` verb prefix.

```js
// bad
const firstState = {};
const [state, setState] = useState(firstState);

// good
const initialState = {};
const [state, setState] = useState(initialState);
```

* When setting defaults, use the `default` verb prefix.

```js
// bad
const initialProperties = { surname: 'Dorrans' };
const properties = { ...initialProperties, firstName: 'Brett' };

// good
const defaultProperties = { surname: 'Dorrans' };
const properties = { ...defaultProperties, firstName: 'Brett' };
```

## References

https://github.com/airbnb/javascript#naming-conventions

https://github.com/kettanaito/naming-cheatsheet
