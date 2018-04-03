# Recursive Big O

## Counting Sheep
```javascript
function countSheep(numSheep) {
  if (numSheep === 0) {
    return;
  }

  console.log(`${numSheep} - Another sheep jump over the fence`);
  countSheep(numSheep - 1);
}
```
O(n) This function runs n times recursively with an O(1) expression in each

## Array Double
```javascript
function doubleArray(arr) {
  if ( !arr.length ) {
    return [];
  }

  return [(arr[0] * 2), ...doubleArray(arr.slice(1))];
}
```
O(n) This function runs n times recursively with an O(1) expression in each

## nth Triangular Number
```javascript
function calculateTrianglularNamuber(num, prev=0) {
  if (num === 0) {
    return prev;
  }

  return calculateTrianglularNamuber(num - 1, num + prev);
}
```
O(n) This function runs n times recursively with two O(1) expressions in each

## String Splitter
```javascript
function stringSplit(str, predicate, word='') {
  if (str === '') {
    return [word];
  }

  if (predicate(str[str.length - 1])) {
    return [...stringSplit(str.slice(0, -1), predicate), word];
  }
  word = str[str.length - 1] + word;
  return stringSplit(str.slice(0, -1), predicate, word);
}
```
O(n) This function runs n times recursively with two O(1) expressions in each

## Binary Representation
```javascript
function binary(num, result='') {
  if (num === 0) {
    return result;
  }

  result = (num % 2).toString() + result;
  return binary(Math.floor(num / 2), result);
}
```
O(log n) This function runs log n times recursively because the recursive call is divided by two each recursion with O(1) expressions in each

## Factorial
```javascript
function factorial(num, result=1) {
  if (num < 1) { 
    return result;
  }

  return factorial(num - 1, result * num);
}
```
O(n) This function runs n times recursively with two O(1) expressions in each

## Fibonacci
```javascript
function fib(num, result=[1, 1]) {
  if (num === 2) {
    return result;
  }

  result.push(result[result.length - 1] + result[result.length - 2]);
  return fib(num - 1, result);
}
```
O(n) This function runs n times recursively with O(1) expressions in each

## Anagrams
```javascript
function anagram(str, result=[], prefix='') {
  if (str.length === 0) {
    result.push(prefix);
    return result;
  }

  for ( let i = 0; i < str.length; i++ ) {
    anagram((str.slice(0, i) + str.slice(i+1)), result, (prefix + str[i]));
  }

  return result;
}
```
O(n!) The top level for loop will recursively call the function with a value of n - 1 and will continue to call it until n = 0 so it has O(n!)

## Animal Hierarchy
```javascript
function traverse(animalHierarchy, parent) {
    let node = {};
    animalHierarchy.filter(item => item.parent === parent)
                   .forEach(item => node[item.id] = traverse(animalHierarchy, item.id));
    return node;  
}
```
O(n) This function runs n times recursively with expressions to work through the object one time

## Org Chart
```javascript
function traverse(node, indent=0) {
  for (const key in node) {
    console.log(' '.repeat(indent), key);
    traverse(node[key], indent + 2);
  }
}
```
O(n) This function runs n times recursively with expressions to work through the object one time