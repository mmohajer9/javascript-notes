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

     // adding a method to a class
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

2. Constructor Method inside a class :

   **Constructor method** will be called at the **beginning of the creation of the object of that class**
   **we can use it for setting initial values to the properties or fields and do some stuffs for the first time of creating the object**

   **NOTE** : we call them fields when we are in class context and then , we call them properties when we are in object context

   ```javascript
   class Product {
     title = "DEFAULT_TITLE";
     imageUrl;
     description;
     price;

     someNameMethod() {...}

     // constructor
     constructor(title, imageUrl, desc, price) {
         // this refers to the 'Current Object' that is want to be created
         this.title = title;
         this.imageUrl = imageUrl;
         this.description = desc;
         this.price = price
     }
   }
   ```

   How to use ? See :

   ```javascript
   let prod = new Product(
     "Mobile Phone",
     "http://...",
     "Brand New Mobile Phone",
     2500
   );
   ```

   in the end , we have always normal javascript objects , it is not something different.
