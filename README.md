# JavaScript Algorithms (Sorted by Popularity)

This list showcases some of the most popular JavaScript algorithms, from simple string manipulations to classic recursive solutions and efficient searching techniques. Each snippet demonstrates a fundamental concept often encountered in coding interviews and real-world development.

> **Note:** Popularity is based on common interview topics, educational resources, and usage in developer communities.

## 1. Reverse a String

```js
function reverseString(str) {
  return str.split("").reverse().join("");
}

console.log(reverseString("hello")); // Output: "olleh"
```

**Explanation**: Reverses the characters in a string by splitting, reversing, and joining them back together.

## 2. Palindrome Check

```js
function isPalindrome(str) {
  return str === str.split("").reverse().join("");
}

console.log(isPalindrome("racecar")); // Output: true
```

**Explanation**: Determines if a string reads the same backward as forward using string reversal.

## 3. Binary Search

```js
function binarySearch(arr, target) {
  let left = 0,
      right = arr.length - 1;
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;
    if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}

console.log(binarySearch([1, 2, 3, 4, 5], 4)); // Output: 3
```

**Explanation**: Searches for a target in a sorted array using a divide-and-conquer approach (Time complexity: O(log n)).

## 4. Fibonacci Sequence (Recursive)

```js
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6)); // Output: 8
```

**Explanation**: Generates the nth Fibonacci number recursively by summing the two preceding numbers.

⚠️ **Note**: This approach has exponential time complexity O(2^n) and is inefficient for large inputs. Use memoization or iteration for better performance.

## 5. Factorial of a Number

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

**Explanation**: Calculates the factorial of a number recursively by multiplying it with decremented values.

## 6. Prime Number Check

```js
function isPrime(num) {
  if (num <= 1) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}

console.log(isPrime(7)); // Output: true
```

**Explanation**: Checks if a number is prime by testing divisibility up to its square root.

## 7. Find Maximum in Array

```js
function findMax(arr) {
  return Math.max(...arr);
}

console.log(findMax([1, 2, 3, 4, 5])); // Output: 5
```

**Explanation**: Finds the largest number in an array using the `Math.max` function and the spread operator.

## 8. Merge Two Sorted Arrays

```js
function mergeSortedArrays(arr1, arr2) {
  let merged = [], i = 0, j = 0;
  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      merged.push(arr1[i]);
      i++;
    } else {
      merged.push(arr2[j]);
      j++;
    }
  }
  return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
}

console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // Output: [1, 2, 3, 4, 5, 6]
```

**Explanation**: Merges two sorted arrays into one sorted array by comparing elements sequentially.

## 9. Bubble Sort

```js
function bubbleSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}

console.log(bubbleSort([5, 3, 8, 4, 2])); // Output: [2, 3, 4, 5, 8]
```

**Explanation**: Sorts an array by repeatedly swapping adjacent elements if they are in the wrong order (Time complexity: O(n²)).

## 10. Find the GCD (Greatest Common Divisor)

```js
function gcd(a, b) {
  if (b === 0) return a;
  return gcd(b, a % b);
}

console.log(gcd(48, 18)); // Output: 6
```

**Explanation**: Uses the Euclidean algorithm to compute the greatest common divisor of two numbers (Time complexity: O(log min(a, b))).
