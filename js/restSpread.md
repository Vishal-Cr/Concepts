# Rest and Spread Operators

### 1. **Merging Arrays with Spread Operator**
Given the following arrays:
```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const array3 = [7, 8, 9];
```
- Merge these arrays into a single array using the spread operator, then insert the value `10` at the beginning and `0` at the end of the resulting array.

### 2. **Copying and Modifying Arrays**
Consider this array: 
```javascript
const fruits = ["apple", "banana", "cherry"];
```
- Use the spread operator to create a copy of the `fruits` array. Then add `"mango"` at the beginning and `"orange"` at the end of the copied array without modifying the original array.

### 3. **Merging Objects with Spread Operator**
Given these objects:
```javascript
const user1 = { name: "Alice", age: 25 };
const user2 = { age: 30, city: "Wonderland" };
```
- Merge `user1` and `user2` into a new object using the spread operator. Ensure that `user2` properties override those in `user1` where they overlap.

### 4. **Rest Operator in Function Parameters**
Write a function `sum` that accepts any number of arguments and returns their sum. Use the rest operator to handle the varying number of arguments.

### 5. **Rest Operator with Destructuring**
Given the following array:
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
```
- Destructure the array to extract the first two elements into variables `a` and `b`, and the remaining elements into a new array `restNumbers` using the rest operator.

### 6. **Cloning and Modifying Objects**
You have this object:
```javascript
const originalUser = { name: "John", age: 40, city: "New York" };
```
- Create a clone of the `originalUser` object using the spread operator, but change the `name` to `"Jane"` and add a new property `country` with the value `"USA"`.

### 7. **Rest Parameter and Spread Operator Combined**
Write a function `concatArrays` that takes an initial array and any number of additional arrays as arguments, then returns a single array with all the arrays concatenated together. Use the rest parameter to capture additional arrays and the spread operator to concatenate them.

### 8. **Removing Specific Elements from an Array**
Given the following array:
```javascript
const people = ["Alice", "Bob", "Charlie", "David"];
```
- Write a function `removePerson` that accepts the `people` array and a name (e.g., `"Charlie"`) and returns a new array with that name removed. Use the spread operator to achieve this.

### 9. **Merging Deeply Nested Objects**
Given these nested objects:
```javascript
const settings1 = {
  appearance: { theme: "dark", fontSize: 14 },
  preferences: { notifications: true }
};

const settings2 = {
  appearance: { fontSize: 16 },
  preferences: { autoSave: true }
};
```
- Merge `settings1` and `settings2` into a new object using the spread operator, ensuring that nested properties like `fontSize` in `settings2` override those in `settings1`.

### 10. **Rest Operator with Object Destructuring**
Consider the following object:
```javascript
const config = {
  hostname: "localhost",
  port: 8080,
  protocol: "http",
  timeout: 3000
};
```
- Destructure the object to extract `hostname` and `port` into variables, and gather the remaining properties into a new object `otherConfig` using the rest operator.

### Extra Challenge: **Flattening Nested Arrays**
Given this nested array:
```javascript
const nestedArray = [1, [2, 3], [4, [5, 6]], 7];
```
- Write a function `flattenArray` that uses recursion and the spread operator to flatten this array into `[1, 2, 3, 4, 5, 6, 7]`.

---

These assignments will test your understanding of the rest and spread operators, helping you to see how versatile and powerful they are in handling arrays, objects, and function parameters. If you want further explanation or examples for any of these tasks, just let me know!