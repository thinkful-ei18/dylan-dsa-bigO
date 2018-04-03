# Big O

## Even or Odd
```javascript
function isEven(value){
  if (value % 2 == 0){
    return true;
  }
  else
    return false;
} 
```
O(1) because no matter what input there is only one expression evaluated: `num % 2`

## Are You Here
```javascript
function areYouHere(arr1, arr2) {
    for (let i=0; i<arr1.length; i++) {
        const el1 = arr1[i];
        for (let j=0; j<arr2.length; j++) {
            const el2 = arr2[j];
            if (el1 === el2) return true;
        }
    }
    return false;
}
```
O(n^2) a for loop nested inside a for loop means that there is an n * n relationship

## Doubler
```javascript
function doubleArrayValues(array) {
    for (let i=0; i<array.length; i++) {
        array[i] *= 2;
    }
    return array;
}
```
O(n) There is one expression evaluated on each item in the array

## Naive Search
```javascript
function naiveSearch(array, item) {
    for (let i=0; i<array.length; i++) {
        if (array[i] === item) {
            return i;
        }
    }
}
```
O(n) is the worst case here, this function iterates over an array until it finds a specific value

## Creating Pairs
```javascript
function createPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for(let j = i+1; j < arr.length; j++) {
            console.log(arr[i] + ", " +  arr[j] );
        }
    }
}
```
O(n^2) Nested for loops means n * n

## Computing Fibonaccis
```javascript
function generateFib(num) {
  let result = [];
  for (let i = 1; i <= num; i++) {

    // we're adding the first item
    // to the result list, append the
    // number 0 to results
    if (i === 1) {
      result.push(0);
    }
    // ...and if it's the second item
    // append 1
    else if (i == 2) {
      result.push(1);
    }

    // otherwise, sum the two previous result items, and append that value to results.
    else {
      result.push(result[i - 2] + result[i - 3]);
    }
  }
  // once the for loop finishes
  // we return `result`.
  return result;
}
```
O(n) this iterates from 0 to the input and performs one expression per operation

## Efficient Search
```javascript
function efficientSearch(array, item) {
    let minIndex = 0;
    let maxIndex = array.length - 1;
    let currentIndex;
    let currentElement;

    while (minIndex <= maxIndex) {
        currentIndex = Math.floor((minIndex + maxIndex) / 2);
        currentElement = array[currentIndex];

        if (currentElement < item) {
            minIndex = currentIndex + 1;
        }
        else if (currentElement > item) {
            maxIndex = currentIndex - 1;
        }
        else {
            return currentIndex;
        }
    }
    return -1;
}
```
O(log n) Halves the search size every iteration assuming the array is sorted

## Random Element
```javascript
function findRandomElement(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
}
```
O(1) This will run one expression no matter the input array size

## Is It Prime?
```javascript
function isPrime(n) {
    // if n is less than 2 or a decimal, it's not prime
    if (n < 2 || n % 1 != 0) {
        return false;
    }
    // otherwise, check if `n` is divisible by any integer
    // between 2 and n.
    for (let i = 2; i < n; ++i) {
        if (n % i == 0) return false;
    }
    return true;
}
```
O(n) Although this has a O(1) best case, the worst case is O(n) because there is one expression run on each iteration