# Must-Know-JS-Snippets
Js Snippets That Can Save You Someday xD....

## all

This snippet returns true if the predicate function returns true for all elements in a collection and false otherwise. You can omit the second argument 'fn' if you want to use Boolean as a default value.
```js
const all = (arr, fn = Boolean) => arr.every(fn);

all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```

## arrayToCSV

This snippet converts the elements to strings with comma-separated values.
```js
const arrayToCSV = (arr, delimiter = ',') =>
  arr.map(v => v.map(x => `"${x}"`).join(delimiter)).join('\n');

arrayToCSV([['a', 'b'], ['c', 'd']]); // '"a","b"\n"c","d"'
arrayToCSV([['a', 'b'], ['c', 'd']], ';'); // '"a";"b"\n"c";"d"'
```
## arrayToHtmlList

This snippet converts the elements of an array into list tags and appends them to the list of the given ID.
```js
const arrayToHtmlList = (arr, listID) =>
  (el => (
    (el = document.querySelector('#' + listID)),
    (el.innerHTML += arr.map(item => `<li>${item}</li>`).join(''))
  ))();

arrayToHtmlList(['item 1', 'item 2'], 'myListID');
```

## bifurcate

This snippet splits values into two groups and then puts a truthy element of filter in the first group, and in the second group otherwise.

You can use Array.prototype.reduce()and Array.prototype.push()to add elements to groups based on filter.
```js
const bifurcate = (arr, filter) =>
  arr.reduce((acc, val, i) => (acc[filter[i] ? 0 : 1].push(val), acc), [[], []]);
bifurcate(['beep', 'boop', 'foo', 'bar'], [true, true, false, true]); 
// [ ['beep', 'boop', 'bar'], ['foo'] ]
```

## byteSize

This snippet returns the length of a string in bytes.
```js
const byteSize = str => new Blob([str]).size;

byteSize('😀'); // 4
byteSize('Hello World'); // 11
```

## capitalize

This snippet capitalizes the first letter of a string.
```js
const capitalize = ([first, ...rest]) =>
  first.toUpperCase() + rest.join('');

capitalize('fooBar'); // 'FooBar'
```

## countOccurrences

This snippet counts the occurrences of a value in an array.
```js
const countOccurrences = (arr, val) => arr.reduce((a, v) => (v === val ? a + 1 : a), 0);
countOccurrences([1, 1, 2, 1, 2, 3], 1); // 3
```
