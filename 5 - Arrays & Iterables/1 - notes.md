# Arrays and Iterables Notes

1. There are many ways to create arrays

   ```javascript
   const a = [1, 2, 3]; //regular and best way

   const b = new Array(1, 2, 3); // slower and low performance

   const c = Array(1, 2, 3); // slower and low performance

   const d = Array.of(1, 2, 3); // slower and low performance

   // create an array with the size of input and empty values
   const e = Array(5); // creates array with 5 length , each value is empty

   // another way of creating arrays , very important!
   // best for converting non-array iterables and array-like objects to Arrays
   // like NodeList , HTMLCollection , etc.
   const f = Array.from(iterable_object);

   // e.g. a string !

   const g = Array.from("salam");

   // output of g : ["s", "a", "l", "a", "m"]
   ```

2. at the end the suggestion is to use :
   1. **`const arr = []`** notation to create arrays
   2. **`const converted_arr = Array.from(iterable)`** to convert array-like objects and iterable objects to array and use the array methods , like HTMLCollection , Nodelist , strings , etc.
3. About Spread Operator (...array) :

   ```javascript
   let people = [
     { age: 20, name: "mamad" },
     { age: 12, name: "ali" },
   ];

   // lets make a copy of this array using spread operator

   let copyPeople = [...people];
   // copyPeople now containes the same elements as people
   // but the objects of {age , name} that were in the people object are exactly the same
   // this is not bug !

   copyPeople[0].age = 33;

   console.log(people[0].age, copyPeople[0].age);
   // out put : 33 33

   // why is that ? because the people array is a refrenced values
   // and it contains the refrences to the values and when we copy the array using spread
   // it copies the references
   // to perform a real copy , we should use map() method

   copyPeople = people.map((item, index, items) => {
     return {
       age: item.age,
       name: item.name,
     };
   });
   ```

4. Array Destructuring :

   ```javascript

   ```
