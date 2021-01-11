# AlgoTips
Algorithmic Patterns and Tips


### Sliding Window (two pointers move from the start of the list)

```js
function doSomething(list) {
  let start = 0;
  let end = 0;

  for (end = 0; end < list.length; end++) {

    list[end]; // Do something with the right element just added to the window

    while (/* condition to move the start pointer */) {
      list[start]; // Do something with the left element that will be removed from the window
      start += 1;
    }
  }

  ...
}
```

### In-place Reversal of a Linked List

```js
function reverseList(head) {

  let previous = null;
  let current = head;
  let next = null;

  while(current !== null) 
    next = current.next;
    current.next = previous;
    previous = current;
    current = next;
  }

  head = previous;

  ...
}
```

or if only part of the linked list needs to be reverted:

```js
function reverseSubList(head) {
  let dummy = Node(head);

  let previous = dummy;
  let current = head;
  let next = null;

  while(...) { // Skip some of element until current is not start of sublist
    previous = current;
    current = current.next;
  }
  
  let before_sublist = previous;
  let first_of_sublist = current;

  while(current !== null) 
    next = current.next;
    current.next = previous;
    previous = current;
    current = next;
  }

  before_sublist.next = previous;
  first_sublist.next = current;

  head = previous;
}
```

### Tree Breadth First Search

```js
class Node {
  value;
  left;
  right; 
};

function traverseTree(root) {
  let queue = [];

  queue.push(root);

  while (queue.length > 0) {
    let levelSize = queue.length;
    
    // Walk on level
    while (levelSize--) {
      let node = queue.shift();

      if(node.left !== null) {
        queue.push(node.left);
      }

      if(node.right !== null) {
        queue.push(node.right);
      }
    }

    // Move to the mext level
  }
};

```

### Tree Depth First Search

```js
function traverseTreeRecursive(node) {
  // Leaf
  if (node === null) {
    return false;
  }
  
  let leftResult = traverseTreeRecursive(node.left);
  let rightResult = traverseTreeRecursive(node.right);
  
  // Do something with leftResult and rightResult
  let result = ...;
  
  return result;
}
```

### Cyclic Sort
```js
function sortArray(nums) {
  let i = 0;
  while (i < nums.length) {
    j = nums[i]; // Sometimes j = nums[i] - 1;
    if (nums[i] !== nums[j]) {
      let tmp = nums[i];
      nums[i] = nums[j];
      nums[j] = tmp;
    } else {
      i += 1;
    }
  }
```

or if the list contains missing numbers

```js
function sortArray(nums) {
  let i = 0;
  while (i < nums.length) {
    j = nums[i]; // Sometimes j = nums[i] - 1;
    if (nums[i] !== nums[j] && nums[i] < nums.length) { // Additional check here
      let tmp = nums[i];
      nums[i] = nums[j];
      nums[j] = tmp;
    } else {
      i += 1;
    }
  }
```
