## What is a good code? It should be...
- Readable -> Your code is generally clean. Others can understand your code
- Scalable -> Based on Big O notation(How long an algorithm takes to run). When we increase the input of our code how much does the algorithm could slow down. We're focusing on how quickly our runtime grows. We simply do this by using the size of the input and compared to the number of operations that increase that's what scalability means. 

## Big O notation

1. BIG O(N) -> linear time to execute an algorithm. (It depends on the number of inputs)

```
const nemo = ['nemo']; // if we 've an array of 1 element -> O(1)
const everyone = ['dory', 'bruce', 'marlin', 'nemo']; // if we 've an array of 4 elements -> O(4)
const large = new Array(10000).fill('nemo'); // if we 've an array of 10000 -> O(10000)

function findNemo(array) {
	for (let i = 0; i < array.length; i++){
		if(array[i] === 'nemo'){
			console.log('Found Nemo!');
		}
	}
}

```

2. BIG O(1) -> constant time to execute an algorithm (It doesn't depends on the number of inputs). For example we could 've a list of 10 boxes and we could only print the first box.

```

const boxes = [0,1,2,3,4,5];

function logFirstTwoBoxes(boxes){
	console.log(boxes[0]); // 0(1)
	console.log(boxes[1]); // 0(1)
}

logFirstTwoBoxes(boxes) // this would keep constant no matter if we 've 1 or 1000 elements 0(2)

```
3. BIG O(n!) Adding a nested loop for every input.

## Rules book

1) Worst Case (Think about in a big array with tons of numbers)

2) Remove constant O(2n) -> O(n)

3) Different terms for inputs

```

function compressBoxesTwice(boxes, boxes2)
{
	// code here
}

```

BIG O(a + b) It depends on the size collection. You could have 100 items on first collection and then just 1 on second collection. 

In another hand you could've an scenario with nested loops. For example:

```

//Log all pairs of array

const boxes = [1,2,3,4,5] // 1-2, 1-3, 1-4, 1-5, 2-1 2-2, 2-3, 2-4, 2-5

function logAllPariosOfArray(array){
	for(let i = 0; i < array.length; i++){
		for(let j = 0; j < array.length; j++){
			console.log(array[i], array[j])
		}
	}
}

```
BIG O (n^2)

4) Drop non dominant terms(We care about the most important term in this case)

```

function printAllNumbersThenAllPairSums(numbers) {
	
	console.log('these are the numbers:')
	numbers.forEach(function(number){
		console.log(number);
	}); // O(n)

	console.log('and these are their sums:')
	numbers.forEach(function(firstNumber){
		numbers.foreach(function(secondNUmber){
			console.log(firstNumber + secondNumber);
		});
	}); // O(n^2)
}

```

We skip the O(n) and we just keep 0(n^2) -> BIG O(n^2)

## Three pilars of code

- Readable -> Clean code that others can read. It's maintainable.
- Speed -> Based on time complexity. How long it takes the algorithm to run. It's efficient.
- Memory -> Based on space complexity. Memory required by the algorithm. 

## Space complexity (How much memory is being used)

What causes Space complexity?

- Variables
- Data structures
- Function call
- Allocations

Example 1
```
function booo(n) {
	for(let i = 0; i < n.length; i++) {
		console.log('boooo!');
	}

	booo([1,2,3,4,5]) // 0(1)
}
```
Space complexity -> O(1) Take a look to "let i = 0"

Example 2
```
function arrayOfHintTimes(n) {
	let hiArray = [];
	for(let i = 0; i < n; i++) {
		hiArray[i] = 'hi';
	}
	return hiArray;
}

arrayOfHintTimes(6) // O(n) ["hi","hi","hi", "hi"..]
```
Space complexity -> O(n) Because we're creating a new data structure and adding memory so each item is an additional memory space.

## How to solve problems?

1. Analytic skills : How can you think trough a problem and analyse things. When you are coding how is your thought process and how you go from not knowing the answer to solving the problem.

2. Coding skills : Is your code clean. Well organized. Readable.

3. Technical skills : Do you know the fundamentals?. Do you understand the pros and cons of different solutions.

4. Communication skills : Does your personality match the company's personality?. Can you communicate well with others with the team ? Most likely you won't be working by yourself

