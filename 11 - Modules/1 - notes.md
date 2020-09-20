# Javascript Modules

1. By default in JS , when we import files from **`<script>`** tag before the main file , they will import and available in the global object but when we are using modules , this will change and then every file will be locked down , its content will not be added to this global , it will not globally be available. **The solution is `export` keyword**. this keyword will make the file be available to access for otherfiles.
2. You should add **`type="module"`** attribute to the **`<script>`** tag :

   ```html
   <script src="..." type="module" defer></script>
   ```

3. Syntax:

   ```javascript
   export someObject

   export default anotherObject

   import defaultObject , { moduleName as alias } from "./path/to/moduleNameFile.js";

   import * as bundleModuleAlias from "./path/to/moduleNameFile.js";
   ```

4. Dynamic Import:

   ```javascript
   // use import as a function , it will return a promise

   import("path/to/module.js").then((module) => {
     const obj = new module.moduleNameFile();
     ...
   });
   ```

5. Code in your modules **runs** when the module is imported and loaded **for the first time** and that is very important , so if you import from a module , multiple times , it will run only once !
