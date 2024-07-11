# First AMA session QnA

1.  **(==) vs. (===):**

- These are both comparison operators in JavaScript.
- `==` performs a loose equality check. It converts values to the same type before comparing them. This can lead to unexpected results. (e.g., "10" == 10 is true)
- `===` performs a strict equality check. It compares both the value and the data type. Use this for reliable comparisons. (e.g., "10" === 10 is false)

2. **Console.log(typeof [])**

- This outputs `"object"` because in JavaScript, arrays are technically a special type of object. While they behave differently from regular objects, they share some underlying characteristics.

3. **Disadvantages of Closures:**

- Closures can create memory leaks if not handled properly. Since a closure holds a reference to its outer function's variables, those variables stay in memory even if the outer function is no longer needed.
- Excessive use of closures can make code harder to understand due to hidden dependencies.

4. **Global Variables in JavaScript:**

- Global variables are accessible from anywhere in your code. This can lead to naming conflicts and make your code harder to maintain.
- They make it difficult to track how variables are being used and can lead to unintended side effects.

5. **Extracting Properties from Array of Objects:**

- There are two ways:

- **Object Destructuring:**

       ```javascript
       const users = [
         { name: "Alice", age: 30 },
         { name: "Bob", age: 25 },
       ];
       const names = users.map((user) => user.name); // Creates array of names
       ```

- **Looping and Pushing:**

       ```javascript
       const users = [
         { name: "Alice", age: 30 },
         { name: "Bob", age: 25 },
       ];
       const names = [];
       for (const user of users) {
         names.push(user.name);
       }
       ```

6. **charAt() vs. at()**

- `charAt(index)`: Returns the character at a specific index in a string. If the index is out of bounds, it returns an empty string.
- `at(index)` (introduced in ES2020): Similar to `charAt` but allows negative indexing and throws an error if the index is out of bounds. It's generally preferred for its clarity and error handling.

7. **Resetting Initial Commit in Git:**

- No, you cannot directly reset the initial commit in Git. However, you have a few options depending on your situation:
- **Force Delete and Re-Push:** This is risky and should be used with caution. It rewrites history and can cause problems.
- **Create a New Branch and Commit:** Make the necessary changes in a new branch and push that instead.

8. **Arrays and Dot Notation:**

   - Arrays are technically objects in JavaScript, but a special kind. They use square brackets `[]` for accessing elements by index, not dot notation like regular objects with key-value pairs.

9. **forEach vs. for loop with undefined:**

   - `forEach` skips `undefined` elements because it only iterates over elements that have a value assigned.
   - A `for` loop iterates over all indices, regardless of value. So, for an undefined index, it'll give `undefined`.

10. **Mimicking Array Methods on Objects:**

   You can't directly use `splice` or `slice` on objects, but you can achieve similar results:

   - **For selective copying:** Use `Object.assign` to create a new object with desired properties.
   - **For removing properties:** Loop through the object and delete unwanted properties.

11. **Callback Hell:**

   - This refers to nested `function` calls within functions, making code hard to read and maintain.
   - Avoid it by using:
     - Promises for asynchronous operations.
     - Async/await syntax for cleaner async code.

12. **Unexpected Output in Module System:**

   - In your example, `console.log("Hello");` is outside the `module.exports` block. It runs first, printing "Hello" before the module exports. 
   - To fix this, move the console log inside the `module.exports` block.