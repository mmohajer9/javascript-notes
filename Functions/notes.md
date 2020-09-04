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
