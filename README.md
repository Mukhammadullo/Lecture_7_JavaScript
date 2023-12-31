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

# 2.What is Asynchronous?

_Asynchronicity means that if JavaScript has to wait for an operation to complete, it will execute the rest of the code while waiting._
_JavaScript can behave in an asynchronous way. Let’s have a look at some techniques that are useful for asynchronous JavaScript:_

>1._promises-writing asynchronous JavaScript code is made easy with promises.  They enable you to create code that runs after a predetermined period of time or when a predetermined condition is satisfied._
_A promise may have one of three states
• Pending
• Fulfilled
• Rejected_
```js

function newPromise(url){
return new Promise ((resolve,reject)=>{
fetch(url)
.then(response=>response.json())
.then(data=>resolve(data))
.catch(error=>reject(error));
});
}

newPromise("https://jsonplacholder.typicode.com/todos/1")
.then(data=>console.log(data))
.catch(error=>console.error(error));

```


>2._callbacks-this allows for asynchronous code to be written in a synchronous fashion._
```js
function new(callback){
    setTimeout(function(){
        callback("hello new line")
    },1000)
}

new(function(value){
    consol.log(value)
});
```
>3._async/await-async/await is a more recent technique for creating asynchronous JavaScript code. It helps you write more succinct and readable code that will execute after a set period of time or when a set condition is met._

```js
let url="https://jsonplacholder.typicode.com/todos/1"

async function getData(url){
try{
let reponse= await fetch(url);
let data=await response.json();
console.log(data);
}catch(error){
console.error(error)}
}

getData()

```
> _What is API?-API stands for Application Programming Interface and is a concept that is not limited or specific to JavaScript, but is used in almost all web application languages._
> _What is Fetch API?-The global fetch() method starts the process of fetching a resource from the network, returning a promise that is fulfilled once the response is available.The fetch() method's parameters are identical to those of the Request() constructor._

> _Get Async_
```js
//get
let url="https://jsonplaceholder.typicode.com/posts"
async function getData(){
try{
    let response=await fetch(url);
    let data=await response.json();
    console.log(data)  
}catch(error){
console.error(error)}
}

getData()
```
> _Post_Async_
```js


async function postUser(newUser){
try{
let reponse =await fetch(`${url}${id}`,
method:"POST",
headers:{
Accept:"application/json"
"Content-Type":"application/json",
}
body:JSON.stringify(newUser)
}catch  (error){
console.error(error)
}
}

//newUser-is Object

```

> _PUT async_
    ```js
async function putUser(editUser){
try{
let reponse =await fetch(`${url}${id}`,
method:"PUT",
headers:{
Accept:"application/json"
"Content-Type":"application/json",
}
body:JSON.stringify(editUser)
}catch  (error){
console.error(error)
}
}

//id is a id of user
//editUser is a object{}

    ```

> _DELETE async_
```js

async function  delUser(id){
try{
let reponse=await fetch(`${url}${id}`)
}catch(error)
{
console.error(error)
}
}

 ```

# _3.What is axios? 
_Axios is a Javascript library used to make HTTP requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. It can be used intercept HTTP requests and responses and enables client-side protection against XSRF. It also has the ability to cancel requests._

```js

//use in inner -> HTML
//<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
//<script src="https://unpkg.com/axios/dist/axios.min.js"></script>

//GET

async function getData(){
try{
let {data}=await axios.get(`url`)
}catch(error){
console.error(error)
}
}

//POST

async funtion postUser(editUser){
try{
let {data}=await axios.post(`url`,editUser)
}catch(error){
consle.error(error)
}
}

//user->is a obJect{}

```

> _Put_
```js

async function putUser(id, editUser){
try{
let {data}= await axios.put(`$url}${id}`, editUser)
}catch (error){
console.error(error)
}
}

```


>_Delete_
```js

async function delUser(id){
try{
let {data}=await axios.delete(`${url}${id}`)
}catch (error){
console.error(error)
}

//id is a id of user

```


