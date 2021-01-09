

```js
let list = [];

let start = 0;
let end = 0;

for (end = 0; end < list.length; end++) {

  list[end]; // Do something with the right element just added to the window
    
  while (/* condition to move the start pointer */) {
    list[start]; // Do something with the left element that will be removed from the window
    start += 1;
  }
}
```
