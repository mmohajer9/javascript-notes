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

2. **NOTE** : Using impure functions is not bad and it is absolutely fine **but** try to have less impure functions as much as you can. it helps the code to be more predictable

## Factory Functions

1. What are them ? they are functions that can produces another functions

   ```javascript
   function createTaxCalculator(tax) {
     function calculateTax(amount) {
       return amount * tax;
     }

     return calculateTax;
     // notice that we are returning the refrenced value
     // which is the function it self
   }

   const calculator1 = createTaxCalculator(0.19);
   const calculator2 = createTaxCalculator(0.25);

   console.log(calculator1(100));
   console.log(calculator2(200));
   ```

## Closure

1. Every function in javascript is a **Closure** , now what is that being a closure then ?
2. s
