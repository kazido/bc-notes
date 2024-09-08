---
Created: 2024-01-15T10:06
---
## Binary Trees

- Binary trees can be recursively defined
    - Left and Right subtree are their own binary trees
    - Binary trees can have no nodes
- Defined as max(height of left subtree, height of right subtree) + 1
- This affects the fact that binary trees can have no nodes
    - Tree with no nodes has a height of -1
    - Tree with one node has a height of 0 (since we are counting edges, not nodes)

### Properties

- External nodes are leaves, internal nodes are non-leaves
- Full binary tree - all noes have either 0 or 2 children
- for full binary trees, the # of external nodes is the # of internal nodes +1

### Traversals

- In order (left-node-right or LNR) traversal. Example: BST “tree sort”
- Post order (LRN) traversal - postfix expression of an expression tree
- Pre order (NLR) traversal - stores binary tree file and “remember” structure