# Binary Trees

## Review

### Sequence Data Structures

|               | Access      | Insert first | Insert last | Insert at pos |
| ------------- | ----------- | ------------ | ----------- | ------------- |
| Array         | $O(1)$      | $O(n)$       | $O(n)$      | $O(n)$        |
| Linked List   | $O(n)$      | $O(1)$       | $O(n)$      | $O(n)$        |
| Dynamic Array | $O(1)$      | $O(n)$       | $O(1)$      | $O(n)$        |
| **Goal**      | $O(\log n)$ | $O(\log n)$  | $O(\log n)$ | $O(\log n)$   |

### Set Data Structures

|              | Search       | Insert       | Find min     | Find prev    |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| Array        | $O(n)$       | $O(n)$       | $O(n)$       | $O(n)$       |
| Sorted Array | $O(\log n)$  | $O(n)$       | $O(1)$       | $O(\log n)$  |
| Map          | $O(1)$       | $O(1)$       | $O(n)$       | $O(n)$       |
| **Goal**     | $O(\log n)$  | $O(\log n)$  | $O(\log n)$  | $O(\log n)$  |

## Binary Tree

* Binary tree is a pointer-based data structure with three pointers per node
* Node representation:

  ```golang
  type node struct {
    value  T
    left   *node
    right  *node
    parent *node // optional
  }
  ```
### Example

![](tree.png)

| node   | A     | B     | C     | D     | E     | F     |
| ------ | ----- | ----- | ----- | ----- | ----- | ----- |
| value  | A     | B     | C     | D     | E     | F     |
| left   | *B*   | *D*   |       | *F*   |       |       |
| right  | *C*   | *E*   |       |       |       |       |
| parent |       | *A*   | *A*   | *B*   | *B*   | *D*   |

### Terminology

* The **root** of a tree has no parent
* A **leaf** of a tree has no children
* Define **depth** of node `<X>` to be length of path from `<X>` to the root
* Define **height** of node `<X>` to be max depth of any node in the subtree rooted at `<X>`