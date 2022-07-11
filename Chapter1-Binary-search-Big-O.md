# Chapter 1 - Binary search / Big O notation

### Simple search

- Iterate through the entire array to find the item you are looking.
- Simple search will take n steps (linear).

### Binary search

- With binary search, the input must be a sorted list of elements. You guess the middle number and eliminate half the remaining numbers every time.
    - In general, for any list of n, binary search will take log n steps.

### Logarithms

- $log_2 8$ is asking how many 2s do we multiply to get 8? The answer is 3.
- When you search for an element in a list with 8 numbers:
    - using simple search, you have to check 8 numbers at most, O(n) = 8
    - using binary search, you have to check 3 numbers at most, O(log n) = 3

### Big O notation

- Big O notation tells you:
    - the number of operations it takes to complete a task
    - how fast the algorithm grows
- Algorithm speed isn’t measured in seconds, but in growth of the number of operations.
    - We talk about how quickly the runtime of an algorithm increases as the size of the input increases.
- For example, run times for simple search and binary search don’t grow at the same rate
    
    
    | # items (input) | Simple search | Binary search | How much faster? |
    | --- | --- | --- | --- |
    | 100 | 100 | 7 | 14 times |
    | 10,000 | 10,000 | 14 | 700 times |
    | 1,000,000 | 1,000,000 | 20 | 50,000 times |
    - As the number of items increases, binary search takes a lot less time than simple search.
    - That is why it’s not enough to know how long an algorithm takes to run - you need to know how the running time increases as the list size increases.
- In a simple search, you might find what you were looking for instantly if it is the first item in the list. But, we say it takes O(n) time because Big O notation is about the worst-case scenario.
    - Along with the worst-case run time, it’s also important to look at the average-case runtime.

### Common Big O run times

| Big O | Example |
| --- | --- |
| O(log n) | Binary search |
| O(n) | Simple search |
| O(n log n) | Quicksort |
| O(n^2) | Selection sort |
| O(n!) | Traveling salesman |

### Recap

- O(log n) is faster than O(n). It gets a lot faster once the list of items you’re searching through grows.
- Algorithm speed is measured in growth of the number of operations as input grows.

### Neet codes

- Binary search
    
    ```jsx
    function binarySearch(nums, target) {
    	let left = 0;
    	let right = nums.length - 1;
    
    	while (left < right) {
    		let mid = Math.floor((left + right) / 2);
    
    		if (target === nums[mid]) {
    			return mid;
    		} else if (target < nums[mid]) {
    			right = mid - 1;
    		} else {
    			left = mid + 1;
    		}
    	}
    
    	return null;
    }
    ```