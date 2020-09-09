# Notes on Objects in Javascript

1. There are many ways to create object or modify the object by adding properties or deleting them and etc.
2. To get a good sight on objects , just take a look at this sample code:

   ```javascript
   let userChosenKeyName = "age";

   let person = {
     "first-name": "mamad",
     "last name": "mamal",
     [userChosenKeyName]: 30,
     2.5: "Hey !",
     grade: "diploma",
   };

   // multiple ways of accessing objects properties
   console.log(person.grade); // dot notation
   console.log(person[userChosenKeyName]); // using the values that stored in variable
   console.log(person["first-name"]); // using square brackets
   console.log(person[2.5]); // same as console.log(person['2.5'])

   // adding properties
   person.gender = "male";

   // deleting the property
   delete person.grade;
   ```

3. Objects Property Shorthand Syntax :

   ```javascript
   let title = "1984";
   let author = "George Orwell";

   // we can create a book object with given data like this
   let book = {
     // keyname : value -> value is stored in variable
     title: title,
     author: author,
   };

   // we can simply do this
   let book_shorthand = {
     title,
     author,
   };
   ```

4. You can use Spread Operator (...) with objects too ! but be careful of Shallow Copy and Deep Copy problems when you have referenced values in an object for example :

   ```javascript
   let person = {
     name: "mamad",
     age: 30,
     array: [1, 2, 3], // this is a referenced value
   };

   // array is Shallow copied into person2 not Deep copy
   // but not the other primitive types
   let person2 = { ...person };

   // correct way of Deep Copy
   let person2 = { ...person, array: [...person.array] };
   ```

5. Another way of Copying objects that is available before ES6 and more , is **`Object.assign(target , ...source)`** , e.g. :

   ```javascript
   let person2 = Object.assign({}, person);
   ```

   This method of copy also does a Shallow Copy by default like the spread operator (...)

6. Objects Destructuring

   ```javascript
   let person = {
     age: 30,
     name: "Mamad",
     last_name: "Mohajer",
     array: [1, 2, 3],
   };

   const { age, name, ...otherProps } = person;
   // take care of variable names between curly braces
   // you can only use the names of key names that are existing in that object
   // but this rule will not apply for the variable with rest operator (...)
   // the variable with rest operator (otherProps) will be the object with the remaining keys and values
   ```

   1. The **difference** between Objects Destructuring and Arrays Destructuring is , **in objects destructuring for making variables , you should only use the key name that exists in that object that you wanna to destructure between the curly braces and in the otherwise , it will return undefined for that variables**, but in arrays destructuring you can use any names for your variables between square brackets.
      and also , you can use **any names** for your variables when the variable has **Rest Operator `(...variable_name)`**

   2. and also if you wanna **change the name of the variable between curly braces** you can use this notation :

      ```javascript
      let { name: firstName } = person;
      ```

      note that you should first give the right key name value of that object then you can change variable name with `:` like this :
      **`keyName : desiredVariableName`**

7. How to check the existence of a property in an object ?

   ```javascript
   let person = {
     age: 30,
     name: "Mamad",
     last_name: "Mohajer",
     array: [1, 2, 3],
   };

   // checking with 'in' keyword
   console.log("age" in person); // returns true

   // checking with equality to undefined
   console.log(person.age !== undefined);
   ```

8. About **`this`** Keyword Behaviour In Objects for Normal Functions (not arrow functions):

   1. **`this`** does not automatically refer to the object that kind of surrounds it
   2. **`this`** refers to who or what was responsible for calling this function , **it is very very important !** , note that this tip was for normal functions like **`function(){...}`** **not arrow functions** like **`(...) => {...}`**
   3. consider the following code :

      ```javascript
      let btn = document.querySelector("#submit-btn"); // get the submit button element

      const someFunc = function () {
        console.log(this); // this will output the button element
      };

      btn.addEventListener("click", someFunc);
      ```

      In this case the **`this`** object will refer to the object that is responsible for triggering that **`someFunc`** function and it will return the button object element.

   4. **`this`** that refers to global **`window`** object , will be **`undefined`** **if we use strict mode** , i mean : **`use strict`**
   5. In summary : normal functions will change the binding of **`this`**

9. About **`this`** Keyword Behaviour In Objects for Arrow Functions **`((...) => {...})`**:

   1. Arrow functions **don't bind `this` to anything !**
   2. **`this`** is not overwritten by the function , instead it refers to exact same thing that it would refer to outside of the function.
   3. strict mode **does not** any changes on **`this`** behaviour in arrow functions
   4. **`.bind()`** method in functions does not affect arrow functions
   5. Arrow Functions don't bind **`this`** to anything , instead they keep the context , it means the this will be bind to what ever it is outside of the function.
   6. Arrow functions don't change the binding of **`this`**

10. Getters and Setters :

    ```javascript
    let person = {
      firstName: "Mamad",
      lastName: "Mohajer",
      age: 30,
      // new syntax
      set jobTitle(value) {
        if (value.trim()) {
          // make a new property here
          // we can access to this property from getters and setters
          // not directly and its internal
          this._jobTitle = value;
        } else {
          this._jobTitle = "DEFAULT";
          return;
        }
      },
      get jobTitle() {
        return this._jobTitle;
      },
    };
    ```

    How can we work and access to this getters and setters ?

    ```javascript
    // getting the property
    console.log(person.jobTitle);

    // setting the property
    person.jobTitle = "Computer Scientist";
    ```

    it is very useful when you want to change the behaviour of accessing the properties or the behaviour of setting the properties
