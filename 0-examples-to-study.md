# Functions by Example

Some completed examples to study. 

### Index
* [declare, call, reference](#declare-call-reference)
* [only one return value](#only-one-return-value)
* [call a function many times](#call-a-function-many-times)
* [args by variable or value](#args-by-variable-or-value)
* [nothing happens after return](#nothing-happens-after-return)
* [same args, same return value](#same-args-same-return-value)
* [named & anonymous functions](#named-and-anonymous-functions)
* [reference-type args](#reference-type-args)
* [reference-type return values](#reference-type-return-values)
* [functions as arguments](#functions-as-arguments)
* [declaring & calling in functions](#declaring-and-calling-in-functions)

---

## Declare, Call, Reference

can be declared, called, and referenced  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20declaring%20a%20function.%20%0A%20%20creates%20the%20function%20in%20memory%0A%20%20does%20not%20take%20a%20step%20of%20execution,%20happens%20at%20creation%20phase%0A*/%0Afunction%20demo%28param%29%20%7B%0A%20%20return%20param%3B%0A%7D%0A%0A/*%20calling%20a%20function.%20%0A%20%20does%20take%20steps%20at%20execution%20phase%0A%20%20can%20be%20done%20as%20many%20times%20as%20you%20like%0A%20%20opens%20a%20new%20'frame'%20in%20memory%0A%20%20evaluates%20to%20the%20function's%20return%20value,%20assign%20this%20value%20to%20a%20variable%0A*/%0Aconst%20first_call%20%3D%20demo%283%29%3B%0Aconst%20second_call%20%3D%20demo%282%29%3B%0Aconst%20third_call%20%3D%20demo%281%29%3B%0A%0A/*%20referencing%20a%20function%0A%20%20functions%20are%20reference%20types%0A%20%20you%20can%20assign%20and%20reassign%20to%20them%20just%20like%20%7B%7D%20and%20%5B%5D%0A%20%20declaring%20a%20function%20creates%20a%20variable%20that%20can%20be%20reused%0A*/%0Alet%20arr%20%3D%20%5B%5D%3B%0Alet%20_%20%3D%20null%3B%0A_%20%3D%20arr%3B%0Aarr%20%3D%20demo%3B%0Ademo%20%3D%20_%3B%0A_%20%3D%20null%3B&cumulative=false&curInstr=15&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  /* declaring a function. 
    creates the function in memory
    does not take a step of execution, happens at creation phase
  */
  function demo(param) {
    return param;
  }

  /* calling a function. 
    does take steps at execution phase
    can be done as many times as you like
    opens a new 'frame' in memory
    evaluates to the function's return value, assign this value to a variable
  */
  const first_call = demo(3);
  const second_call = demo(2);
  const third_call = demo(1);

  /* referencing a function
    functions are reference types
    you can assign and reassign to them just like {} and []
    declaring a function creates a variable that can be reused
  */
  let arr = [];
  let _ = null;
  _ = arr;
  arr = demo;
  demo = _;
  _ = null;
}
```

[TOP](#functions-by-example)

---

## Only One Return Value

functions can only return one thing, after it does that the frame will close.  
[on pytut](http://www.pythontutor.com/live.html#code=//%20you%20can%20only%20return%20one%20value%0Afunction%20one_ret_val%28param_1,%20param_2%29%20%7B%0A%20%20return%20param_1%3B%0A%20%20return%20param_2%3B%0A%7D%0A%0Aconst%20only_one%20%3D%20one_ret_val%282,%206%29%3B&cumulative=false&curInstr=3&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  // you can only return one value
  function one_ret_val(param_1, param_2) {
    return param_1;
    return param_2;
  }

  const only_one = one_ret_val(2, 6);
}
```

[TOP](#functions-by-example)

---

## Call a Function Many Times

[on pytut](http://www.pythontutor.com/live.html#code=//%20you%20can%20call%20the%20same%20function%20many%20times%0A//%20different%20arguments%20make%20different%20return%20values%0Afunction%20add_1%28param%29%20%7B%0A%20%20return%20param%20%2B%201%3B%0A%7D%0A%0Aconst%20four%20%3D%20add_1%283%29%3B%0Aconst%20six%20%3D%20add_1%285%29%3B%0Aconst%20twenty%20%3D%20add_1%2819%29%3B&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  // you can call the same function many times
  // different arguments make different return values
  function add_1(param) {
    return param + 1;
  }

  const four = add_1(3);
  const six = add_1(5);
  const twenty = add_1(19);
}
```

[TOP](#functions-by-example)

---

## Args by Variable or Value

arguments can be passed by value or by variable    
[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1%29%20%7B%0A%20%20return%20param_1%3B%0A%7D%3B%0A%0A//%20variables%20can%20be%20passed%20by%20value%0Alet%20return_val_1%20%3D%20f%28%22x%22%29%3B%0A%0A//%20or%20by%20variable%0Alet%20arg%20%3D%20%22z%22%3B%0Alet%20return_val_2%20%3D%20f%28arg%29%3B&cumulative=false&curInstr=7&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function f(param_1) {
    return param_1;
  };

  // variables can be passed by value
  let return_val_1 = f("x");

  // or by variable
  let arg = "z";
  let return_val_2 = f(arg);
}
```

[TOP](#functions-by-example)

---

## Nothing Happens after _return_


nothing happens after the return statement, the frame closes and the function is over.  
[on pytut](http://www.pythontutor.com/javascript.html#code=//%20nothing%20happens%20after%20the%20return%20statement%0Afunction%20demo%28param%29%20%7B%0A%20%20return%20param%3B%0A%20%20param%20%2B%3D%203%3B%20%20%20%20%20%20%20%20%20%20%20%0A%7D%0A%0Aconst%20return_val_1%20%3D%20demo%283%29%3B%0Aconst%20return_val_2%20%3D%20demo%284%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  // nothing happens after the return statement
  function demo(param) {
    return param;
    param += 3;           
  }

  const return_val = demo(3);
  const return_val = demo(4);
}
```

[TOP](#functions-by-example)

---

## Same args, Same Return Value

Well-written functions will always return the same value for the same argument.  
[on pytut](http://www.pythontutor.com/live.html#code=//%20the%20same%20arguments%20will%20make%20the%20same%20return%20value%0Afunction%20truthify%28param%29%20%7B%0A%20%20return%20Boolean%28param%29%3B%0A%7D%0A%0Aconst%20wiggle%20%3D%20truthify%283%29%3B%0Aconst%20earplug%20%3D%20truthify%283%29%3B%0Aconst%20raul%20%3D%20truthify%280%29%3B%0Aconst%20luar%20%3D%20truthify%280%29%3B%0Aconst%20stamping%20%3D%20truthify%283%29%3B&cumulative=false&curInstr=15&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  // the same arguments will make the same return value
  function truthify(param) {
    return Boolean(param);
  }

  const wiggle = truthify(3);
  const earplug = truthify(3);
  const raul = truthify(0);
  const luar = truthify(0);
  const stamping = truthify(3);
}
```

[TOP](#functions-by-example)

---

## Named and Anonymous Functions


functions can be named or anonymous  
[on pytut](http://www.pythontutor.com/live.html#code=//%20declaring%20the%20functions%0A//%20named%20functions%20automatically%20create%20variables%0Afunction%20named%28param%29%20%7B%0A%20%20return%20param%3B%0A%7D%0A//%20anonymous%20functions%20do%20not%20create%20variables%20automatically%0Alet%20anonymous%20%3D%20function%20%28param%29%20%7B%0A%20return%20param%3B%20%0A%7D%0A%0A//%20calling%20the%20functions%0Aconst%20zeroth_call%20%3D%20named%283%29%3B%0Aconst%20first_call%20%3D%20named%282%29%3B%0Aconst%20second_call%20%3D%20anonymous%281%29%3B%0Aconst%20third_call%20%3D%20anonymous%280%29%3B%0A%0A//%20referencing%20the%20functions%0A//%20variables%20created%20by%20named%20functions%20can%20be%20reassigned%0Alet%20_%20%3D%20null%3B%0A%0A_%20%3D%20named%3B%0Anamed%20%3D%20anonymous%3B%0Aanonymous%20%3D%20_%3B%0A_%20%3D%20null%3B%0A%0A//%20calling%20the%20swapped%20functions%0A//%20it's%20the%20reference%20in%20memory,%20not%20the%20name,%20that%20counts%0Aconst%20call_i%20%3D%20named%28%22i%22%29%3B%0Aconst%20call_j%20%3D%20named%28%22j%22%29%3B%0Aconst%20call_k%20%3D%20anonymous%28%22k%22%29%3B%0Aconst%20call_l%20%3D%20anonymous%28%22l%22%29%3B&cumulative=false&curInstr=30&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

[more on named & anonymous functions](https://janke-learning.org/recursive-calls/)
```js
{
  // declaring the functions
  // named functions automatically create variables
  function named(param) {
    return param;
  }
  // anonymous functions do not create variables automatically
  let anonymous = function (param) {
   return param; 
  }

  // calling the functions
  const zeroth_call = named(3);
  const first_call = named(2);
  const second_call = anonymous(1);
  const third_call = anonymous(0);

  // referencing the functions
  // variables created by named functions can be reassigned
  let _ = null;

  _ = named;
  named = anonymous;
  anonymous = _;
  _ = null;

  // calling the swapped functions
  // it's the reference in memory, not the name, that counts
  const call_i = named("i");
  const call_j = named("j");
  const call_k = anonymous("k");
  const call_l = anonymous("l");
}
```


[TOP](#functions-by-example)

---

## Reference Type Args

functions can take reference types as arguments, but they will modify the global data structure  
[on pytut](http://www.pythontutor.com/live.html#code=//%20not%20copying%20reference%20type%20args%20in%20a%20function%20leads%20to%20%22side%20effects%22%0A//%20%20%28when%20something%20in%20a%20parent%20frame%20is%20modified%20by%20a%20function%20call%29%0Aconst%20arr_1%20%3D%20%5B3%5D%3B%0Afunction%20add_to_zero_side_effect%28arr%29%20%7B%0A%20%20arr%5B0%5D%20%3D%20arr%5B0%5D%20%2B%204%3B%0A%20%20return%20arr%3B%0A%7D%0Aconst%20arr_2%20%3D%20add_to_zero_side_effect%28arr_1%29%3B%0A%0A//%20pure%20functions%20do%20not%20change%20anything%20in%20the%20global%20scope%0A//%20%20this%20happens%20by%20default%20with%20primitive%20values%0A//%20%20with%20reference%20types%20you%20need%20to%20copy%20the%20argument%0Aconst%20arr_x%20%3D%20%5B3%5D%3B%0Afunction%20add_to_zero_pure%28arr%29%20%7B%0A%20%20var%20arr_copy%20%3D%20JSON.parse%28JSON.stringify%28arr%29%29%3B%0A%20%20arr_copy%5B0%5D%20%3D%20arr%5B0%5D%20%2B%204%3B%0A%20%20return%20arr%3B%0A%7D%20%0Aconst%20arr_y%20%3D%20add_to_zero_pure%28arr_x%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  // not copying reference type args in a function leads to "side effects"
  //  (when something in a parent frame is modified by a function call)
  const arr_1 = [3];
  function add_to_zero_side_effect(arr) {
    arr[0] = arr[0] + 4;
    return arr;
  }
  const arr_2 = add_to_zero_side_effect(arr_1);

  // pure functions do not change anything in the global scope
  //  this happens by default with primitive values
  //  with reference types you need to copy the argument
  const arr_x = [3];
  function add_to_zero_pure(arr) {
    var arr_copy = JSON.parse(JSON.stringify(arr));
    arr_copy[0] = arr[0] + 4;
    return arr;
  } 
  const arr_y = add_to_zero_pure(arr_x);
}
```


[TOP](#functions-by-example)

---

## Reference Types Return Value



returning reference types does not produce side effects and can be useful to return more than one primitive values   
[on pytut](http://www.pythontutor.com/live.html#code=function%20add_to_both%28param_1,%20param_2%29%20%7B%0A%20%20var%20result%20%3D%20%5B%5D%3B%0A%20%20result.push%28param_1%20%2B%201%29%3B%0A%20%20result.push%28param_2%20%2B%201%29%3B%0A%20%20return%20result%3B%0A%7D%0A%0Aconst%20six_seven%20%3D%20add_to_both%285,%206%29%3B%0Aconst%20four_two%20%3D%20add_to_both%283,%201%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function add_to_both(param_1, param_2) {
    var result = [];
    result.push(param_1 + 1);
    result.push(param_2 + 1);
    return result;
  }

  const six_seven = add_to_both(5, 6);
  const four_two = add_to_both(3, 1);
}
```


[TOP](#functions-by-example)

---

## Functions as Arguments

functions can be passed as arguments to other functions
this works just like arrays and objects    
[on pytut](http://www.pythontutor.com/live.html#code=function%20do_math%28math_to_do,%20arg_1,%20arg_2%29%20%7B%0A%20%20var%20result%20%3D%20math_to_do%28arg_1,%20arg_2%29%3B%0A%20%20return%20result%3B%0A%7D%0A%0Afunction%20sum_squares%28param_1,%20param_2%29%20%7B%0A%20%20var%20square_1%20%3D%20param_1%20*%20param_1%3B%0A%20%20var%20square_2%20%3D%20param_2%20*%20param_2%3B%0A%20%20var%20sum_of_squares%20%3D%20square_1%20%2B%20square_2%3B%0A%20%20return%20sum_of_squares%3B%0A%7D%0A%0Aconst%20final_answer%20%3D%20do_math%28sum_squares,%204,%203%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function do_math(math_to_do, arg_1, arg_2) {
    var result = math_to_do(arg_1, arg_2);
    return result;
  }

  function sum_squares(param_1, param_2) {
    var square_1 = param_1 * param_1;
    var square_2 = param_2 * param_2;
    var sum_of_squares = square_1 + square_2;
    return sum_of_squares;
  }

  const final_answer = do_math(sum_squares, 4, 3);
}
```


[TOP](#functions-by-example)

---

## Declaring and Calling in Functions


functions can be declared and called from within other functions.  this leads to a stack of frames -> the callstack  
[on pytut](http://www.pythontutor.com/live.html#code=const%20global_var%20%3D%20%22global%22%3B%0Aconsole.log%28global_var,%20bottom_var,%20middle_var,%20top_var%29%3B%0Afunction%20bottom%28%29%20%7B%0A%20%20var%20bottom_var%20%3D%20%22bottom%22%3B%0A%20%20console.log%28global_var,%20bottom_var,%20middle_var,%20top_var%29%3B%0A%20%20function%20middle%28%29%20%7B%0A%20%20%20%20var%20middle_var%20%3D%20%22middle%22%3B%0A%20%20%20%20console.log%28global_var,%20bottom_var,%20middle_var,%20top_var%29%3B%0A%20%20%20%20function%20top%28%29%20%7B%0A%20%20%20%20%20%20var%20top_var%20%3D%20%22top%22%3B%0A%20%20%20%20%20%20console.log%28global_var,%20bottom_var,%20middle_var,%20top_var%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20top%28%29%0A%20%20%7D%0A%20%20middle%28%29%3B%0A%7D%0Abottom%28%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  const global_var = "g";
  console.log(global_var, bottom_var, middle_var, top_var);
  function bottom() {
    var bottom_var = "b";
    console.log(global_var, bottom_var, middle_var, top_var);
    function middle() {
      var middle_var = "m";
      console.log(global_var, bottom_var, middle_var, top_var);
      function top() {
        var top_var;
        console.log(global_var, bottom_var, middle_var, top_var);
      }
      top()
    }
    middle();
  }
  bottom();
}
```


[TOP](#functions-by-example)



___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
