# Problem #814 ([Binary Tree Pruning](https://leetcode.com/problems/binary-tree-pruning/) | Tree, Depth-First Search, Binary Tree)

Given the `root` of a binary tree, return *the same tree where every subtree (of the given tree)* not containing a `1` *has been removed*.

A subtree of a node `node` is `node` plus every node that is a descendant of `node`.

# Solutions

## 1. Depth-First Search (Recursive)

### Codes

- **Java**
```java
class Solution {
    public TreeNode pruneTree(TreeNode root) {
        if(root == null) return null;
        root.left = pruneTree(root.left);
        root.right = pruneTree(root.right);
        if(root.left == null && root.right == null && root.val== 0) return null;
        return root;
    }
}
```
![image](https://user-images.githubusercontent.com/89616705/188560772-96ad0936-d406-4489-a978-ee85a449757a.png)
<br/>

- **C++*
```cpp
class Solution {
public:
    TreeNode* pruneTree(TreeNode* root) {
        if(!root) return NULL;
        root->left = pruneTree(root->left);
        root->right = pruneTree(root->right);
        if(!root->left && !root->right && root->val == 0) return NULL;
        return root;
    }
};
```
![image](https://user-images.githubusercontent.com/89616705/188562216-e8876062-e363-440b-8b7d-6671284bffc7.png)
<br/>

- **Python**
```python
class Solution(object):
    def pruneTree(self, root):
        if not root: return None
        root.left = self.pruneTree(root.left)
        root.right = self.pruneTree(root.right)
        if not root.left and not root.right and root.val == 0: return None
        return root
```
![image](https://user-images.githubusercontent.com/89616705/188563159-629b3d24-4242-4b49-aeb5-7e5ea888e88e.png)

### Complexity
- **Time:** `O(log n)`
- **Space:** `O(1)`