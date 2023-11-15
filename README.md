# 1.What is Synchronous in JavaScript?
>_JavaScript is synchronous by default:Synchronous code is executed line by line.Each line of code waits for previous line to finish;_
>_Long-running operations  block code execution_

```js

let one="Hello from first line"
let second="Hello from second line"
let third="Hello from third line"

console.log(one, second, third) 
// "Hello from first line"
// "Hello from second line"
// "Hello from third line"
```

# 2.what is Asynchronous?
_Asynchronous in JavaScript is a programming paradigm that allows you to run multiple tasks simultaneously in a single process and work with large amounts of data without blocking other tasks._

_In JavaScript, asynchrony is achieved through callbacks, promises, and asynchronous functions. For example, methods such as setTimeout(), setInterval() and asynchronous AJAX requests are asynchronous._


```js
setTimeout(function(){
    console.log('Hello new Line!');
}, 2000);
```

# 3.Callback-Callbacks are functions that are passed as arguments to other functions and are executed when the called function completes its task. Callbacks can be used to handle asynchronous operations by passing a callback function to an asynchronous method, which then calls the callback function when the operation is completed.

```js
function new(callback){
    setTimeout(function(){
        callback("hello new line")
    },1000)
}

foo(function(value){
    consol.log(value)
});
```


# 4.New Promise -A Promise is an object that represents an activity that can be completed and return a result in the future, including an asynchronous operation.

```js
function main(a) {
  return new Promise(resolve => setTimeout(resolve, a));
}

main(2000).then(() => console.log("4 seconds"));


fetch('http://example.com/data.json')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```
