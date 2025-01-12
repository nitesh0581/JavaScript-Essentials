<div align="center">
  <h1>JS is ❤️❤️! Do it everyday 💯💯</h1>
</div>

1. **What will be the output ?**

```JS
console.log(typeof fn);

function fn() {
  return "reassign";
}
var fn = "reassign";

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: `function`

1. console.log(typeof fn);: This line is executed first. At this point, foo is hoisted as a variable, but it has not been assigned a value yet, so its type is undefined.

2. function fn() { return "reassign" }: The function declaration is hoisted to the top of its containing scope (in this case, the entire script or function). This means that the foo variable is now a function.

3. var fn = "reassign";: This line is executed last. It reassigns the variable fn with the string value "reassign" overwriting the previous function declaration.

So, when you call console.log(typeof fn); after the entire script has been executed, the output will be "function" because, at the time of the console.log statement, fn refers to the function declaration that was hoisted.

</p>
</details>

</li>

---

2. **What will be the output ?**

```JS
function fn() {
  return "reassign";
}
var fn;

console.log(typeof fn);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: `function`

function fn() { return "reassign"; }: This is a function declaration, and it creates a function named fn. Function declarations are hoisted to the top of their containing scope.

var fn; This declares a variable foo. However, since there's already a function declaration named foo in the same scope, the variable declaration doesn't override the function declaration.

</p>
</details>

</li>

---

3. **What will be the output ?**

```JS
function outer() {
    inner();
    return;
    function inner() {
      console.log("bar");
    }
  }
  outer();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "bar"

This ```JS code defines two functions: outer and inner. When you run outer(), it calls inner(), logs "bar" to the console, and exits the outer function. The return statement doesn't affect the output. The final result is that "bar" is printed to the console when the script is executed.


</p>
</details>

</li>

---
4. **What will be the output ?**

```JS
  if (true) {
    function fn() {
      console.log(1);
    }
  } else {
    function fn() {
      console.log(2);
    }
  }
  fn();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:1

In this code snippet, there's a conditional block, but due to function hoisting, both branches define a function named fn. Regardless of the condition, the function defined inside the if block is the one that gets hoisted and is accessible outside the block. Consequently, when fn() is called outside the conditional block, it prints "1" to the console. The condition itself (if true or false) doesn't affect the output.

</p>
</details>

</li>

---
5. **What will be the output ?**

```JS
  function foo(x) {
    x();
    function x() {
      console.log("foo");
    }
  }

  foo(function () {
    console.log("bar");
  });

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: foo


The code defines a function foo that takes a function x as a parameter. Inside foo, it immediately calls x(), and then declares a nested function x that logs "foo" to the console.

When foo is invoked with an anonymous function logging "bar," due to hoisting, the nested x inside foo is called first, logging "foo," and then the anonymous function is invoked, logging "bar."


</p>
</details>

</li>

---

6. **What will be the output ?**

```JS
  foo();
  function foo() {
    console.log(1);
  }
  var foo = function () {
    console.log(2);
  };
  function foo() {
    console.log(3);
  }
  foo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3


The given code will output: 3
Here's the explanation:

Function declarations are hoisted to the top during the compilation phase. So, when the code is executed:

```JS
function foo() {
  console.log(1);
}
```
The first function declaration function foo() is hoisted to the top, and it logs 1 to the console.

Next, there is a variable declaration using var:

```JS
var foo = function () {
  console.log(2);
};
```
This declaration is also hoisted to the top, but it doesn't override the previous function declaration. At this point, foo still refers to the function declared in step 1.

Another function declaration follows:

```JS
function foo() {
  console.log(3);
}
```
Again, this function declaration is hoisted to the top. It overrides the previous function declaration and sets foo to the new function that logs 3 to the console.

When foo() is called:

```JS
foo();
```
It executes the latest function assigned to foo, which logs 3 to the console.


</p>
</details>

</li>

---
7. **What will be the output ?**

```JS
   function animal() {
    console.log("Cat");
  }
  var otherAnimal;
  animal();
  otherAnimal();
  otherAnimal = function () {
    console.log("Dog");
  };

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: error

```JS
function animal() {
    console.log("Cat");
}

var otherAnimal; // Variable declaration (undefined)

animal(); // Function invocation - Outputs: Cat

otherAnimal(); // Error: otherAnimal is not a function

otherAnimal = function () {
    console.log("Dog");
};
```

In this code, an attempt to invoke otherAnimal before its initialization as a function will result in an error. The error occurs because otherAnimal is assigned a function expression after the attempted invocation.





</p>
</details>

</li>

---


8. **What will be the output ?**

```JS
   function animal() {
    console.log("Cat");
  }
  var otherAnimal;
  animal();
  otherAnimal();
  otherAnimal = function () {
    console.log("Dog");
  };

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ƒ b() {} 6


Function Expression Assignment:

```JS

b = function a() {};

```
Declares a function expression a and assigns it to the variable b.

Variable Declaration and Assignment:

```JS

var a = (b = 6);
```
Assigns the value 6 to b and assigns the result (which is 6) to a.

Function Expression Assignment:

```JS

a = function b() {};
```
Declares a function expression b and assigns it to a.

Function Declarations (hoisted):

```JS

function b() {}
function a() {}
```
Hoisted function declarations for b and a.

Logging the Variables:

```JS

console.log(a, b);
```
Outputs the values, resulting in:

```JS

