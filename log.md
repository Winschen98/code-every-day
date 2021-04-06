## Day 0: March 6, 2021 

Today's Progress: Continuing to do coding challenges on Leetcode.

Thoughts: Still working my way up to more difficult problems and finding creative, more optimal approaches to every challenge. 

Link to work: https://leetcode.com/problems/maximum-depth-of-binary-tree/
### code
var maxDepth = function(root) {
    function dfs(node, height){
        if (!node) return height; 
        return Math.max(dfs(node.left, height + 1), dfs(node.right, height + 1))
    }
    return dfs(root, 0);
};