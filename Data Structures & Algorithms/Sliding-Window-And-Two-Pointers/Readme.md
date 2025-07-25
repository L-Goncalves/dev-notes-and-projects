# Sliding Window and Two Pointers

This folder covers two powerful problem-solving techniques.

Topics include:

- Sliding window approach for subarray and substring problems
- Two pointer technique for searching and sorting problems
- Common patterns and problem examples
- Code demonstrations and optimization tips

### Why Do We Need Two Pointers (`left` and `right`) in the Sliding Window?

Imagine you are looking at a portion of a string, a **window**, that can grow or shrink dynamically.

* Right pointer is used to expand the window by moving forward through the string and including more characters
* The **left pointer** is used to **shrink** the window from the left side, removing characters when a problem arises in this case, when a character repeats inside the window.

#### Why not just one pointer?

With a single pointer you can only move forward and backward:

```js
// Index goes forward ->
[1,2,3,4,5]
```

```js
// Index goes backwards <-
[1,2,3,4,5]
```


Example of a solved Leetcode Problem:


```js
function lengthOfLongestSubstring(s) {
  let left = 0;
  let maxLength = 0;
  const seen = new Set();

  for (let right = 0; right < s.length; right++) {
    while (seen.has(s[right])) {
      seen.delete(s[left]);
      left++;
    }
    seen.add(s[right]);
    maxLength = Math.max(maxLength, right - left + 1);
  }

  return maxLength;
}

```

1. We need a "hashset" to keep track of duplicates.
2. Left starts at 0 just like right = 0

When it has been seen ONCE, it deleles the first left item and moves the window.

Example:

Input: "abca"

The for loop goes from 0 (a), 1 (b), 2 (c), 3 (a) when RIGHT is 3 we delete the first item because it has been repeated.

Example 2:

Input: "abcb"

The for loop goes from 0 (a), 1 (b), 2 (c), 3 (b) when RIGHT is 3 we MOVE the left pointer and delete the Item, just like a "subarray"

When that happens this happens:

b (index 3) is found:

Delete index 0 Move Left for next deletition, is still being duplicate?

Delete Index 1 Move left for next deletition, is still being duplicate? If not we add to seen because it was seen the first time.


### More on Sliding Window:


How to recognize a problem with sliding window?
A: Most time we can get it by "when the solution to the problem is" a subarray or size of subarray that fills some condition.


