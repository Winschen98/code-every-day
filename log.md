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

## Day 11: March 17, 2021 

### Today's Progress: 
Refreshing on data science concepts and practicing Django in preparation for my next project. I am quite confident that in my next project I would like to deploy a machine learning model. Learning webscraping with Ruby and how to train classification/regression models on collected data. 

### Thoughts: 
Data Science was one of the initial topics that drew me into the world of programming. I was completely fascinated by the ability/potential of AI to entirely reinvent the way our world operates. I still strongly believe that there is tremendous good that can be provided through our application of machine learning models. I was previously intimidated by the complexity of many data science concepts, but now feel confident in being able to gradually absorb many of theses concepts and apply them at a smaller scale.

### Problem/Link to work: 
https://leetcode.com/problems/remove-duplicates-from-sorted-list/

### Code
```
var deleteDuplicates = function(head) {
    let current = head;
    while (current && current.next) {
        if (current.val == current.next.val){
            current.next = current.next.next; 
        } else {
            current = current.next;
        }
    }
    return head;
};
```



## Day 12: March 17, 2021 

### Today's Progress: 
Gaining more familiarity with different data structures, brushing up on simple linked list problems. 

### Thoughts: 
A fairly simple linked list problem. Can likely optimize so that the entire linked list does not need to be traversed.  

### Problem/Link to work: 
https://leetcode.com/problems/remove-duplicates-from-sorted-list/

### Code
```
var deleteDuplicates = function(head) {
    let current = head;
    while (current && current.next) {
        if (current.val == current.next.val){
            current.next = current.next.next; 
        } else {
            current = current.next;
        }
    }
    return head;
};
```

## Day 13: March 18, 2021 

### Today's Progress: 
Continuing to practice leetcode problems and particularly further learning to break down the logic that goes into writing recusrive algorithms. I had to seek out hints for this problem in order to arrive at my provided solution.  

### Thoughts: 
I found this problem to incredibly challenging. Despite being a spin on a previous quesiton I completed, being the maxDepth of a binary tree, this problem had many more edge cases to consider. 

### Problem/Link to work: 
https://leetcode.com/problems/diameter-of-binary-tree/

### Code
```
var diameterOfBinaryTree = function(root) {
    // problem 
    // find the greatest distance between any two nodes on the binary tree
    // return the number of edges between the two nodes 
    
    // recursive approach 
    // the longest 'diameter' seems to always be the: 
    // sum between the max depth of the right and left subtree (of root)
    // can use dfs to traverse the height of left and right 
    // use variables to keep track of the current max height of each subtree
    
    let maxDepth = 0;
    function DFS(node){
        if (!node) return 0; 
        let left = DFS(node.left); 
        let right = DFS(node.right);
        maxDepth = Math.max(maxDepth, left + right); 
        return Math.max(left, right) + 1; 
    }
    DFS(root); 
    return maxDepth; 
};
```

## Day 14: March 19, 2021 

### Today's Progress: 
Began working on my ecommerce project using react and django. Began structuring the frontend of the project, revisiting major React concepts. Continuing to practice leetcode problems as well. 

### Thoughts: 
Typically prior to starting a project I prefer to scaffold out my ideas and general strcuture of my project. I find that by mentally creating a roadmap for a project, there tends to be less problems that arise down the line. One problem that I have had with previous projects is by building too fast early without consideration for how the project will scale at a later stage. 

### Problem/Link to work: 
code in fan-apparel repository.

### Code
```
Code in fan-apparel repository. 
```


## Day 15: March 20, 2021 

### Today's Progress: 
Continuing to practice leetcode problems while working on my project. 

### Thoughts: 
There are times, like today, when solutions that would typically come naturally are not quite as obvious. The problem solved below is one such scenario. In such a case, it is best to practice a brute force apprach and simply focus on arriving at a solution, even if less than optimal. Today I was able to get good practice in that regard. 

### Problem/Link to work: 
https://leetcode.com/problems/maximum-ascending-subarray-sum/

### Code
```
var maxAscendingSum = function(nums) {
    let prevNum = nums[0]; 
    let currSum = nums[0]; 
    let maxSum = nums[0]; 
    for(let i=1; i < nums.length; i++){
        if (nums[i] > prevNum){
            currSum += nums[i];
            prevNum = nums[i];
        } else {
            if (currSum > maxSum){
                maxSum = currSum; 
            }
            currSum = nums[i];
            prevNum = nums[i];
        }
        // if last number also check the currSum to maxSum 
        if (i == nums.length - 1 && currSum > maxSum){
            maxSum = currSum;
        }
    }
    return maxSum;
};
```

## Day 16: March 21, 2021 

### Today's Progress: 
Today I focused on gaining progress in my current ecommerce site project. A lot of time was spent learning react-bootstrap in order to incorporate it into this project. 

### Thoughts: 
I began working on this project relatively late since I was unable to secure an idea I liked and then the past 2 days I also struggled to scaffold out my ideas and how I wanted to approach the project. Now that I have a general vision for the project and have an idea for how to build out the project, it has become much easier to gain headway. Today I learned a good deal about bootstrap and was able to incorporate it heavily in my project. With how many working components that come straight out the box with bootstrap, it certainly streamlines a lot of design work. 

### Problem/Link to work: 
code in fan-apparel repository.

### Code
```
Code in fan-apparel repository. 
```