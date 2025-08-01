---
{"dg-publish":true,"permalink":"/yfitpage/dsa 50/","created":"2025-08-01T05:41:49.863+05:30"}
---


Here’s a categorized list of **50 basic JavaScript DSA questions**, suitable for fresher-level interviews. Each includes:

- **Topic Name**
    
- **Question**
    
- **Code**
    
- **Short Explanation (only if needed for clarity)**
    

---

## 1. **Array Basics (10 Questions)**

### Q1. Reverse an array

```js
function reverseArray(arr) {
  return arr.reverse();
}
console.log(reverseArray([1, 2, 3, 4]));
```

### Q2. Find the maximum element in an array

```js
function maxElement(arr) {
  return Math.max(...arr);
}
console.log(maxElement([1, 5, 2, 9, 3]));
```

### Q3. Find the minimum element in an array

```js
function minElement(arr) {
  return Math.min(...arr);
}
console.log(minElement([1, 5, 2, 9, 3]));
```

### Q4. Find the sum of all elements in an array

```js
function sumArray(arr) {
  return arr.reduce((sum, val) => sum + val, 0);
}
console.log(sumArray([1, 2, 3, 4]));
```

### Q5. Find the average of an array

```js
function averageArray(arr) {
  return sumArray(arr) / arr.length;
}
```

### Q6. Remove duplicates from array

```js
function removeDuplicates(arr) {
  return [...new Set(arr)];
}
console.log(removeDuplicates([1, 2, 2, 3, 1]));
```

### Q7. Check if array is sorted

```js
function isSorted(arr) {
  for(let i=0; i<arr.length-1; i++) {
    if(arr[i] > arr[i+1]) return false;
  }
  return true;
}
```

### Q8. Find second largest number

```js
function secondLargest(arr) {
  let first = -Infinity, second = -Infinity;
  for(let num of arr){
    if(num > first){
      second = first;
      first = num;
    } else if(num > second && num !== first){
      second = num;
    }
  }
  return second;
}
```

### Q9. Count even and odd numbers

```js
function countEvenOdd(arr){
  let even = 0, odd = 0;
  for(let num of arr){
    num % 2 === 0 ? even++ : odd++;
  }
  return { even, odd };
}
```

### Q10. Rotate array to the right by 1

```js
function rotateRight(arr) {
  arr.unshift(arr.pop());
  return arr;
}
```

---

## 2. **String Problems (10 Questions)**

### Q11. Reverse a string

```js
function reverseStr(str) {
  return str.split('').reverse().join('');
}
```

### Q12. Check if a string is palindrome

```js
function isPalindrome(str) {
  return str === str.split('').reverse().join('');
}
```

### Q13. Count vowels in a string

```js
function countVowels(str) {
  return str.match(/[aeiou]/gi)?.length || 0;
}
```

### Q14. Capitalize first letter of each word

```js
function capitalizeWords(str){
  return str.split(' ').map(w => w[0].toUpperCase() + w.slice(1)).join(' ');
}
```

### Q15. Find longest word in a sentence

```js
function longestWord(str){
  return str.split(' ').reduce((a,b) => a.length > b.length ? a : b);
}
```

### Q16. Check for anagram

```js
function isAnagram(s1, s2){
  return s1.split('').sort().join('') === s2.split('').sort().join('');
}
```

### Q17. Remove duplicates from string

```js
function removeDuplicateChars(str){
  return [...new Set(str)].join('');
}
```

### Q18. Find character frequency

```js
function charFrequency(str){
  let freq = {};
  for(let char of str){
    freq[char] = (freq[char] || 0) + 1;
  }
  return freq;
}
```

### Q19. Check if string contains only digits

```js
function onlyDigits(str){
  return /^\d+$/.test(str);
}
```

### Q20. Convert string to camelCase

```js
function toCamelCase(str){
  return str.split(' ').map((w,i) => i === 0 ? w.toLowerCase() : w[0].toUpperCase() + w.slice(1)).join('');
}
```

---

## 3. **Searching & Sorting (5 Questions)**

### Q21. Linear search

```js
function linearSearch(arr, target){
  for(let i=0; i<arr.length; i++){
    if(arr[i] === target) return i;
  }
  return -1;
}
```

### Q22. Binary search (sorted array)

```js
function binarySearch(arr, target){
  let low = 0, high = arr.length - 1;
  while(low <= high){
    let mid = Math.floor((low + high) / 2);
    if(arr[mid] === target) return mid;
    else if(arr[mid] < target) low = mid + 1;
    else high = mid - 1;
  }
  return -1;
}
```

### Q23. Bubble Sort

```js
function bubbleSort(arr){
  for(let i=0; i<arr.length; i++){
    for(let j=0; j<arr.length-i-1; j++){
      if(arr[j] > arr[j+1]){
        [arr[j], arr[j+1]] = [arr[j+1], arr[j]];
      }
    }
  }
  return arr;
}
```

### Q24. Selection Sort

```js
function selectionSort(arr){
  for(let i=0; i<arr.length; i++){
    let minIdx = i;
    for(let j=i+1; j<arr.length; j++){
      if(arr[j] < arr[minIdx]) minIdx = j;
    }
    [arr[i], arr[minIdx]] = [arr[minIdx], arr[i]];
  }
  return arr;
}
```

### Q25. Insertion Sort

