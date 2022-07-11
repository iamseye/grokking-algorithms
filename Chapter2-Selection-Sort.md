# Chapter 2 - Selection Sort

### Linked lists

- The item stores the address of the next item in the list.
- with a linked list, you never have to move your items
- The elements aren’t next to each other, so you can’t instantly calculate the position of the fifth element in memory.

### Arrays

- Great if you want to read random elements. cuz you can look up any element in your array instantly.

|  | Arrays | Linked lists |
| --- | --- | --- |
| Reading | O(1) | O(n) |
| inserting | O(n) | O(1) (if not count search) |
| Deletion | O(n) | O(1) (if not count search) |

### Selection sort

Suppose you have a bunch of music on your computer. For each artist, you have a play count. and you want to sort this list from most to least played.

1. Go through the list, find the most-played, and add it to the new list 
2. Do it again to find the next-most-played, and add it to the new list
3. Do it until the list is empty.

To go throuh each item, take O(n). doing it n times. so the time complexity is **O(n^2)**

- selection sort is not very fast.

```jsx
// time: O(n^2n => n^2)
function selectionSort(array) {
  const newArray = [];

  while(array.length) {
	  const smallestIndex = findSmallestIndex(array);
    newArray.push(array[smallestIndex]);
	  array.splice(smallestIndex, 1);     
  }
	return newArray;
}

function findSmallestIndex(array) {
  let min = array[0];
  let minIndex = 0;

  for(let i =0; i<array.length;i++) {
	  if(array[i]<min) {
		min = array[i];
        minIndex = i;
	  }
  }

	return minIndex;
}
```

- Recap
    - With array, all your elements are stored right next to each other
    - With a list, elements are strewn all over, and one element stores the address of the next one.
    - Arrays allow fast read
    - Linked lists allow fast insert and delete