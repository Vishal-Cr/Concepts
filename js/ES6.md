# ES6 Notes
#### innerText vs textContent

### Destructuring 
#### Object Destructuring
- Normal ds
- Nested object destructuring example:
```
// Create a nested object 
const person = {
  name: "Alice",
  address: {
    street: "123 Main St",
    city: "Anytown",
    state: "CA"
  },
  contact: {
    phone: "123-456-7890",
    email: "alice@example.com"
  }
};

// Destructure nested properties
const { name, address: { street, city, state }, contact: { phone, email } } = person;

console.log(name); // Output: Alice
console.log(street); // Output: 123 Main St
console.log(city); // Output: Anytown
console.log(state); // Output: CA
console.log(phone); // Output: 123-456-7890
console.log(email); // Output: alice@example.com
```
##### Destructuring using default values.
- Assign default values to destructured variables in case they are undefined or null.
- Explore different ways to provide default values, such as using the logical OR operator (||) or the nullish coalescing operator (??).
- Test how default values behave in various scenarios.

```
// Object with potentially undefined or null properties
const person = {
  name: "Alice",
  age: undefined,
  address: null
};

// Destructuring with default values using logical OR (||)
const { name, age = 30, address = "Unknown" } = person;

console.log(name); // Output: Alice
console.log(age); // Output: 30 (default value)
console.log(address); // Output: Unknown (default value)

// Destructuring with default values using nullish coalescing operator (??)
const { name: personName = "Default Name", age: personAge = 25, address: personAddress = "N/A" } = person;

console.log(personName); // Output: Alice
console.log(personAge); // Output: 25 (default value)
console.log(personAddress); // Output: N/A (default value)
```

##### Computed Property Names:

- Use computed property names to dynamically create variable names based on expressions.
- Destructure objects with computed property names and access their values.
- Practice using different types of expressions for computed property names.
```
// Object with computed property names
const person = {
  [`name_${Math.floor(Math.random() * 100)}`]: "Alice",
  [`age_${new Date().getFullYear()}`]: 30
};

// Destructure computed property names
const { [`name_${Math.floor(Math.random() * 100)}`]: name, [`age_${new Date().getFullYear()}`]: age } = person;

console.log(name); // Output: Alice (or another random name)
console.log(age); // Output: 30
```


##### Destructuring with Rest Syntax
```
Example:
JavaScript

const person = {
  name: "Alice",
  age: 30,
  city: "New York"
};

const { name, ...rest } = person;

console.log(name); // Output: Alice
console.log(rest); // Output: { age: 30, city: "New York" }

```

Explanation:

    The ...rest syntax collects all the remaining properties of the object into a new object.
    This can be useful when you want to extract specific properties and then use the rest for other purposes.

Use cases:

    Extracting specific properties: When you need to extract certain properties and then work with the remaining properties as a separate object.
    Creating new objects: When you want to create a new object with some properties from an existing object and additional properties.

##### Destructuring with Spread Syntax
```
Example:
JavaScript

const person = {
  name: "Alice",
  age: 30
};

const newPerson = {
  ...person,
  city: "New York"
};

console.log(newPerson); // Output: { name: "Alice", age: 30, city: "New York" }
```


Explanation:

    The ...person syntax spreads the properties of the person object into the new object.
    This allows you to create a new object with the same properties as an existing object, and then add or modify properties as needed.

Use cases:

    Creating new objects: When you want to create a new object based on an existing object with additional or modified properties.
    Combining objects: When you want to combine multiple objects into a single object.

#### Optional Chaining
```
    const person = {
  address: {
    street: "123 Main St"
  }
};
```
const { address: { street } = {} } = person;

console.log(street); // Output: 123 Main St

## How Object destructuring Works
The reason you can't access `address` directly in the code is due to the way **object destructuring** works in JavaScript. Let's break it down:

### Code Overview
```javascript
const person = {
  address: {
    street: "123 Main St"
  }
};

const { address: { street } } = person;

console.log(address); // Error: address is not defined
```

### Object Destructuring Explanation
- The line `const { address: { street } } = person;` uses destructuring to directly extract the `street` property from the `address` object inside `person`.
- After this line, only the `street` variable is created and initialized with the value `"123 Main St"`.
- However, the `address` variable itself is **not** created by this destructuring assignment.

### Why You Can't Access `address`
In your code, `address` is not a defined variable in the current scope because the destructuring only creates the variable `street`. It doesn't create an `address` variable.

If you try to access `address` with `console.log(address);`, JavaScript will throw an error:
```plaintext
ReferenceError: address is not defined
```
This is because `address` was not declared or defined anywhere in the code.

### How to Access `address`
If you want to access `address` directly, you have a few options:

#### Option 1: Destructure `address` Separately
You can destructure the `address` object itself:
```javascript
const { address } = person;
console.log(address); // Outputs: { street: "123 Main St" }
```

#### Option 2: Use `person.address`
You can directly access `address` from the `person` object without destructuring:
```javascript
console.log(person.address); // Outputs: { street: "123 Main St" }
```

### Summary
The error occurs because the destructuring only creates the `street` variable, not the `address` variable. If you need to access `address`, you must either destructure it explicitly or access it directly through the `person` object.

## Shallow Copy and Deep Copy in Object Destructuring

#### shallow COPY(which only un-nested properties are copied as values)
```


const person = {
  name: "Alice",
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};


let {name,address:{street,city}}=person;
name='vishal';
let newPerson={...person}

// console.log(newPerson)

newPerson.name='anthony'   

console.log(person)     //{ name: 'Alice', address: { street: '123 Main St', city: 'Anytown' } }
console.log(newPerson)     
// otuput
//{
//   name: 'anthony',
//   address: { street: '123 Main St', city: 'Anytown' }
// }





// console.log(name)
// console.log(person.name)
```

```
const person = {
  name: "Alice",
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};

let {name,...rest}=person

// console.log(rest);  //{ address: { street: '123 Main St', city: 'Anytown' } }

rest.address.street='new address'
console.log(rest)

console.log(person)

```

## padStart and padEnd :
- The padStart method pads the given string with another string at the start, untill it reaches a given lenght.
```
const str = 'vishal';
let padded = str.padStart(10, '0');
console.log(padded); // Output: "0000vishal"
```
- The padEnd does the same just the opposite.