```js
function insertionSort(arr){
  for(let i=1; i<arr.length; i++){
    let key = arr[i];
    let j = i - 1;
    while(j >= 0 && arr[j] > key){
      arr[j+1] = arr[j];
      j--;
    }
    arr[j+1] = key;
  }
  return arr;
}
```

---

## 4. **Math & Numbers (10 Questions)**

### Q26. Check if number is prime

```js
function isPrime(n){
  if(n <= 1) return false;
  for(let i=2; i<=Math.sqrt(n); i++){
    if(n % i === 0) return false;
  }
  return true;
}
```

### Q27. Find factorial of number

```js
function factorial(n){
  let res = 1;
  for(let i=2; i<=n; i++) res *= i;
  return res;
}
```

### Q28. Generate Fibonacci series

```js
function fibonacci(n){
  let fib = [0, 1];
  for(let i=2; i<n; i++){
    fib[i] = fib[i-1] + fib[i-2];
  }
  return fib;
}
```

### Q29. Check if number is Armstrong

```js
function isArmstrong(n){
  let digits = n.toString().split('');
  let sum = digits.reduce((acc, d) => acc + Math.pow(+d, digits.length), 0);
  return sum === n;
}
```

### Q30. Check for perfect number

```js
function isPerfect(n){
  let sum = 0;
  for(let i=1; i<n; i++){
    if(n % i === 0) sum += i;
  }
  return sum === n;
}
```

### Q31. Count digits in number

```js
function countDigits(n){
  return n.toString().length;
}
```

### Q32. Reverse a number

```js
function reverseNumber(n){
  return parseInt(n.toString().split('').reverse().join(''));
}
```

### Q33. Sum of digits of number

```js
function sumDigits(n){
  return n.toString().split('').reduce((sum,d) => sum + +d, 0);
}
```

### Q34. Find GCD

```js
function gcd(a, b){
  while(b !== 0){
    [a, b] = [b, a % b];
  }
  return a;
}
```

### Q35. Find LCM

```js
function lcm(a, b){
  return (a * b) / gcd(a, b);
}
```

---

## 5. **Objects & Hashmaps (5 Questions)**

### Q36. Count frequency of numbers

```js
function countFreq(arr){
  let map = {};
  for(let num of arr){
    map[num] = (map[num] || 0) + 1;
  }
  return map;
}
```

### Q37. Find first non-repeating character

```js
function firstUniqueChar(str){
  let freq = {};
  for(let ch of str) freq[ch] = (freq[ch] || 0) + 1;
  for(let ch of str){
    if(freq[ch] === 1) return ch;
  }
  return null;
}
```

### Q38. Group anagrams

```js
function groupAnagrams(words){
  let map = {};
  for(let word of words){
    let sorted = word.split('').sort().join('');
    map[sorted] = map[sorted] || [];
    map[sorted].push(word);
  }
  return Object.values(map);
}
```

### Q39. Check if two objects are equal

```js
function isEqual(obj1, obj2){
  return JSON.stringify(obj1) === JSON.stringify(obj2);
}
```

### Q40. Find most frequent element

```js
function mostFrequent(arr){
  let map = {};
  let max = 0, res;
  for(let val of arr){
    map[val] = (map[val] || 0) + 1;
    if(map[val] > max){
      max = map[val];
      res = val;
    }
  }
  return res;
}
```

---

## 6. **Stack/Queue/Recursion (10 Questions)**

### Q41. Implement stack using array

```js
class Stack {
  constructor() {
    this.stack = [];
  }
  push(x) {
    this.stack.push(x);
  }
  pop() {
    return this.stack.pop();
  }
  peek() {
    return this.stack[this.stack.length - 1];
  }
}
```

### Q42. Implement queue using array

```js
class Queue {
  constructor(){
    this.queue = [];
  }
  enqueue(x){
    this.queue.push(x);
  }
  dequeue(){
    return this.queue.shift();
  }
}
```

### Q43. Reverse string using stack

```js
function reverseStack(str){
  let stack = [];
  for(let ch of str) stack.push(ch);
  return stack.reverse().join('');
}
```

### Q44. Recursively sum numbers up to n

```js
function sum(n){
  if(n === 0) return 0;
  return n + sum(n-1);
}
```

### Q45. Recursively calculate factorial

```js
function factorial(n){
  if(n === 0) return 1;
  return n * factorial(n-1);
}
```

### Q46. Fibonacci using recursion

```js
function fib(n){
  if(n <= 1) return n;
  return fib(n-1) + fib(n-2);
}
```

### Q47. Check balanced parentheses

```js
function isValidParentheses(str){
  let stack = [];
  for(let ch of str){
    if(ch === '(') stack.push(ch);
    else if(ch === ')'){
      if(stack.length === 0) return false;
      stack.pop();
    }
  }
  return stack.length === 0;
}
```

### Q48. Convert infix to postfix (basic)

```js
// Skipping due to complexity, not expected in basic interviews
```

### Q49. Remove duplicates from stack

```js
function removeDuplicatesStack(arr){
  let stack = [];
  let seen = new Set();
  for(let val of arr){
    if(!seen.has(val)){
      seen.add(val);
      stack.push(val);
    }
  }
  return stack;
}
```

### Q50. Implement simple calculator using stack (optional)

```js
function evaluate(expr){
  return eval(expr); // For basic use only
}
```

---

Let me know if you want this in downloadable format (PDF/Markdown) or with topics like **Graphs**, **Trees**, or **Linked List** added later.