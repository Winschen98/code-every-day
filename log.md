## Day 0: March 6, 2021 

### Today's Progress: 
Continuing to do coding challenges on Leetcode.

### Thoughts: 
Still working my way up to more difficult problems and finding creative, more optimal approaches to every challenge. 

### Problem/Link to work: 
https://leetcode.com/problems/maximum-depth-of-binary-tree/

### Code
```
var maxDepth = function(root) {
    function dfs(node, height){
        if (!node) return height; 
        return Math.max(dfs(node.left, height + 1), dfs(node.right, height + 1))
    }
    return dfs(root, 0);
};
``` 


## Day 1: March 7, 2021 

### Today's Progress: 
Continuing to do work through coding challenges.

### Thoughts:
This was a quick morning exercise where I attempted to solve both problems within 15 minutes. while I did succeed, both problems can still use much improvement in terms of optimization.

### Problem/Link to work: 
1. Write a function called countTheBits that accepts a single numeric argument that will be an integer.
The function should return the number of bits set to 1 in the number's binary representation.

2. Write a function called addChecker that accepts two arguments.
The first argument is an array containing at least two integers. The integers in the array have been pre-sorted in ascending order.
The second argument is an integer.
The addChecker function should return true if there are two integers in the array of integers (first argument) that, when added together, equals the integer passed in as the second argument.
If there are no two integers in the array with a sum equal to the second argument, addChecker should return false.

### Code
```
function countTheBits(num){
  let bits = 0; 
  const binaryNum = num.toString(2); 
  for (let i=0; i < binaryNum.length; i++){
    if (binaryNum[i] == 1){
      bits ++; 
    }
  }
  return bits;
}

// countTheBits( 0 ) // => 0
// countTheBits( 256 ) // => 1
// countTheBits( 255 ) //=> 8
// countTheBits( 65535 ) //=> 16
```

```
function addChecker(arr, int){
  for (let i=0; i < arr.length; i++){
    for (let j=0; j < arr.length; j++){
      if (i != j){
        if (arr[i] + arr[j] == int){
          return true; 
        }
      }
    }
  }
  return false; 
}

addChecker( [1, 2], 3 ) // => true
addChecker( [-3, 2], 9 ) // => false
``` 


## Day 2: March 8, 2021 

### Today's Progress: 
Continuing to work on my first simple Android App with Kotlin and Android Studio. I've also picked up on an old Python project now that I am  revisiting Python. Lastly, as always, working through coding challenges everyday to keep the problem solving tooth sharp. 

### Thoughts: 
Working through coding challenges in python is a bit of challenge after having only done them in javascript. The largest challenge is finding if the same approach from javascript could be replicated in python, and if so, how.

### Problem/Link to work: 
cc_more_python ==> challenges.py

### Code
```
# Shortest Word

def shortest_word(s): 
    words = s.split()
    min_word = len(words[0])
    for i in words: 
        if len(i) < min_word: 
            min_word = len(i)
    return min_word

print(shortest_word("I don't think that word means what you think it means"))
# should return: 1
  

# Sum of Minimums
def sum_of_minimums(list):
    return (sum(min(row) for row in list))

my_list = [
    [1,2,3,4,5], # minimum value of row is 1
    [5,6,7,8,9], # minimum value of row is 5
    [20,21,34,56,100] # minimum value of row is 20
    ]

print(sum_of_minimums(my_list))
    # should return 26
```
