# Advanced Concepts

## Pure Functions & Side-Effects

1. A function is Pure if it has 2 major aspects:

   - If it doesn't have side effects which means doesn't have any effects on anything outside the function

   ```javascript
   let variable = 0;

   function impureFunction() {
     variable = 10; // changing outside variable make it impure
     return 2;
   }
   ```

   - If it produces a same out put every time for a same arguemnts that we pass in

   ```javascript
   function generateRandomNumber(seed) {
       ...
   }
   // this code will generate a random number every time for a certain seed
   ```