function b() 6
```
In summary, the code involves variable reassignments, function expressions, and hoisted function declarations. The console.log statement shows the final values of a (function expression) and b (assigned number).

</p>
</details>

</li>

---


9. **What will be the output ?**

```JS
  var a = 10;
console.log("line number 2", a);
function fn() {
  console.log("line number 4", a);
  var a = 20;
  a++;
  console.log("line number 7", a);
  if (a) {
    var a = 30;
    a++;
    console.log("line number 11", a);
  }
  console.log("line number 13", a);
}
fn();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:
line number 4 undefined
line number 7 21
line number 11 31
line number 13 31

Certainly! Let's break down the code step by step and see what gets printed to the console:

```JS

var a = 10;
console.log("line number 2", a);
Output: line number 2 10
```

Here, a variable a is declared and assigned the value 10. The value of a is then logged to the console.

```JS

function fn() {
  console.log("line number 4", a);
  var a = 20;
  a++;
  console.log("line number 7", a);
  if (a) {
    var a = 30;
    a++;
    console.log("line number 11", a);
  }
  console.log("line number 13", a);
}
fn();
```
Output:

```JS

line number 4 undefined
line number 7 21
line number 11 31
line number 13 31
```
Inside the function fn, a new variable a is declared and assigned the value 20, but the logging of the variable at "line number 4" prints undefined because there is a variable shadowing effect. The inner variable a is hoisted to the top of the function, so at the point of logging, it exists but hasn't been assigned a value yet.

The value of a is then incremented and logged at "line number 7". Inside the if statement, a new variable a is declared and assigned the value 30, incremented, and logged at "line number 11". After exiting the if statement, the value of a is logged again at "line number 13".

So, the final output shows the values of a at different points inside the function. The variable a inside the function does affect the outer a due to the hoisting and variable shadowing.


</p>
</details>

</li>

---

10. **What will be the output ?**

```JS
function foo() {
  let a = (b = 0);
  a++;
  return a;
}
foo();
console.log(typeof a);
console.log(typeof b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:undefined,number

Inside the function foo, there is a variable a declared using let, and it is assigned the value (b = 0). Here, the expression (b = 0) assigns 0 to both variable b and variable a. The parentheses are used to avoid any potential issues with the assignment.

a is then incremented by 1 with a++, and the function returns the updated value of a.

When the function foo is invoked with foo();, it doesn't explicitly use the returned value, so the result (the incremented value of a) is not logged or stored anywhere.

After the function call, there are two console.log statements:

console.log(typeof a);: This attempts to log the type of the variable a outside the function. However, since a is declared with let inside the function, it has block scope and is not accessible outside the function. As a result, this line will throw an error, and the script execution may stop at this point.
console.log(typeof b);: This attempts to log the type of the variable b outside the function. Surprisingly, b is not declared with let or var inside the function, making it implicitly a global variable. As a result, this line will log the type of b, which is number.
In summary, the code will likely throw an error at the first console.log statement (typeof a) due to the block-scoping of a. The second console.log statement (typeof b) will log number, as b becomes a global variable due to the absence of a declaration keyword (let, var, or const) inside the function.
</p>
</details>

</li>

---

11. **What will be the output ?**

```JS
let a = {};
let b = { key: "b" };
let c = { key: "c" };

a[b] = 123;
a[c] = 456;

console.log(a[b]);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 456

In this code, a is an empty object that is being assigned properties using the square bracket notation. The values of the properties are being set to the numbers 123 and 456. The keys of the properties are the objects b and c.

When the console.log statement is executed, it logs the value of the property of a whose key is the object b. In this case, the value of this property is 456, because the value of the property was last set to 456 when the object c was used as the key.

This behavior occurs because when objects are used as keys in an object, the object's default behavior is to convert the object to a string representation. In this case, both b and c are converted to the string [object Object], which means that they both end up being used as the same key in the a object. As a result, the value of the property that is set using the object c as the key overwrites the value of the property that was set using the object b as the key.

So the object a looks like -

```JS
{
    "[object Object]": 456
}
```
</p>
</details>

</li>

---

12. **What will be the output ?**

```JS
let obj1 = { key: "value" };
let obj2 = obj1;
let obj3 = obj2;

obj1.key = "new value";
obj2 = { key: "another value" };

console.log(obj1.key, obj2.key, obj3.key);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼:  `new value` `another value` `new value`

In this code, we are declaring three variables obj1, obj2, and obj3, and assigning an object to each of them. Then, we are reassigning a new object to obj2 and modifying a property of obj1.

When the console.log statement is executed, it logs the values of the key property for each object. The value of the key property for obj1 is "new value", the value of the key property for obj2 is "another value", and the value of the key property for obj3 is "new value".

This is because when an object is assigned to a variable, the variable stores a reference to the object in memory rather than the object itself. Changing the value of a property of the object using one variable will affect the value of that property when accessed using a different variable that references the same object. However, reassigning a new object to a variable will change the reference stored in that variable, so the original object is no longer accessible using that variable.

In this case, the value of the key property for obj1 was changed to "new value" using the obj1 variable, which affected the value of the key property when accessed using the obj3 variable, because both variables reference the same object. However, the value of the key property for obj2 was not affected, because the obj2 variable was reassigned to reference a new object.
</p>
</details>

</li>

---

13. **What will be the output ?**

```JS

