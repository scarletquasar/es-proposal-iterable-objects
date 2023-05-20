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

for (const entry of obj) {
  console.log(`Key: ${entry[0]} | Value: ${entry[1]}`);
}
```

## Motivation

`Map` object is not used like the planned, the vast majority of javascript codebases only uses default objects (and makes operations using `Object.entries/keys/values` to deal with that data). The main reason is that `Map` api is not good to use, there is no support to use the spread operator in it and there is no way to create a new `Map` using an existing object (like `new Map({a: 1, b: 2})` - so, only slow/ugly ways to convert and use the data.
