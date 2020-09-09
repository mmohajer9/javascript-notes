# Object Oriented Programmin in Javascript

## `Class` Keyword

1. Take a look at this sample codes:

   ```javascript
   class Product {
     // you should assign default value to your fields with '=' and end it with ';'
     title = "DEFAULT_TITLE";
     imageUrl;
     description;
     price;

     someNameMethod() {...}
   }
   ```

   It's just a Blueprint for creating our objects.
   How to use it and create objects ?
   See the following codes:

   ```javascript
   // new syntax -> calling the class like function ('Product()')
   // and put 'new' before to tell the javascript to create objects based on this class
   let prod = new Product(); // this gives us a new Product Instance or Object
   ```

   If you try to invoke **`Product()`** without **`new`** keyword , it will raise an error :

   ![error-no-new](./error-no-new-keyword.png)

   Also, the created object is something like this :

   ![product-creation](./product-creation.png)