const obj = {
  a: "foo",
  b: function () {
    console.log(this.a);
  },
};

const c = obj.b;

obj.b();
c();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: foo, undefined

When the method obj.b is called directly on obj, the output will be "foo". This is because this refers to the object that the method is called on, and obj.a is equal to "foo".

When the variable c is assigned the value of obj.b, it is a reference to the function itself and not the object obj. When c is called, it is not called on an object, so this will not refer to obj and the value of this.a is undefined. As a result, the output when calling c() will be undefined.

</p>
</details>

</li>

---

14. **What will be the output ?**

```JS
const x = { foo: 1 };
const y = { foo: 2 };

function addFoo(obj) {
  return obj.foo + 1;
}

console.log(addFoo(x));
console.log(addFoo(y));

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2,3

The addFoo function takes an object as an argument and returns the value of obj.foo + 1. When addFoo is called with x as the argument, the output will be 2, because x.foo is equal to 1. When addFoo is called with y as the argument, the output will be 3, because y.foo is equal to 2.

</p>
</details>

</li>

---

15. **What will be the output ?**

```JS
const arr = [1, 2, 3, 4, 5];

for (var i = 0; i < arr.length; i++) {
  setTimeout(function () {
    console.log(i);
  }, 1000);
}

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 5, 5, 5, 5, 5

The setTimeout function is called inside of a loop that iterates through the elements in the arr array. The setTimeout function will execute its callback function after a delay of 1000 milliseconds. However, by the time the delay has elapsed and the callback function is called, the loop will have already completed and the value of i will be 5. As a result, the output will be 5 printed five times.

</p>
</details>

</li>

---

16. **What will be the output ?**

```JS
const arr = [1, 2, 3, 4, 5];

arr.forEach(function (element) {
  console.log(element);
});

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1, 2, 3, 4, 5

The forEach method is called on the arr array and a callback function is passed as an argument. The callback function will be executed for each element in the array, with the element passed as an argument to the callback. As a result, the output will be the elements of the array, 1, 2, 3, 4, and 5, printed on separate lines.

</p>
</details>

</li>

---

17. **What will be the output ?**

```JS
let x = 1;

if (function f() {}) {
  x += typeof f;
}

