# Iterative Big O

## Counting Sheep
```javascript
function countSheepIt(num) {
  while (num > 0) {
    console.log(`${num} - Another sheep jumps the fence`);
    num--;
  }
}
```
O(n) This function iterates n times

## Double Array
```js
function doubleIt(arr) {
  let result = [];
  for ( let i = 0; i < arr.length; i++ ) {
    result[i] = arr[i] * 2;
  } 
  return result;
}
```
O(n) This function iterates n times

## Reverse
```js
function reverseIt(str) {
  let reversed = '';
  for ( let i = str.length - 1; i >= 0; i-- ) {
    reversed += str[i];
  }
  return reversed;
}
```
O(n) This function iterates n times

## Triangular Number 
```js
function triangleIt(num) {
  let total = 0;
  for ( let i = 0; i <= num; i++) {
    total += i;
  }
  return total;
}
```
O(n) This function iterates n times

## Split
```js
function splitIt(str, predicate) {
  const result = [];
  let loop = true;
  while (loop) {
    let index = str.indexOf(predicate);
    if ( index === -1 ) break;
    result.push(str.slice(0, index));
    str = str.slice(index + predicate.length);
  }
  result.push(str);
  return result;
}
```
O(n) This iterates through the entire string input once 

## Binary
```js
function binaryIt(num) {
  let result = '';
  while ( num > 0 ) {
    result = (num % 2).toString() + result;
    num = Math.floor(num / 2);
  }
  return result;
}
```
O(log n) This iterates but each iteration divides by 2 instead of decrementing so it is log n

## Factorial
```js
function factorialIt(num) {
  let result = 1;
  for (let i = 2; i <= num; i++ ) {
    result *= i;
  }
  return result;
}
```
O(n) This function iterates n times

## Fibonacci
```js
function fibIt(num) {
  let result = [];
  for ( let i = 0; i <= num; i++ ) {
    if ( i === 0 ) {
      result.push(0);
    } else if ( i === 1) {
      result.push(1);
    } else {
      result.push(result[i - 2] + result[i - 1]);
    }
  }
  return result;
}
```
O(n) This function iterates n times