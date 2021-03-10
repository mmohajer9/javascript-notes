# Constructor Functions

1. Introduction Code :

   This is nowdays we work with classes and objects and constructor method

   ```javascript
   class Person {
     name = "Mamad";

     constructor() {
       this.age = 30;
     }

     greet() {
       console.log(this.name, this.age);
     }
   }

   const person = new Person();
   person.greet();
   ```

   but before we had something that is called **Constructor Function**

   ```javascript
   function Person() {
     this.name = "Mamad";
     this.age = 30;
     this.greet = function () {
       console.log(this.name, this.age);
     };
   }
   const person = new Person();
   person.greet();
   ```

   this kind of object which is called constructor function will return an object only and only when you call it with **`new`** key word since as you see , we have no return statement in that function.
   well ofcourse we can have return state ment but when we use **`new`** , javascript automatically return object based on that constructor function.

   **So What Does `new` Keyword Actually Do?**

   **Answer :** It changes the constructor function like this :

   ```javascript
   function Person() {
     this = {}; // initializing an object because of new key word

     this.name = "Mamad";
     this.age = 30;
     this.greet = function () {
       console.log(this.name, this.age);
     };

     // return that created and extended object
     return this;
   }
   const person = new Person();
   person.greet();
   ```
