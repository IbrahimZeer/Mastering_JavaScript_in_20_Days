# Doggos Quiz Game
## while loop
if we want to loop over and over again until something changes to stop looping
while loop allow us to keep running and chunk of code
```javascript
let fiveRandomNumbers = [];
while (fiveRandomNumbers.length < 5) {
    fiveRandomNumbers.push(Math.random());
}
// output = 5 random numbers

```
---
## setTimeout
Usually, our JS code does things that are very quick So JS can usually run straight through our program "synchronously"
```javascript
console.log("This will print in a New York minute");
console.log("This will print one New York minute later");
```
But when we need to do something that takes a long time JS can only do one task at a time ("single-threaded") So when we give JS a task that takes a while, it doesn't stop and wait
```javascript
console.log("This will print first");
setTimeout(() => console.log("This will print third"), 1000);
console.log("This will print second");
```
---
**Some things that take time:**
- eventsAsking a user to pick a file

- Getting permission to access the camera/mic

- Loading data from the interwebs

---

# data Fetching & promises
APIs provide URLs that point at data we care about
```json
{
    "message": [
      "afghan",
      "basset",
      "blood",
      "english",
      "ibizan",
      "plott",
      "walker"
    ],
    "status": "success"
  }
```
Some time we need data from elsewhere on the web and we can do that by accessing URL , API
---
fetch() : build in function to lode data from APIs in js
---
Promises : something that comes into play in js when we are doing things that take a long time or looking for things that we are going to need some time to find.

```javascript
fetch("https://dog.ceo/api/breed/hound/list")
// output = Promise { <state>: "pending" }
```
---
**Promises can be in 3 possible states:**

- `pending`: still waiting for the value, hang tight

- `fulfilled` (aka "resolved"): finally got the value, all done

- `rejected`: sorry couldn't get the value, all done It takes time for Promises to resolve, so they are  "asynchronous"

---

await : tell JS to stop and wait for an asynchronous operation to finish

```javascript
let response = await fetch("https://dog.ceo/api/breed/hound/list");
console.log(response);
```
>**Note : [a] 200 mean => ok , [b] 404 mean => not Found**
---
```javascript
response.json()
//  this is just a conventional format that js knows how to read
```

```javascript
let response = await fetch("https://dog.ceo/api/breed/hound/list");
let body = await response.json();

// to capture that calue as a variable like body
// body will be Object 
```
---
# Destructuring
Destructuring is a fancy way of declaring multiple variables at once
```javascript
const sp = [
    {name : "ibraheem" , nicname : "ibra" },
]

let {name , nicname } = sp[0]

// name = ibraheem
// nicname = ibra

//========================================

let {nicname} = sp[0]
// it just care about nicname only
// if we try to to get naem will return ""
```
---
```javascript
let [one , two , three] = [1 , 2 , 3]

// one => 1 
// two => 2 
// three => 3

let [six , five , four ] = [6 , 5 , 4]
```
We can ignore the values in the array we don't need 
```javascript
const [,,thirty] = [10 , 20 , 30 , 40 ]

// thirty => 30

let {title} = document
// title ... the output = title of page 

let [one , ...others] = [1,2,3,4,5,6,7,8,9]

// one => 1 
// others => [2, 3, 4, 5, 6, 7, 8, 9]
```
---
`split()` method takes a pattern and divides a String into an ordered list of substrings by searching for the pattern, puts these substrings into an array, and returns the array

```javascript
"ibraheem Zeer".split('ee')
// output = ['ibrah', 'm Z', 'r']
//====================================
"ibraheem Zeer".split('ee')[1]
// output = 'm z'
```
---
`reverse()` method reverses an array in place and returns the reference to the same array, the first array element now becoming the last, and the last array element becoming the first. In other words, elements order in the array will be turned towards the direction opposite to that previously stated.

```javascript
let splitArray = "poodle-standered".split("-")
splitArray // output = ['poodle', 'standered']

splitArray.reverse()
splitArray // output = ['standered', 'poodle']
```
---
`trim()` method removes whitespace from both ends of a string and returns a new string, without modifying the original string.
```javascript
let [brd , sbrd] = "beagle".split("-")
// when use join(" ") the space will return with output
[undefined , "beagle"].join(" ") // ' beagle' , the space is here

// use trim to fix the problem
[undefined , "beagle"].join(" ").trim();
// output = beagle // The space has been removed
```
---
# Async
`async` : function declaration creates a binding of a new async function to a given name. The await keyword is permitted within the function body, enabling asynchronous, promise-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains
```javascript
function fetchResponse(url) {
    const response = await fetch(url);
    return response;
}
// this code will return Error because we use await without async
// We need to make it an async function
async function fetchResponse(url) {
    const response = await fetch(url);
    return response;
}
// This tells JS to expect to await async operations inside the function
```

```javascript
// Full function use async ... await and return message such as array 
async function fetchMessage(url) {
    const response = await fetch(url)
    const body = await response.json()
    const { message } = body;
    return message;
};
```
---
## createElement() method
`document.createElement()` method creates the HTML element specified by __tagName__












