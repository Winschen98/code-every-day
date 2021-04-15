## Day 0/1: March 6, 2021 

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


## Day 2: March 7, 2021 

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


## Day 3: March 8, 2021 

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


## Day 4: March 9, 2021 

### Today's Progress: 
Working through practice problems on leetcode. Practicing white boarding ability by working through problems on paper. 

### Thoughts: 
Still need to work on 

### Problem/Link to work: 
https://leetcode.com/problems/maximum-depth-of-binary-tree/

### Code
```
var islandPerimeter = function(grid) {
    const rows = grid.length; 
    const columns = grid[0].length; 
    let perimeter = 0; 
    for (let i=0; i < rows; i++){
        for (let j=0; j < columns; j++){
            if (grid[i][j] === 1){
                perimeter += 4; 
                if (grid[i][j-1] === 1){
                    perimeter --; 
                }
                if (grid[i][j+1] === 1){
                    perimeter --;
                }
                if (grid[i - 1] && grid[i - 1][j] === 1){
                    perimeter --; 
                }
                if (grid[i + 1] && grid[i + 1][j] === 1){
                    perimeter --;
                }
            }
        }   
    }
    return perimeter; 
};
``` 


## Day 5 & Day 6: March 10 & 11, 2021 

### Today's Progress: 
Learning Android mobile development with Android Studio and Kotlin. Was able to complete the MVP of the app with basic add/delete funcitonality and displaying lists. 

### Thoughts: 
With time the structure of Android Studio began to resemble other code editors such as VSCode with which I have more familiarity. The biggest hurdles were getting aquainted with the syntax of Kotlin code and then to become more comfortable with the nuances of working in Android Studio. There were many dependencies and extensions that I had to become familiarized with in order for my application to run correctly. Additionally, learning to use constraint layouts versus CSS was another challenge. 

### Problem/Link to work: 
Code in "pocket-cart" repo

### Code
```
see full source code in "pocket-cart" repo
``` 


## Day 7: March 12, 2021 

### Today's Progress: 
Continuing to learn Django and Kotlin. Continuing to practice leetcode questions and honing my problem solving skills. 

### Thoughts: 
Learning Kotlin has been more enjoyable and less challenging than I initially expected. Not to confuse with saying that it is easy, but overall I feel that after having multiple languages under my belt, learning Kotlin has been much more of a smooth transition and finding out nuances to each language is very enjoyable. Leetcode problems are engaging as well, especially after finding out the multitude of approaches that can be taken with any given problem. Some individuals find amazingly creative approaches. 

### Problem/Link to work: 
https://leetcode.com/problems/middle-of-the-linked-list/

### Code
```
var middleNode = function(head) {
    let length = 1;
    let currNode = head; 
    while (currNode.next){
        currNode = currNode.next; 
        length ++; 
    }
    
    const mid = Math.floor(length/2);  
    let currIdx = 0; 
    while (currIdx != mid){
        head = head.next; 
        currIdx ++; 
    }
    return head; 
};
``` 



## Day 8: March 13, 2021 

### Today's Progress: 
Continuing to practice setting up a Django backend, both the monolithic framework and with django REST framework.

### Thoughts: 
Compared to the MERN stack, I find django to be far more intuitive and better for handling a quick CRUD setup. 

### Problem/Link to work: 
none

### Code
```
No code to provide today
``` 


## Day 9: March 14, 2021 

### Today's Progress: 
Continuing to practice leetcode problems. practicing implentations of different data structures. 

### Thoughts: 
I remember intitially learning recursions and finding them incredibly complicated to comprehend. but by deconstructing the logic, it has become easier appraoch problems from a recursive perspective. 

### Problem/Link to work: 
https://leetcode.com/problems/n-ary-tree-preorder-traversal/

### Code
```
var preorder = function(root) {
    // traversal function that recursively traverses node.children
    // on each recursive call push the node.val into an array
    // *for preorder, the node should be pushed prior to traversal 
    
    let res = []; 
    function traverse(node){
        if (!node) return;
        res.push(node.val); 
        for (let child of node.children){
            traverse(child);
        }
    }
    traverse(root)
    return res
};
```



## Day 10: March 15, 2021 

### Today's Progress: 
Continuing to practice leetcode problems. practicing implentations of different data structures. Todays focus was to get a better grip of breaking down a problem and conveying ideas through pseudocode before code implementation. 

### Thoughts: 
It is still very much a challenge to very cohesively break down a problem into good pseudocode. One struggle I have is processing too many different approaches initially and getting caught up with efficiency from the get go. I think its much better to verbalize that you're willing to take a initial brute force approach and optimize the code at a further stage. 

### Problem/Link to work: 
https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers/

### Code
```
var sumRootToLeaf = function(root) {
    // each path from root to leaf represents a binary number, each node being a digit
    // make all possible traversals from root to leaf and track the binary num it produces
    // return the sum of all binary nums that are recorded
    
    // can use a recursive approach
    // if the node passed into current call does not exist return (base case)
    // for each call we need to add the current node.val to a running sum
    // if its a leaf node then add the sum to our final returned result 
    // recursive call on node.left and node.right, pass along the running sum as well 
    // since 0s and 1s are strings, we can pass along running sum as a string and then parseint after
    // when all recursive calls are done return the result/total sum. 
    
    
    let sum = 0; 
    
    function DFS(node, runningSum){   
        if (!node) return 
        runningSum += node.val; 
        if (!node.left && !node.right){
            sum += parseInt(runningSum, 2);
            return; 
        }
        DFS(node.left, runningSum); 
        DFS(node.right, runningSum); 
    }
    DFS(root, '');
    return sum; 
};
```