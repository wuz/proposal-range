# ECMAScript Range Operator

## [Status](https://tc39.github.io/process-document/)

**Stage**: 0

**Author**: Conlin Durbin (Lessonly, [@CallMeWuz](https://twitter.com/CallMeWuz)), Amelia Bellamy-Royds ([@AmeliasBrain](https://twitter.com/AmeliasBrain))

**Champions**:

## Introduction

This proposal adds a range function and operator to the Iterable object.

This proposal is for both a `Iterable.range` method and an operator for future use.

This file includes casual, example-based discussion of the proposal. The next step will be adding an actual specification, which will happen in [CORE.md](/CORE.md).

This proposal draws heavily from corresponding features in many languages, like Python and Ruby, which all have a range operator or function.

Want to contribute/discuss this proposal? [Open an issue!](/issues)

## Motivating Examples

Checking a number exists with in a range:

```javascript
function inAllowedRange(number) {
    return Iterable.range(1, 10, 3).incudes(number);
}
```

Simpler ways to create empty states on iterated content.

```js
function TodoApp() {
  return (
    Iterable.range(0, 3).map(() => 
        <Todo />   
    )
  );
}
```

Using the range operator:

```javascript
for(let num of 0...10) {
    console.log(num);
}
```

Using the range operator with an array:

```js
function TodoApp() {
  return (
    [0...3].map(() => 
        <Todo />   
    )
  );
}
```

