# Leetcode’s Two Sum Problem  Solution in (JavaScript)

> The Two Sum problem states that given an array of integers, return indices of the two numbers such that they add up to a specific target. We can’t use the same element twice.

```javascript
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```
# My Solution:
```javascript
function twoSum(nums, target) {
  const differences = {};
  for (let i = 0; i < nums.length; i++) {
    differences[target - nums[i]] = i;
  }

  for (let i = 0; i < nums.length; i++) {
    const difference = differences[nums[i]];
    if (difference !== undefined && difference !== i) {
      return [i, difference];
    }
  }
}
```

# Official Solution:

> Approach: One-pass Hash Table

# Algorithm

> It turns out we can do it in one-pass. While we are iterating and inserting elements into the hash table, we also look back to check if current element's complement already exists in the hash table. If it exists, we have found a solution and return the indices immediately.

# Complexity Analysis

> Time complexity: O(n)O(n)O(n). We traverse the list containing nnn elements only once. Each lookup in the table costs only O(1)O(1)O(1) time.

> Space complexity: O(n)O(n)O(n). The extra space required depends on the number of items stored in the hash table, which stores at most nnn elements.

# More

> Instead of looking for the sum of two numbers, which would be the obvious and intuitive approach, this approach takes each number, and looks for the number which when added to itself, would equalize the target (i.e the complement). For each number in the array, it creates this complement variable. If that complement number exists in the key:value object called numObj we created (i.e, it’s not undefined), then great! Return that number’s position in the object along with the position of number we’re looking at, and we’re done. If not, then add the number we’re looking at, and it’s position, in the numObj object.

> The twoSum() function is a common algorithm for finding two numbers in an array that add up to a target sum. The basic idea is to loop through the array and for each element, store the difference between the target sum and the current element in a hash table. Then, loop through the array again and check if the difference is in the hash table. If so, return the indices of the two numbers. Here is an example implementation of this algorithm:

> One algorithm that is less than O(n2) time complexity for this twoSum() function is the two-pass hash table algorithm. This algorithm works by first looping through the array and storing the difference between the target and the current element in a hash table. Then, loop through the array again and check if the difference is in the hash table. If so, return the indices of the two numbers. This algorithm has a time complexity of O(n) as it only requires one pass over the array. Here is an example implementation of this algorithm:


































