# Mote About Strings

1. Different syntax of using string literals **(back single quote)**:

   ```javascript
   function describe(strings, name, lastName) {
     console.log(strings); // the entire string without dynamic $ fields
     console.log(name); // Mamad
     console.log(lastName); // Mohajer
     return {
         strings,
         name,
         lastName
     };
   }

   const name = "Mamad";
   const lastName = "Mohajer;

   const output = describe`Hi My Name is ${name} and my last name is ${lastName}`;

   console.log(output);
   // { ... } acutally with this syntax, we can convert strings to object
   // btw it is just one of the examples that we can show , we can do many things
   ```

2. RegExp:

   ```javascript
   // 2 ways of creating regexp
   const regex1 = new RegExp("..."); // #1

   const regex2 = /^\S+@\S+\.\S+$/; // #2

   // To test a string with given regexp
   regex2.test("..."); // returns true or false

   // to find more information about the matched pattern

   regex2.exec("...");

   // another way to match a pattern to a string

   "a sample string".match(regex2);
   ```
