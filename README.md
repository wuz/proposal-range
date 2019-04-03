# ECMAScript Range Operator

## [Status](https://tc39.github.io/process-document/)

**Stage**: 0

**Authors**: Conlin Durbin (Lessonly, [@CallMeWuz](https://twitter.com/CallMeWuz)), Amelia Bellamy-Royds ([@AmeliasBrain](https://twitter.com/AmeliasBrain))

**Champions**:

## Introduction

This proposal is to add the ability to have have a native range functionality in Javascript. 

We have outlined to options in this proposal. The first is an optional property on the Iterable interface, which would be used to add specific implementations of range to Array, Set, TypedArray, and possibly more (like String and Number). The second is to add `range` function to each class that could be "ranged", allowing for methods like `Number.rangeInt8`, which would create a typed array.

This file includes casual, example-based discussion of the proposal. The next step will be adding an actual specification, which will happen in [CORE.md](/CORE.md).

This proposal draws heavily from corresponding features in many languages, like Python and Ruby, which all have a range operator or function.

Want to contribute/discuss this proposal? [Open an issue!](https://github.com/wuz/proposal-range-operator/issues)

## Motivating Examples

Each example is presented with how they would look for each implementation option. In most cases, they uses are very similar, but the background implementation is different.

Checking a number exists with in a range:
**Option 1**
```js
function inAllowedRange(number) {
    return Array.range(1, 10, 3).includes(number);
}
```

**Option 2**
```js
function inAllowedRange(number) {
    return Number.rangeInt8(1, 10, 3).includes(number);
}
```

Get all letters in a sequence:
**Option 1/Option 2**
```js
function atoz() {
    return String.range("a", "z");
}
```

Simpler ways to create empty states on iterated content.
**Option 1**
```js
function TodoApp() {
  return (
    Array.range(0, 3).map(() => 
        <TodoListItem />   
    )
  );
}
```

**Option 2**
```js
function TodoApp() {
  return (
    Number.rangeInt8(0, 3).map(() => 
        <TodoListItem />   
    )
  );
}
```

