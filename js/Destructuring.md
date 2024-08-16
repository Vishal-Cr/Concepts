
# Array Destructuring

### 1. **Nested Array Destructuring**
Given the following array:
```javascript
const data = [1, [2, 3, [4, 5]], 6];
```
- Destructure the array to extract the values `1`, `2`, `5`, and `6` into variables `a`, `b`, `c`, and `d` respectively.

### 2. **Skipping Elements in Destructuring**
You have the following array:
```javascript
const numbers = [10, 20, 30, 40, 50, 60];
```
- Destructure the array to extract `10`, `30`, and `50` into variables `first`, `third`, and `fifth` while skipping the other values.

### 3. **Destructuring with Default Values**
Consider this array:
```javascript
const colors = ["red", "green"];
```
- Destructure the array to extract the first, second, and third elements into variables `primary`, `secondary`, and `tertiary`, respectively. Set a default value of `"blue"` for `tertiary` if the third element is not present.

### 4. **Swapping Variables**
Given two variables:
```javascript
let x = 5;
let y = 10;
```
- Use array destructuring to swap the values of `x` and `y` without using a temporary variable.

### 5. **Destructuring with Rest Operator**
You have this array:
```javascript
const fruits = ["apple", "banana", "cherry", "date", "elderberry"];
```
- Destructure the array to extract the first two fruits into `fruit1` and `fruit2`, and the rest of the fruits into a new array `otherFruits`.

### 6. **Complex Destructuring with Functions**
You have the following function that returns an array:
```javascript
function getCoordinates() {
  return [12, 34, [56, 78]];
}
```
- Destructure the returned array so that `x`, `y`, `z1`, and `z2` hold the values `12`, `34`, `56`, and `78` respectively.

### 7. **Renaming Variables While Destructuring**
Consider the array:
```javascript
const scores = [100, 200, 300];
```
- Destructure the array to extract the first and second elements, but assign them to variables `highScore` and `mediumScore` instead of using their original positions.

### 8. **Handling Sparse Arrays**
Given the array:
```javascript
const sparseArray = [1, , 3, , 5];
```
- Destructure the array to extract `1`, `3`, and `5` into variables `a`, `b`, and `c`, and assign `undefined` to `missing1` and `missing2` for the empty slots.

### 9. **Destructuring with Mixed Types**
Given an array with mixed types:
```javascript
const mixedArray = [42, "hello", true, [7, 8, 9], { name: "John" }];
```
- Destructure the array to extract the number into `num`, the string into `greeting`, the boolean into `isTrue`, the array into `nestedArray`, and the object into `person`.

### 10. **Dynamic Destructuring Based on Array Length**
Write a function `dynamicDestructure` that accepts an array of any length and returns an object where the first three elements of the array are assigned to keys `first`, `second`, and `third`, and the rest of the elements are assigned to a key `rest` as an array. If the array has less than three elements, the missing keys should have a value of `null`.

### Extra Challenge: **Destructuring Inside Loops**
Given an array of arrays:
```javascript
const points = [
  [1, 2],
  [3, 4],
  [5, 6],
];
```
- Use destructuring inside a `for...of` loop to extract each pair into variables `x` and `y`, and log the coordinates in the format `(x, y)`.

---

These assignments should help you dive deep into the nuances of array destructuring in JavaScript. Let me know if you'd like to explore any of these challenges further!



# Object Destructuring

Here are some challenging assignments on object destructuring:

### 1. **Nested Object Destructuring**
Given the following object:
```javascript
const person = {
  name: "Alice",
  address: {
    city: "Wonderland",
    zip: {
      code: "12345",
      country: "Dreamland"
    }
  },
  friends: [
    { name: "Mad Hatter", age: 30 },
    { name: "Cheshire Cat", age: 25 }
  ]
};
```
- Destructure the object to extract the person's `name`, the `city`, the `zip code`, the `country`, and the `name` of the first friend into separate variables.

### 2. **Default Values in Destructuring**
Consider this object:
```javascript
const options = {
  timeout: 1000,
  isActive: true
};
```
- Destructure the object to extract `timeout`, `isActive`, and a `retryCount` property, setting a default value of `3` for `retryCount` if it doesn't exist in the object.

### 3. **Renaming Variables While Destructuring**
Given the object:
```javascript
const product = {
  id: 101,
  name: "Gadget",
  price: 299.99,
  stock: 50
};
```
- Destructure the object to extract the `name` as `productName`, `price` as `cost`, and `stock` as `quantity` into new variables.

### 4. **Destructuring with Rest Operator**
You have this object:
```javascript
const user = {
  username: "john_doe",
  email: "john@example.com",
  password: "securepassword123",
  age: 28,
  country: "USA"
};
```
- Destructure the object to extract `username` and `email` into separate variables, and gather the remaining properties into a new object called `otherDetails`.

### 5. **Destructuring in Function Parameters**
Write a function `createUserProfile` that takes an object as a parameter with properties `name`, `age`, `email`, and `address` (which itself is an object with `street`, `city`, and `zip`). Destructure these properties in the function's parameters and log each of them.

### 6. **Complex Destructuring with Arrays in Objects**
Given the following object:
```javascript
const data = {
  users: [
    { id: 1, name: "John" },
    { id: 2, name: "Jane" }
  ],
  admin: { id: 0, name: "Admin" }
};
```
- Destructure the object to extract the `id` of the `admin` and the `name` of the second user into variables `adminId` and `secondUserName`.

### 7. **Destructuring with Renaming and Default Values**
You have this object:
```javascript
const settings = {
  theme: "dark",
  notifications: {
    alerts: true,
    sounds: false
  }
};
```
- Destructure the object to extract `theme` (rename it to `currentTheme`), `alerts` (rename it to `allowAlerts`), and a `sounds` property from the `notifications` object with a default value of `true`.

### 8. **Handling Deeply Nested Objects**
Given the deeply nested object:
```javascript
const department = {
  name: "Engineering",
  manager: {
    name: "Elon",
    age: 45,
    reports: {
      direct: {
        count: 5,
        names: ["Alice", "Bob", "Charlie", "David", "Eve"]
      }
    }
  }
};
```
- Destructure the object to extract the `department name`, the `manager's name`, the `number of direct reports`, and the `name of the last direct report` into separate variables.

### 9. **Dynamic Object Destructuring Based on Condition**
Write a function `getProfile` that accepts a user object with optional properties `name`, `age`, `email`, and `address`. Destructure the properties into variables and set default values only if certain properties exist. If `name` exists, `email` should default to `"no-email@example.com"`, otherwise set `email` to `null`.

### 10. **Destructuring with Mixed Arrays and Objects**
Given the following structure:
```javascript
const config = {
  server: "localhost",
  ports: [8080, 8081, 8082],
  database: {
    user: "admin",
    pass: "secret"
  }
};
```
- Destructure the object to extract `server`, the first port into `mainPort`, and the `database` credentials into `dbUser` and `dbPass`.

### Extra Challenge: **Destructuring with Computed Property Names**
You have the following object:
```javascript
const dynamicKey = "lastName";
const profile = {
  firstName: "James",
  [dynamicKey]: "Bond"
};
```
- Destructure the object to extract `firstName` and the property with the key stored in `dynamicKey`.

---

These assignments will push your understanding of object destructuring, helping you master this powerful feature in JavaScript. Let me know if you'd like more details or explanations on any of the tasks!