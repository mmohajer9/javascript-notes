# Strict Mode in Javascript

1. at the beginning of your code , put `'use strict'`
2. it will force you to avoid some bad patterns in your coding style with javascript
3. these bad patterns are shown in the following sample code :

```javascript
"use strict"; // first you should enable strict mode in your code

userName = "mamad"; // raise an error ,
// because of declaring variables without var , let , const

var lastName = "Mohajer";

var lastName = "Abbasi"; // raise an error ,
//in strict mode , it is forbidden to declare a variable multiple times

var undefined = 5; // raise an error , in  strict mode , it is forbidden to declare a variable with name of keywords and built in data types

// note : if you use let , const (modern javascript)
// it will automatically raise an error without using strict mode
// so use modern javascript
```

note that if you had not enabled the strict mode , then the variables that you declare without `var` or `let` or `const` will be implicitely declared with `var` but , **it is forbidden in strict mode**