console.log(x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1undefined

The if statement is evaluating the function f as a boolean value. In JavaScript, functions are truthy values, so the condition will evaluate to true and the code block inside the if statement will be executed. The value of x is then incremented by the string "undefined", which is the result of calling typeof f.

</p>
</details>

</li>

---

18. **What will be the output ?**

```JS
let a = {
  x: 1,
  y: 2,
};
let b = a;
a.x = 5;
console.log(a);
console.log(b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: {x:5, y:2} {x:5, y:2}

JavaScript objects are passed by reference. So when we assigned a object to b. b also pointing to the same object in memory. When we change the value of a.x it also affects b.x

</p>
</details>

</li>

---

19. **What will be the output ?**

```JS
let x = [1, 2, 3];
let y = [1, 2, 3];
let z = y;

console.log(x == y);
console.log(x === y);
console.log(z == y);
console.log(z == x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: false false true false

When comparing two objects with the == operator, it compares their references, not their values. In this case, x and y are different objects with the same values. z is assigned the value of y, so they refer to the same object. As a result, the first comparison returns false, the second comparison also returns false and the third comparison returns true. and the last comparison also returns false.

</p>
</details>

</li>

---

20. **What will be the output ?**

```JS
var x = 0;
for (let i = 0; i < 5; i++) {
  setTimeout(() => {
    x++;
    console.log(x);
  }, 1000);
}

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3 4 5

The for loop is iterating 5 times, and in each iteration, it is scheduling a function to be invoked after 1000 milliseconds (1 second) using setTimeout. This function increments the value of x and logs it.

But all the 5 functions invoked after 1000 milliseconds.

Since, javascript is single threaded and event loop queue all the functions in the event loop and execute them one by one.

But inside each setTimeout callback execution, x++ increments x value by 1.

It makes difference when position of x++ code changes wrt the setTimout callback.

So all the 5 callbacks logs the values in incremental way, which is 1 2 3 4 5.s

</p>
</details>

</li>

---

21. **What will be the output ?**

```JS
let a = { x: 1 };
let b = { x: 2 };
let c = { x: 3 };
let d = { x: 4 };
let e = { x: 5 };
let arr = [a, b, c, d, e];

arr.forEach((obj) => (obj.x = obj.x * 2));

console.log(a.x, b.x, c.x, d.x, e.x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2 4 6 8 10

The code is using the forEach method to iterate over an array of objects, and it is modifying the x property of each object by multiplying it by 2.

It's updating the original objects with x*2 values.

So, the output of the code is 2 4 6 8 10.

</p>
</details>

</li>

---

22. **What will be the output ?**

```JS
let num = 0;

function test() {
  var num = 1;
  return num;
}

console.log(test());
console.log(num);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 0

The code defines a global variable num with the value of 0 and then a function test which declares a local variable num with the value of 1 and returns it.

When test() is called, it first declares a local variable num with the value of 1.

Then the function return statement logs 1 on the console.

After that, it logs the value of global variable num which is 0.

Because the global and local variables have different scope and different memory allocation.

</p>
</details>

</li>

---

23. **What will be the output ?**

```JS
let obj = { name: "John", age: 25 };
let newObj = { ...obj, age: 30 };

console.log(obj.age);
console.log(newObj.age);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 25 30

The code creates an object obj with properties name and age. Then it creates a new object newObj using the spread operator to copy the properties of obj and then it updates the age property to 30.

The spread operator ... creates a new object with properties copied from the original object.

So, the first console.log statement logs the value of age property of obj which is 25.

And, the second console.log statement logs the value of age property of newObj which is 30.

It doesn't affect the original object obj.

</p>
</details>

</li>

---

24. **What will be the output ?**

```JS
const add = (a = 1, b = 2) => a + b;
console.log(add());
console.log(add(5));
console.log(add(undefined, 10));

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 7 11

The code defines a function add which takes two parameters a and b and returns the sum of both. It uses default parameters to assign default values 1 to a and 2 to b if they are not provided.

So, the first console.log statement logs the result of add() which is 1 + 2 = 3 as both the parameters are not provided and default values are used.

The second console.log statement logs the result of add(5) which is 5 + 2 = 7 as only the first parameter is provided and the default value of b is used.

The third console.log statement logs the result of add(undefined, 10) which is 1 + 10 = 11 as the first parameter is provided as undefined and it takes the default value 1 and the second parameter is provided as 10.

</p>
</details>

</li>

---

25. **What will be the output ?**

```JS
const name = "John";
const age = 25;

const user = { name, age };
console.log(user);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { name: "John", age: 25 }

The code defines two variables name and age with values "John" and 25 respectively.

Then, it uses object literal notation to create an object user with properties name and age and the values are assigned from the variables name and age respectively.

So, the console.log statement logs the user object which is { name: "John", age: 25 }.

In ES6+, you can use object literal notation to create objects with properties using the same name as the variables with the values assigned to them.

</p>
</details>

</li>

---

26. **What will be the output ?**

```JS
const arr = [1, 2, 3];
const [a, b, c] = arr;

console.log(a);
console.log(b);
console.log(c);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3

The code defines an array arr with values [1, 2, 3].

Then, it uses destructuring assignment to extract the values from the array arr and assign them to variables a, b, and c respectively.

So, the first console.log statement logs the value of a which is 1.

The second console.log statement logs the value of b which is 2.

The third console.log statement logs the value of c which is 3.

In ES6+, you can use destructuring assignment to extract values from arrays and objects and assign them to variables in a concise way.

</p>
</details>

</li>

---

27. **What will be the output ?**

```JS
console.log(typeof null);
console.log(typeof undefined);
console.log(null === undefined);
console.log(null == undefined);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: object undefined false true

typeof null returns object which is an error in JavaScript. This is a historical bug in the language that cannot be fixed without breaking existing code. So, to check for null, you should use === null instead of typeof operator.

typeof undefined returns undefined.

null === undefined is false because null and undefined are two distinct types in JavaScript.

null == undefined is true because == is the loose equality operator in JavaScript, which performs type coercion before comparison. In this case, both null and undefined are coerced to undefined before comparison, and since they both have the same value, the comparison returns true. However, it is generally recommended to use === instead of == to avoid unexpected behavior due to type coercion.

</p>
</details>

</li>

---

28. **What will be the output ?**

```JS
let x = 5;
{
  let x = 10;
  console.log(x);
}
console.log(x);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 10 5

This is because of the block scoping behavior of the let keyword in ES6.

When we declare a variable with let inside a block (in this case, the block is defined by the curly braces), the variable is only accessible inside that block and its sub-blocks.

In the code above, we define a variable x outside the block with the value of 5. Then we define another variable x inside the block with the value of 10.

The first console.log() statement inside the block will print 10, because x refers to the variable defined inside the block. The second console.log() statement outside the block will print 5, because it refers to the variable defined outside the block.

</p>
</details>

</li>

---

29. **What will be the output ?**

```JS
const obj = { a: 1, b: 2, c: 3 };
const { a, b } = obj;
console.log(a, b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 

This is because of the object destructuring syntax introduced in ES6.

We declare a constant variable obj with an object containing three properties. Then we use object destructuring to extract the properties a and b from the object and assign them to separate variables with the same names.

The console.log() statement then prints the values of the a and b variables, which are 1 and 2 respectively.

</p>
</details>

</li>

---

30. **What will be the output ?**

```JS
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
console.log(arr3);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3, 4, 5, 6]

This is because of the spread syntax (...) introduced in ES6.

The ... operator can be used to spread the elements of an array or the properties of an object into a new array or object.

In the code above, we define two arrays arr1 and arr2. Then we create a new array arr3 by spreading the elements of arr1 and arr2 into it using the spread syntax.

The console.log() statement then prints the contents of arr3, which are the elements of arr1 followed by the elements of arr2.

</p>
</details>

</li>

---

31. **What will be the output ?**

```JS
const arr1 = [1, 2, 3];
const arr2 = [...arr1];

arr2.push(4);

console.log(arr1);
console.log(arr2);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3] [1, 2, 3, 4]

The code creates an array arr1 with the values [1, 2, 3]. It then creates a new array arr2 using the spread syntax (...) to spread the values of arr1 into a new array.

arr2.push(4) adds the value 4 to the end of arr2.

However, arr1 remains unchanged because arr2 is a new array with its own reference to the values of arr1. This is known as creating a shallow copy of the array.

Therefore, the first console.log(arr1) prints [1, 2, 3] and the second console.log(arr2) prints [1, 2, 3, 4].

</p>
</details>

</li>

---

32. **What will be the output ?**

```JS
const x = 10;

function foo() {
  console.log(x);
  const x = 20;
}

foo();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError: Cannot access 'x' before initialization

The foo function attempts to log the value of x before it is initialized. This causes a ReferenceError to be thrown, as x is not yet defined in the function scope.

This happens because of variable hoisting in JavaScript. When a variable is declared with const or let, it is not hoisted to the top of the scope like variables declared with var are. Instead, they are only accessible after they are declared.

Therefore, when console.log(x) is called in the foo function, the local variable x has not yet been initialized, resulting in a ReferenceError.

</p>
</details>

</li>

---

33. **What will be the output ?**

```JS
const a = [1, 2, 3];
const b = a;

b.push(4);

console.log(a);
console.log(b);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [1, 2, 3, 4] [1, 2, 3, 4]

The code creates an array a with the values [1, 2, 3]. It then creates a new variable b and assigns it to a, creating a reference to the same array.

b.push(4) adds the value 4 to the end of the array.

Since a and b reference the same array, both console.log(a) and console.log(b) will print [1, 2, 3, 4].

This is different from the previous example where ... spread operator was used, which created a new array with the same values as the original array instead of referencing the same array.

</p>
</details>

</li>

---

34. **What will be the output ?**

```JS
const companies = [
  { id: "1", name: "Facebook" },
  { id: "2", name: "Apple" },
  { id: "3", name: "Google" },
];

companies.sort((a, b) => (a.name > b.name ? -1 : 1));
console.log(companies);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: [{id: "3", name:"Google"}, {id: "1", name:"Facebook"},{id: "2", name:"Apple"}]

The comparison function takes two parameters, "a" and "b", which represent two elements being compared in the array.

If the "name" property of "a" comes before the "name" property of "b" in alphabetical order, then the function returns -1, which means "a" should come before "b" in the sorted array.

Otherwise, if the "name" property of "a" comes after the "name" property of "b" in alphabetical order, then the function returns 1, which means "b" should come before "a" in the sorted array.

</p>
</details>

</li>

---

35. **What will be the output ?**

```JS
console.log(typeof 42);
console.log(typeof "Hello");
console.log(typeof true);
console.log(typeof [1, 2, 3]);
console.log(typeof { name: "John", age: 25 });
console.log(typeof null);
console.log(typeof undefined);
console.log(typeof function () {});

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: bash Copy code number string boolean object object object undefined function

The typeof operator in JavaScript is used to determine the type of a value or expression. Here's the breakdown of the output:

typeof 42 returns "number" because 42 is a numeric value.<br>
typeof "Hello" returns "string" because "Hello" is a string.<br>
typeof true returns "boolean" because true is a boolean value.<br>
typeof [1, 2, 3] returns "object" because arrays are considered objects in JavaScript.<br>
typeof { name: "John", age: 25 } returns "object" because objects are considered objects in JavaScript.<br>
typeof null returns "object", which is a known quirk in JavaScript. null is considered an object type.<br>
typeof undefined returns "undefined" because it is a special value in JavaScript representing an uninitialized variable.<br>
typeof function() {} returns "function" because it is a function object.

</p>
</details>

</li>

---

36. **What will be the output ?**

```JS
function calculateSum() {
  console.log(result);
  var num1 = 5;
  let num2 = 10;
  const num3 = 15;
  var result = num1 + num2 + num3;
}

calculateSum();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: undefined

In the code, the variable result is declared using the var keyword, but it is assigned a value after the console.log statement.

When JavaScript executes the function calculateSum(), it hoists the variable declaration of result to the top of the function scope. However, since the assignment of the value num1 + num2 + num3 comes after the console.log statement, the variable is undefined at the point of the console.log.

So, the code is effectively interpreted like this:

```JS
function calculateSum() {
  var result; // Variable declaration is hoisted to the top

  console.log(result); // undefined

  var num1 = 5;
  let num2 = 10;
  const num3 = 15;
  result = num1 + num2 + num3; // Assignment is performed here
}

calculateSum();
```

Since the variable result is hoisted, it exists in the function scope but does not have any assigned value until after the console.log statement. Therefore, when console.log(result) is executed, the variable result exists but is undefined.

</p>
</details>

</li>

---

37. **What will be the output ?**

```JS
let x = 10;

function updateX() {
  if (true) {
    let x = 20;
    console.log(x);
  }
  console.log(x);
}

updateX();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 20, 10

In this code, the variable x is declared and assigned a value of 10 outside the updateX function.

Inside the function, a new block is created using an if statement. Within that block, a new variable x is declared and assigned a value of 20 using let. This creates a separate scope for the inner x, which is only accessible within the if block.

When the console.log statements are executed, the first one inside the if block will output 20, as it refers to the inner x variable. The second console.log statement outside the if block will output 10, as it refers to the outer x variable.

Therefore, the output will be 20, 10.

</p>
</details>

</li>

---

38. **What will be the output ?**

```JS
const person = {
  name: "John",
  age: 30,
};

Object.freeze(person);
person.age = 40;

console.log(person.age);

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 30

In this code, the Object.freeze() method is used to make

the person object immutable. This means that the properties of the object cannot be modified.

When attempting to assign a new value to person.age after freezing the object, it does not throw an error or modify the object. Instead, it silently fails in non-strict mode and throws a TypeError in strict mode.

Since the code is not running in strict mode, the assignment person.age = 40 does not have any effect. Therefore, when console.log(person.age) is executed, it will output the original value of 30.

Hence, the output will be 30.

</p>
</details>

</li>

---

39. **What will be the output ?**

```JS
function foo() {
  let x = 1;

  function bar() {
    let y = 2;
    console.log(x + y);
  }

  bar();
}

foo();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3

In this code, there are two nested functions: foo and bar. The variable x is declared and assigned a value of 1 within the foo function, while the variable y is declared and assigned a value of 2 within the bar function.

When the foo function is called, it invokes the bar function. Inside the bar function, the values of x and y are accessed and summed together using console.log(x + y).

Since x is accessible within the bar function due to lexical scoping, the value of x is 1. Similarly, the value of y is 2. Therefore, the output of console.log(x + y) will be 3.

Hence, the correct answer is 3.

</p>
</details>

</li>

---

40. **What will be the output ?**

```JS
let x = 10;

function outer() {
  console.log(x);

  if (false) {
    var x = 20;
  }
}

outer();

```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: undefined

In this code snippet, there's a variable hoisting issue with the var declaration inside the outer function. The variable x is declared using var within the outer function scope.

When the function outer() is called, the console.log(x) statement is executed. At this point, the variable x is hoisted to the top of the function scope and is initialized with undefined. This means that the local variable x inside the function is different from the global x.

The if (false) block will not be executed, so the assignment var x = 20; will not take place.

Thus, the console.log(x) statement inside the outer function will log the value of the locally hoisted variable x, which is undefined.

Hence, the correct answer is undefined.

</p>
</details>

</li>

---

41. **What will be the output ?**

```JS
const obj = {
  a: 1,
  b: 2,
  c: {
    a: 3,
    b: 4,
  },
};

const {
  a,
  b,
  c: { a: nestedA },
} = obj;

console.log(a, b, nestedA);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 3

This code snippet uses destructuring assignment to extract values from the obj object. It extracts the properties a, b, and the nested property a from the c object and assigns them to the corresponding variables a, b, and nestedA, respectively.

After destructuring, the variables will hold the following values:

a: 1 (value of obj.a)
b: 2 (value of obj.b)
nestedA: 3 (value of obj.c.a)
When console.log(a, b, nestedA) is executed, it will print 1 2 3, as the values of the variables match the above assignments.

Hence, the correct answer is 1 2 3.

</p>
</details>

</li>

---

42. **What will be the output ?**

```JS
function sum(){
    let a = 8;
    const b=2;
    var c=a+b;
}
console.log(a,b,c)
sum()
console.log(a,b,c)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: error error

console.log(a)
// Reference error: a is not defined

console.log(b)
// Reference error: a is not defined

console.log(c)
// Reference error: a is not defined

sum()

console.log(a)
// Reference error: a is not defined

console.log(b)
// Reference error: b is not defined

console.log(c)
//Output: undefined

</p>
</details>

</li>

---

43. **What will be the output ?**

```JS
let arr=[1,2,3,4,5]
console.log(arr[2], arr.length);
arr.length=0;
console.log(arr[2], arr.length);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 5 undefined 0

As we can see in above code 1st questions is so easy but second is bit tricky one for second we are re-assigning the value of arr.length which logically we can do that's why after assign new value to arr.length our output is undefined for index value and 0 for arr.length.

</p>
</details>

</li>

---

44. **What will be the output ?**

```JS
for (var i = 0; i < 3; i++) {
  setTimeout(function() { alert(i); }, 1000 + i);
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 3 3 3

As we are using var so which is a global scope that's why as we are calling setTimeout which itself take time to RUN is call stack so within that time all Loops is finished that's why it takes last value which is 3 in each iteration.

</p>
</details>

</li>

---

45. **What will be the output ?**

```JS
for(let i = 0; i <5; i++){
	setTimeout(()=>{
		console.log(i);
    },0)
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0 1 2 3 4

It relates to previous questions, as we are using let so which is a block scope that's why it keeps increase until loop didn't finished.

</p>
</details>

</li>

---

46. **What will be the output ?**

```JS
let count = 0;
(function immediate() {
  if (count === 0) {
    let count = 1;
    console.log(count); 
  }
  console.log(count); 
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0 1

As we know code runs top to bottom so when go inside function count === 0 is TRUE as count variable defined before function called so output will be firstly 1 then 0 for second console.log().

</p>
</details>

</li>

---

47. **What will be the output ?**

```JS
console.log(1+false); 
console.log(1+true);
console.log(1-false); 
console.log(1+'2'-1);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 1 2 1 11

internal type coersion

</p>
</details>

</li>

---

48. **What will be the output ?**

```JS
(function fnA(a) {
  return (function fnB(b) {
    console.log(a); 
  })(1);
})(0);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 0

It is immediate runs function as we are calling into () and as we can see we are calling function inside function which is also a Closure concept that's why we are able to get the value of variable b

</p>
</details>

</li>

---

49. **What will be the output ?**

```JS
let randomValue = { name: "Lydia" }
randomValue = 23

if (!typeof randomValue === "string") {
	console.log("It's not a string!")
} else {
	console.log("Yay it's a string!")
}
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Yay it's a string!

The condition within the if statement checks whether the value of !typeof randomValue is equal to "string". The ! operator converts the value to a boolean value. If the value is truthy, the returned value will be false, if the value is falsy, the returned value will be true. In this case, the returned value of typeof randomValue is the truthy value "number", meaning that the value of !typeof randomValue is the boolean value false.

!typeof randomValue === "string" always returns false, since we're actually checking false === "string". Since the condition returned false, the code block of the else statement gets run, and Yay it's a string! gets logged.

</p>
</details>

</li>

---

50. **What will be the output ?**

```JS
const createMember = ({ email, address = {}}) => {
	const validEmail = /.+\@.+\..+/.test(email)
	if (!validEmail) throw new Error("Valid email pls")

	return {
		email,
		address: address ? address : null
	}
}

const member = createMember({ email: "my@email.com" })
console.log(member)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { email: "my@email.com", address: {} }

The default value of address is an empty object {}. When we set the variable member equal to the object returned by the createMember function, we didn't pass a value for the address, which means that the value of the address is the default empty object {}. An empty object is a truthy value, which means that the condition of the address ? address : null conditional returns true. The value of the address is the empty object {}

</p>
</details>

</li>

---

51. **What will be the output ?**

```JS
const promise1 = Promise.resolve('First')
const promise2 = Promise.resolve('Second')
const promise3 = Promise.reject('Third')
const promise4 = Promise.resolve('Fourth')

const runPromises = async () => {
	const res1 = await Promise.all([promise1, promise2])
	const res2  = await Promise.all([promise3, promise4])
	return [res1, res2]
}

runPromises()
	.then(res => console.log(res))
	.catch(err => console.log(err))
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 'Third'

The Promise.all method runs the passed promises in parallel. If one promise fails, the Promise.all method rejects with the value of the rejected promise. In this case, promise3 is rejected with the value "Third". We’re catching the rejected value in the chained catch method on the runPromises invocation to catch any errors within the runPromises function. Only "Third" gets logged, since promise3 is rejected with this value.

</p>
</details>

</li>

---

52. **What will be the output ?**

```JS
const user = {
	email: "my@email.com",
	updateEmail: email => {
		this.email = email
	}
}

user.updateEmail("new@email.com")
console.log(user.email)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: my@email.com

The updateEmail function is an arrow function, and is not bound to the user object. This means that the this keyword is not referring to the user object, but refers to the global scope in this case. The value of email within the user object does not get updated. When logging the value of user.email, the original value of my@email.com gets returned.

</p>
</details>

</li>

---

53. **What will be the output ?**

```JS
const animals = {};
let dog = { emoji: '🐶' }
let cat = { emoji: '🐈' }

animals[dog] = { ...dog, name: "Shubham" }
animals[cat] = { ...cat, name: "Swati" }

console.log(animals[dog])
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: { emoji: "🐈", name: "Swati" }

Object keys are converted to strings.

Since the value of dog is an object, animals[dog] actually means that we’re creating a new property called "[object Object]" equal to the new object. animals["[object Object]"] is now equal to { emoji: "🐶", name: "Shubham"}.

cat is also an object, which means that animals[cat] actually means that we’re overwriting the value of animals["[object Object]"] with the new cat properties.

Logging animals[dog], or actually animals["[object Object]"] since converting the dog object to a string results "[object Object]", returns the { emoji: "🐈", name: "Swati" }

</p>
</details>

</li>

---

54. **What will be the output ?**

```JS
const fruit = ['🍌', '🍊', '🍎']

fruit.slice(0, 1)
fruit.splice(0, 1)
fruit.unshift('🍇')

console.log(fruit)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ['🍇', '🍊', '🍎']

First, we invoke the slice method on the fruit array. The slice method does not modify the original array, but returns the value that it sliced off the array: the banana emoji. Then, we invoke the splice method on the fruit array. The splice method does modify the original array, which means that the fruit array now consists of ['🍊', '🍎']. At last, we invoke the unshift method on the fruit array, which modifies the original array by adding the provided value, ‘🍇’ in this case, as the first element in the array. The fruit array now consists of ['🍇', '🍊', '🍎'].

</p>
</details>

</li>

---

55. **What will be the output ?**

```JS
const user = {
	email: "e@mail.com",
	password: "12345"
}

const updateUser = ({ email, password }) => {
	if (email) {
		Object.assign(user, { email })
	}

	if (password) {
		user.password = password
	}

	return user
}

const updatedUser = updateUser({ email: "new@email.com" })

console.log(updatedUser === user)
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: true

The updateUser function updates the values of the email and password properties on user, if their values are passed to the function, after which the function returns the user object. The returned value of the updateUser function is the user object, which means that the value of updatedUser is a reference to the same user object that user points to. updatedUser === user equals true.

</p>
</details>

</li>

---

56. **What will be the output ?**

```JS
const person = {
  name: 'Tutu Singh',
  hobbies: ['swimming'],
};

function addHobby(hobby, hobbies = person.hobbies) {
  hobbies.push(hobby);
  return hobbies;
}

addHobby('running', []);
addHobby('dancing');
addHobby('baking', person.hobbies);

console.log(person.hobbies);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ["swimming", "dancing", "baking"]

The addHobby function receives two arguments, hobby and hobbies with the default value of the hobbies array on the person object.

First, we invoke the addHobby function, and pass "running" as the value for hobby and an empty array as the value for hobbies. Since we pass an empty array as the value for hobbies, "running" gets added to this empty array.

Then, we invoke the addHobby function, and pass "dancing" as the value for hobby. We didn't pass a value for hobbies, so it gets the default value, the hobbies property on the person object. We push the hobby dancing to the person.hobbies array.

Last, we invoke the addHobby function, and pass "baking" as the value for hobby, and the person.hobbies array as the value for hobbies. We push the hobby baking to the person.hobbies array.

After pushing dancing and baking, the value of person.hobbies is ["swimming", "dancing", "baking"]

</p>
</details>

</li>

---

57. **What will be the output ?**

```JS
const add = x => x + x;

function myFunc(num = 2, value = add(num)) {
  console.log(num, value);
}

myFunc();
myFunc(3);
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: 2 4 and 3 6

First, we invoked myFunc() without passing any arguments. Since we didn't pass arguments, num and value got their default values: num is 2, and value is the returned value of the function add. To the add function, we pass num as an argument, which had the value of 2. add returns 4, which is the value of value.

Then, we invoked myFunc(3) and passed the value 3 as the value for the argument num. We didn't pass an argument for value. Since we didn't pass a value for the value argument, it got the default value: the returned value of the add function. To add, we pass num, which has the value of 3. add returns 6, which is the value of value.

</p>
</details>

</li>

---

58. **What will be the output ?**

```JS
const myPromise = Promise.resolve(Promise.resolve('Promise'));

function funOne() {
  setTimeout(() => console.log('Timeout 1!'), 0);
  myPromise.then(res => res).then(res => console.log(`${res} 1!`));
  console.log('Last line 1!');
}

async function funTwo() {
  const res = await myPromise;
  console.log(`${res} 2!`)
  setTimeout(() => console.log('Timeout 2!'), 0);
  console.log('Last line 2!');
}

funOne();
funTwo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: Last line 1! Promise 2! Last line 2! Promise 1! Timeout 1! Timeout 2!

First, we invoke funOne. On the first line of funOne, we call the asynchronous setTimeout function, from which the callback is sent to the Web API. (see my article on the event loop here.)

Then we call the myPromise promise, which is an asynchronous operation. Pay attention, that now only the first then clause was added to the microtask queue.

Both the promise and the timeout are asynchronous operations, the function keeps on running while it's busy completing the promise and handling the setTimeout callback. This means that Last line 1! gets logged first, since this is not an asynchonous operation.

Since the callstack is not empty yet, the setTimeout function and promise in funOne cannot get added to the callstack yet.

In funTwo, the variable res gets Promise because Promise.resolve(Promise.resolve('Promise')) is equivalent to Promise.resolve('Promise') since resolving a promise just resolves it's value. The await in this line stops the execution of the function until it receives the resolution of the promise and then keeps on running synchronously until completion, so Promise 2! and then Last line 2! are logged and the setTimeout is sent to the Web API. If the first then clause in funOne had its own log statement, it would be printed before Promise 2!. Howewer, it executed silently and put the second then clause in microtask queue. So, the second clause will be printed after Promise 2!.

Then the call stack is empty. Promises are microtasks so they are resolved first when the call stack is empty so Promise 1! gets to be logged.

Now, since funTwo popped off the call stack, the call stack is empty. The callbacks waiting in the queue (() => console.log("Timeout 1!") from funOne, and () => console.log("Timeout 2!") from funTwo) get added to the call stack one by one. The first callback logs Timeout 1!, and gets popped off the stack. Then, the second callback logs Timeout 2!, and gets popped off the stack.

</p>
</details>

</li>

---

59. **What will be the output ?**

```JS
const emojis = ['🥑', ['✨', '✨', ['🍕', '🍕']]];

console.log(emojis.flat(1));
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ['🥑', '✨', '✨', ['🍕', '🍕']]

With the flat method, we can create a new, flattened array. The depth of the flattened array depends on the value that we pass. In this case, we passed the value 1 (which we didn't have to, that's the default value), meaning that only the arrays on the first depth will be concatenated. ['🥑'] and ['✨', '✨', ['🍕', '🍕']] in this case. Concatenating these two arrays results in ['🥑', '✨', '✨', ['🍕', '🍕']]

</p>
</details>

</li>

---

60. **What will be the output ?**

```JS
const myPromise = Promise.resolve('yo man!, I did it');

(async () => {
  try {
    console.log(await myPromise);
  } catch {
    throw new Error(`Oops, I couldn't do it`);
  } finally {
    console.log('Oh finally!, something has happend');
  }
})();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: "yo man!, I did it"   "Oh finally!, something has happend"

In the try block, we're logging the awaited value of the myPromise variable: "yo man!, I did it". Since no errors were thrown in the try block, the code in the catch block doesn't run. The code in the finally block always runs, "Oh finally!, something has happend" gets logged.

</p>
</details>

</li>

---

61. **What will be the output ?**

```JS
const randomValue = 21;

function getInfo() {
  console.log(typeof randomValue);
  const randomValue = 'Tutu Singh';
}

getInfo();
```

<br/>

<details>
<summary><b>Answer</b></summary>
<p>

#### ➼➼➼: ReferenceError

Variables declared with the const keyword are not referenceable before their initialization: this is called the temporal dead zone. In the getInfo function, the variable randomValue is scoped in the functional scope of getInfo. On the line where we want to log the value of typeof randomValue, the variable randomValue isn't initialized yet: a ReferenceError gets thrown! The engine didn't go down the scope chain since we declared the variable randomValue in the getInfo function.

</p>
</details>

</li>

---