In order to solve coding coding problems we will need these data structures and algorithms.

Data structures

- Arrays		- Trees
- Stacks		- Tries
- Queues		- Graphs
- Linked Lists	- Hash Tables

Algorithms

- Sorting
- Dynamic Programming
- BFS + DFS (Searching)
- Recursion

1. When the interviewer says the question, write down the key points at the top. Make sure you have all the details

```
//Given 2 arrays, create a function that let's user know (true/false) whether these two arrays contain any common items:
//For example:

const array1 = ['a', 'b', 'c', 'x'];
const array2 = ['z', 'y', 'i'];
should return false;

const array1 = ['a', 'b', 'c', 'x'];
const array2 = ['z', 'y', 'x'];
should return true;
```

2. Make sure you double check: What are the inputs? What are the outputs?

```
2 parameters - arrays - no size limit
return true or false
```

3. What is the most important value of the problem? Do you have time, and space and memory,
etc.. What is the main goal?

```
How large this array's gonna get ? What's more important time complexity or space complexity ?
```

4. Start with naive brute force approach. Just speak about it

```
//You can start saying. This looks like a nested loop where we're comparing 'a' with 'z' and then with 'y'...
//Start with O(n^2)... Don't code about it. Tell why this approach isn't the best.

For example (1st approach)

function containsCommonItem(arr1, arr2) {
	for(let i=0; i < arr1.length; i++){
		for(let j=0; j<arr2.length; j++){
			if(arr1[i] === arr2[j]){
			  return true;
			}
		}
	}
	return false;
}

For example (2nd approach)

//Convert array into object.

// array1 ===> obj {
//  a: true,
//  b: true,
//  c: true,
//  x: true	
//}

```

5. Before you start coding, walk through your code and write down the steps you are going to
follow.

```
function containsCommonItem2(arr1, arr2){
	
	// loop through first array and create object
	//where properities === items in the array
	
	// loop through second array and check if item
	//in second array exists on created object,

	//O(a+b) -> One step + second step (two separate for loops)
}
```

6. Start actually writing your code now. And then check false inputs(For example repeated char, a number, an array, a null value, function call without 2nd array)
```
// loop through first array and create object where properities === items in the array
// can we assume always 2 parameters?

function containsCommonItem2(arr1, arr2){
	let map = {};
	for (let i=0; i < arr1.length; i++) {
		if(!map[arr1[i]]){ // check if the element exists, for example if 'a' not exists it will add an element
			const item = array1[i];
			map[item] = true; 
			// { a: true }
		}
	}
}

// loop through second array and check if item in second array exists on created object

containsCommonItem2(arr1, arr2)

for (let j=0; j < arr2.length; j++){
	if (map[arr2[j]]){
		return true;
	}
}
return false;
}

// O(a+b) Better Time Complexity
```

7. Finally talk to the interviewer where you would improve the code.

```
// For example I would google specific methods to see if I can clean up the code and make it readable.

function containsCommonItem3(arr1, arr2) {
	return arr1.some(item => arr2.includes(item))
}

```

8. How you would handle the problem if the whole input is too large to fit into memory, or if the input arrives as a stream.

```
// Evaluate the two functions. Pros and cons

function containsCommonItem(arr1, arr2) {
	for(let i=0; i < arr1.length; i++){
		for(let j=0; j<arr2.length; j++){
			if(arr1[i] === arr2[j]){
			  return true;
			}
		}
	}
	return false;
}

//0(a*b) Time complexity
//0(1) - Space complexity -> we're not creating any new variables. We 're just using the input arrays

function containsCommonItem2(arr1, arr2){
	let map = {};
	for (let i=0; i < arr1.length; i++) {
		if(!map[arr1[i]]){ // check if the element exists, for example if 'a' not exists it will add an element
			const item = array1[i];
			map[item] = true; 
			// { a: true }
		}
	}
}

//0(a+b) Time complexity
//0(a) Space complexity -> we're creating a new object and we 're adding the first array into an object which trakes up memory

// If we need to evaluate the solution based on Space Complexity we should choose the first option. But based on Time Complexity the second one.
```

9. Modularize your code from the very beginning

```
// Create a function mapArrayToObject(arr1)
// Create a function compareArrayToObject....
```
