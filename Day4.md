# Events & Handlers

We can detect events with JS using an event listener The **.addEventListener()**

```
document.addEventListener("click", () => {
    console.log("clicked")
});
// when the code run if we clicked on page , in console we can see "clicked"
```
---
JS passes an event object to the handler function with information about the event If we accept this as a parameter, we can use it to get details
```
document.addEventListener("click", (event) => {
    console.log(event);
});
```
----
event.target is the element the event fired on
```
document.addEventListener("click", (event) => {
    console.log(event.target);
});
// if we click on anything such as background page , the output will be details of background page
```
---
**Types of events**
- "click"
- "dblclick"
- "mouseover"
- "mouseout"
---

# Conditionals
An expression whose value is used as a condition.
```
let age = [15 , 20 , 19 , 22 , 50 , 30 , 40];
let moreThan19Counter = 0
for(let i = 1 ; i <= age.length ; i++){
    if(age[i] > 19){
        console.log(moreThan19Counter += 1 )
    }
}

//=======================================================

function comp(x , y) {
    if (x == y){
        console.log(`${x} Equal to ${y}`)
    }else if (x < y) {
        console.log(`${x} less than ${y}`)
    } else {
        console.log(`${x} greater than ${y}`)
    }
}

comp(9,5) // out = 9 greater than 5
comp(5,9) // out = 5 less than 9
comp(9,9) // out = 9 Equal to 9

//========================================================================================

if (0) {
    console.log("zero is truthy");
} else {
    console.log("zero is falsy");
}
```
---
## Logic And
| A | B | A && B |
| ----------- | ----------- | ----------- |
| true | true | true |
| treu | false | false |
| false | true | false |
| false | false | false |
---
## Logic Or
| A | B | A || B |
| ----------- | ----------- | ----------- |
| true | true | true |
| treu | false | true |
| false | true | true |
| false | false | false |


---
## short condition
JS also has a shortcut operator for writing quick conditionals
```
//syntax
//condition ? valueIfTrue : valueIfFalse;

// Real example :
let mood = forecast === "sunny" ? "happy" : "sad";
```
---
# Loop
The for statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement to be executed in the loop.
```
//syntax
//for (initialization; condition; afterthought)
//  statement
```
---
**for loops require us to:**
- declare & initialize a loop counter
- give a condition for the loop to keep running
- describe how to change (usually increment) the counter each time

```
for (let count = 0; count <= 100; count += 10) {
    console.log(count);
}

//=================================================
const numbers = [1,2,3];
for (let n of numbers) {
    console.log(n);
}
// output = 1 2 3
```





























**Answer to questions**
---
Q1
```
function checkSign(num) {
  return num == 0 ? 'zero' : num < 0 ? 'negative' : 'positive'
}

console.log(checkSign(20))
```
---
Q2
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
  if(strokes === 1) {
    return names[0]
  }
  else if (strokes <= par - 2) {
    return names[1]
  }
  else if (strokes == par - 1) {
    return names[2]
  }
  else if (strokes == par) {
    return names[3]
  }
  else if (strokes == par + 1) {
    return names[4]
  }
  else if (strokes == par + 2) {
    return names[5]
  }
  else if (strokes >= par + 3) {
    return names[6]
  }
  return "Change Me";
  // Only change code above this line
}

golfScore(5, 4);
```
---
Q3
```
const ratings = watchList.map(ele => ({
  title: ele.Title ,
  rating: ele.imdbRating
}));
```
---
Q4
```
const filteredList = watchList.filter(rating => rating.imdbRating > 8.0)
      .map(function(movies) {
        return { 
          title : movies.Title,
          rating : movies.imdbRating
        }
      }) 
```

