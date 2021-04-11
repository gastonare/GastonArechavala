## What is a good code? It should be...
1. Readable -> Your code is generally clean. Others can understand your code
2. Scalable -> Based on Big O notation(How long an algorithm takes to run). When we increase the input of our code how much does the algorithm could slow down. We're focusing on how quickly our runtime grows. We simply do this by using the size of the input and compared to the number of operations that increase that's what scalability means. 

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
