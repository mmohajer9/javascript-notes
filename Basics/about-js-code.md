# About Javascript Code and Parsing and Executing it

## Parsing and Order of Code Execution

1. You can define functions either in top or in other places of the code , because the js engine at first in the parsing phase , will begin to gather all functions and top and registers them , so **order does not matters for functions in the javascript code** but , **order matters for variables and constants**
2. If you connect multiple javascript sources to your html file , from top of the html to down of it , they will begin to parse and execute sequentially and you can access to functions and variables that are exists in previous files

## Local and Global Scope

1. Take a look at this example :

```javascript
let global_scope_varible;

function add(num1, num2) {
  // this is global scope variable
  // and we can access to this inside the function
  global_scope_varible = num1 + num2;

  // this is local scope variable
  // we can't access to this variable outside the function
  let local_scope_variable = global_scope_variable;

  return local_scope_variable;
}

let output1 = global_scope_variable; // Correct
let output2 = local_scope_variable; // raise an error , not defined
```

It is better **Not to** manipulate global variables from inside of a function

## Number and Strings Convertions

```javascript
let number_int;
let number_float;
let string_int = "123";
let string_float = "12.5";

number_int = parseInt(string_int);
number_float = parseFloat(string_float);

// More Convinient Form : using +
number_int = +string_int;
number_float = +string_float;

// converting number to string
let str1 = number_int.toString()

let str2 = String(number_int)
```
