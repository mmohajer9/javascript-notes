# Numbers

1. First of all , let's say that :
   ![numjs](./Numbers%20in%20JS.png)
2. Some useful codes:

   ```javascript
   // Number is a global Number object

   // getting the maximum integer numebr
   Number.MAX_SAFE_INTEGER; // equal to 2 ^ (53) - 1

   // getting the minimum integer number
   Number.MIN_SAFE_INTEGER; // equal to -(2 ^ 53)

   // getting the maximum value (not only integers)
   Number.MAX_VALUE;

   // two reserved value : +infitinity and -inifinity
   // this is the value of (1 / 0) or (-1 / 0)
   Number.POSTIIVE_INFINITY;
   Number.NEGATIIVE_INFINITY;

   // to check wheter is finite or not
   Number.isFinite(10); // returns true

   Number.isNaN(...); // trivial
   isNaN(...) // same and accesible globally

   ```
