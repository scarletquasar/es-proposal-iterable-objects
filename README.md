# es-proposal-iterable-objects
## Synopsis
With iterable objects, would be possible to easy iterate JavaScript default objects (`Object.prototype`) represented by `{}`. This change would be useful to avoid unnecessary casts and conversions between data (when trying to filter a `{a: 1, b: 2}` by value for example).

Examples:

```js
Object.prototype[Symbol.iterator] //ƒ entries() { [native code] }
Object.prototype.forEach //ƒ forEach() { [native code] }
Object.prototype.map //ƒ map() { [native code] }
Object.prototype.reduce //ƒ reduce() { [native code] }
Object.prototype.filter //ƒ filter() { [native code] }
Object.prototype.find //ƒ find() { [native code] }
...
```

```js
const obj = {
  a: 1,
  b: 2
}


```
