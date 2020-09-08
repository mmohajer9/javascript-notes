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
