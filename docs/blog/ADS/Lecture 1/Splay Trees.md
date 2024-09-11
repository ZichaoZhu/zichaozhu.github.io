# Splay Trees

## Target

Any M consecutive tree operations starting from an empty tree take at most $O(M \log N)$ time.

*So AVL tree is a kind of splay tree.*

It just means that the **amortized** time is $O(\log N)$.

> *Note*: access: 访问、接触

## Idea

After a node is accessed, it is pushed to the root by a series of AVL tree rotations.

