# AlgoTips
Algorithmic Patterns and Tips


### Sliding Window

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


