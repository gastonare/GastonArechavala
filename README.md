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


