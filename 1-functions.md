# Functions

some exercises to help you understand functions:
* Defining vs. Calling functions
    * Defining: when you write the funciton -> function name() {}.  This creates the function in memory
    * Calling: using the function to compute new values -> name().  This creates a new frame and returns a new value
* Arguments
* Lexical Scope
* Return Values

### Index
* [completed 

---

## Completed Example

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_2%20%2B%20param_3%20%2B%20param_1%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22x%22,%20arg_2%20%3D%20%22z%22,%20arg_3%20%3D%20%22y%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
function f(param_1, param_2, param_3) {
  var result = param_2 + param_3 + param_1;
  return result;
};

// set values in the args to pass the assert
let arg_1 = "x", arg_2 = "z", arg_3 = "y";
let return_val = f(arg_1, arg_2, arg_3);

console.assert(return_val === "zyx", "return_val === " + return_val);
```

[TOP](#functions)

---

## Exercises

### 1

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  

## Resources

* Lexical Scope: [NWCalvank](https://www.youtube.com/watch?v=GhNA0r10MmA),  [techsith 1](https://www.youtube.com/watch?v=ycTp4vRmLp8), [techsith 2](https://www.youtube.com/watch?v=7tGmS2SPxBo&list=PL7pEw9n3GkoVYU-ZKBrDnxIiiUn0YP-uO&index=2)  
* [HYF](https://github.com/HackYourFutureBelgium/fundamentals/blob/master/fundamentals/functions.md)


[TOP](#functions)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
