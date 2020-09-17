# Some Notes Around The Functions

1. If you give default parameter value in any function , it will use default parameter value only when you are giving that parameter **`undefined`** **implicitly** or **explicitly**.
2. **implicit** means you give that value nothing and don't give any argument for that parameter to the function. let's take a look at this example :

   ```javascript
   function add(num1, num2 = 10) {
     return num1 + num2;
   }

   let result = add(5);
   ```

   in this situation , when you don't pass an argument to the function , it will implicitly put **`undefined`** in the given arguemnt , so the function will know to use default parameter value and put **`10`** in num2 and the result is **`15`**

3. **`explicit`** means you put **`undefined`** value directly into the function , take a look at this example:

   ```javascript
   function add(num1 = 10, num2) {
     return num1 + num2;
   }

   let result = add(undefined, 12);
   ```

   in this case , especially when the default parameter value has been set to the first parameter , you should put **`undefined`** to the first argument , you can't do something like this :

   ```javascript
   let result = add(,12) // it is WRONG !
   ```

4. Rest Operator vs Old Fashioned arguemnts variable

   ```javascript
   // rest operator ; also works for function() style
   const sumUp = (a, b, ...numbers) => {
     let sum = 0;
     for (const num of numbers) {
       sum += num;
     }
     return sum;
   };

   // arguments built-in variable for old-fashioned function()
   // only useable in this style
   const subtractUp = function () {
     let sum = 0;
     for (const num of arguments) {
       sum += num;
     }
     return sum;
   };
   ```

5. Callback Function means a function that it is called for you by something else and you just pass a reference or saying pointer to that function to another function to call it for you

6. method `.bind()` is very useful when you are trying to :

   1. setting `this` to a specific method or function
   2. preparing arguments before calling the method or function
   3. note that bind method always return a new function or btw a new or different function object which is not equal with the function it self.

   ```javascript
   const f1 = someFunction;
   const f2 = someFunction.bind(this, ...);

   console.log(f1 === f2); // returns false
   ```
