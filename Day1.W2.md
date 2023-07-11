# JavaScript Principles
Execution context
- Thread of execution
- Memory

```javascript
const num = 3;
function multiplyBy2 (inputNumber){
const result = inputNumber*2;
return result;
}
const output = multiplyBy2(num);
const newOutput = multiplyBy2(10);

//*********** Memory ******************
// num : 3
// multyplayBy2 : f
// output : 6
// newOutput : 20
```
> output will join to block
## Global execution context
#### output = multiplyBy2(3)
|  | Local Memory |
| ----------- | -----------
|  | input num : 3 | 
|  | result : 6 |
|  |  |
| return result |  |

#### output = multiplyBy2(3)
|  | Local Memory |
| ----------- | -----------
|  | input num : 10 | 
|  | result : 20 |
|  |  |
| return result |  |

**Note : after return result the output will gose to function and  the output Evaluated to 6 , then 20**
> parameters , Arguments , Evaluate 

## Call Stack

- JavaScript keeps track of what function is currently running
- Run a function - add to call stack
- Finish running the function - JS removes it from call stack
- Whatever is top of the call stack
- that’s the function we’re currently running

---
# Function & Callbacks

```javascript
function copyArrayAndManipulate(array, instructions) {
 const output = [];
 for (let i = 0; i < array.length; i++) {
 output.push(instructions(array[i]));
 }
 return output;
}
function multiplyBy2(input) {return input * 2;}
const result = copyArrayAndManipulate([1, 2, 3], multiplyBy2);

// Higer order function is : copyArrayAndManipulate
// callback function is : multiplyBy2
```





































