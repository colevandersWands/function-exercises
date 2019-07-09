# Tracing Functions

some exercises to help you understand functions:
* Defining vs. Calling functions
    * Defining: when you write the funciton -> function name() {}.  This creates the function in memory
    * Calling: using the function to compute new values -> name().  This creates a new frame and returns a new value
* Arguments
* Lexical Scope
* Return Values

And to help you learn how to trace values as they are passed through functions!  This skill is absolutely fundamental to understanding programming. It can be helpful to trace values _backwards_ from the assertion to the variables.  Like so:
1. stored in a global variable
1. passed as argument to a function call
1. available as a parameter in the new frame
1. returned as part of a return value
1. captured in a new global variable  

Or you may find it helpful to work backwards:
1. Pick an index in the expected value string (in the assert).
1. Find that same position in the concatinated return value (inside the function body).
1. Find in which position that variable is declared as a paramter (inside the parenthesis of the function declaration)
1. Find which argument is located in that position of the function call.
1. Find the value assigned to that variable
If the first value and the final values match, they're good to go!

> Don't forget to use [python tutor](http://www.pythontutor.com/live.html#mode=edit) and [the parsonizer](https://janke-learning.org/parsonizer)!

[TOP](#tracing-functions)

---

### Index
* [completed example](#completed-example)
* exercises
    * [number 1](#1)
    * [number 2](#2)
    * [number 3](#3)
    * [number 4](#4)
    * [number 5](#5)
    * [number 6](#6)
    * [number 7](#7)
    * [number 8](#8)
    * [number 9](#9)
    * [number 10](#10)
    * [number 11](#11)
    * [number 12](#12)
    * [number 13](#13)
* [resources](#resources)

---

## Completed Example

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_2%20%2B%20param_3%20%2B%20param_1%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22x%22,%20arg_2%20%3D%20%22z%22,%20arg_3%20%3D%20%22y%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_2%20%2B%20param_3%20%2B%20param_1%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22x%22,%20arg_2%20%3D%20%22z%22,%20arg_3%20%3D%20%22y%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{  // completed example
  function f(param_1, param_2, param_3) {
    var result = param_2 + param_3 + param_1;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "x", arg_2 = "z", arg_3 = "y";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "zyx", "example: return_val === " + return_val);
}
```

[TOP](#tracing-functions)

---

## Exercises

[TOP](#tracing-functions)

---

### 1

```js
{ console.log(1);

  function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "zyx", "1 a");

  arg_1 = "", arg_2 = "", arg_3 = "";
  return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "yzx", "1 b");
}
```

[TOP](#tracing-functions)

---

### 2

```js
{ console.log(2);

  function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_3, arg_2);
  console.assert(return_val === "yxz", "2 a");

  arg_1 = "", arg_2 = "", arg_3 = "";
  return_val = f(arg_2, arg_1, arg_3);
  console.log(return_val === "zxy", "2 b");
}
```

[TOP](#tracing-functions)

---

### 3

```js
{ console.log(3);

  function f(param_1, param_2, param_3) {
    var _ = param_2;
    param_2 = param_1;
    param_1 = _;
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "yxz", "3 a");
  
  
  arg_1 = "", arg_2 = "", arg_3 = "";
  return_val = f(arg_3, arg_2, arg_1);
  console.assert(return_val === "zyx", "3 b");
}
```

[TOP](#tracing-functions)

---

### 4

```js
{ console.log(4);

  function f(param_1, param_2, param_3) {
    var _ = param_2;
    param_2 = param_3;
    param_3 = _;
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "xyz", "4 a");
  
  arg_1 = "", arg_2 = "", arg_3 = "";
  return_val = f(arg_2, arg_3, arg_1);
  console.assert(return_val === "zyx", "4 b");
}
```

[TOP](#tracing-functions)

---

### 5
  
```js
{ console.log(5);

  function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
  };

  let x = "x", y = "y", z = "z";
  // pass x, y and z to the function in the right order
  let return_val = f();
  console.assert(return_val === "yxz", "5 a");

  x = "x", y = "z", z = "y";
  return_val = f();
  console.assert(return_val === "zyx", "5 b");
}
```

[TOP](#tracing-functions)

---

### 6


```js
{ console.log(6);

  function f(param_1, param_2, param_3) {
    var result = param_2 + param_1 + param_3;
    return result;
  };

  // pass x, y and z to the function in the right order
  let x = "x", y = "y", z = "z";
  let return_val = f();
  console.assert(return_val === "xzy", "6 a");
            
  x = "y", y = "x", z = "z";
  return_val = f();
  console.assert(return_val === "zyx", "6 b");
}
```

[TOP](#tracing-functions)

---

### 7

 
```js    
{ console.log(7);

  // concatinate the params to pass the tests
  function f(param_1, param_2, param_3) {
    var result;
    return result;
  };

  let arg_1 = "z", arg_2 = "y", arg_3 = "x";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "xzy", "7 a");

  arg_1 = "z", arg_2 = "x", arg_3 = "y";
  return_val = f(arg_3, arg_2, arg_1);
  console.assert(return_val === "zyx", "7 b");
}
```

[TOP](#tracing-functions)

---

### 8

```js
{ console.log(8);

  // concatinate the params to pass the tests
  function f(param_1, param_2, param_3) {
    var result;
    return result;
  };

  let arg_1 = "z", arg_2 = "y", arg_3 = "x";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "yxz", "8 a");

  arg_1 = "x", arg_2 = "z", arg_3 = "y";
  return_val = f(arg_3, arg_1, arg_2);
  console.assert(return_val === "xzy", "8 b");
}  
```

[TOP](#tracing-functions)

---

### 9

```js
{ console.log(9);

  // arrange the parameters to pass the asserts
  function f() {
    var result = param_2 + param_1 + param_3;
    return result;
  };

  let arg_1 = "z", arg_2 = "y", arg_3 = "x";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "yxz", "9 a");

  arg_1 = "x", arg_2 = "z", arg_3 = "y";
  return_val = f(arg_3, arg_1, arg_2);
  console.assert(return_val === "xzy", "9 b");
}  
```

[TOP](#tracing-functions)

---

### 10

```js
{ console.log(10);

  // arrange the parameters to pass the asserts
  function f() {
    var result = param_1 + param_2 + param_3;
    return result;
  };

  let arg_1 = "y", arg_2 = "z", arg_3 = "x";
  let return_val = f(arg_1, arg_2, arg_3);
  console.assert(return_val === "xyz", "10 a");

  arg_1 = "z", arg_2 = "x", arg_3 = "y";
  return_val = f(arg_3, arg_1, arg_2);
  console.assert(return_val === "xyz", "10 b");
} 
```

[TOP](#tracing-functions)

---

### 11

```js
{ console.log(11); // do what needs to be done

  function f(param_1, param_2, param_3, param_4) {
    var result = param_4 + param_2 + param_3 + param_1;
    return result;
  };

  let arg_1 = "", arg_2 = "", arg_3 = "", arg_4 = ""; // <--
  let return_val = f(arg_1, arg_2, arg_3, arg_4);
  console.assert(return_val === "xyzw", "11 a");

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f(arg_3, arg_1, arg_4, arg_2);
  console.assert(return_val === "", "11 b");          // <--

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f();                                   // <--
  console.assert(return_val === "zywx", "11 c");
} 
```

[TOP](#tracing-functions)

---

### 12

```js
{ console.log(12); // do what needs to be done

  function f(param_2, param_3, param_4, param_1) {
    var result;  // <--
    return result;
  };

  let arg_1 = "", arg_2 = "", arg_3 = "", arg_4 = ""; // <--
  let return_val = f(arg_1, arg_2, arg_3, arg_4);
  console.assert(return_val === "xyzw", "12 a");

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f(arg_3, arg_1, arg_4, arg_2);
  console.assert(return_val === "", "12 b");          // <--

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f();                                   // <--
  console.assert(return_val === "zywx", "12 c");
} 
```

[TOP](#tracing-functions)

---

### 13

```js
{ console.log(13); // do what needs to be done

  function f() {  // <--
    var result = param_3 + param_1 + param_2 + param_4;
    return result;
  };

  let arg_1 = "", arg_2 = "", arg_3 = "", arg_4 = ""; // <--
  let return_val = f(arg_1, arg_2, arg_3, arg_4);
  console.assert(return_val === "xyzw", "13 a");

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f(arg_3, arg_1, arg_4, arg_2);
  console.assert(return_val === "", "13 b");          // <--

  arg_1 = "z", arg_2 = "w", arg_3 = "y", arg_4 = "x";
  return_val = f();                                   // <--
  console.assert(return_val === "zywx", "13 c");
} 
```

---

## Resources

* [pythontutor video](https://www.youtube.com/watch?v=bJUmxDsaduY&list=PLzV58Zm8FuBJFfQN5il3ujx6FDAY8Ds3u&index=6)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
