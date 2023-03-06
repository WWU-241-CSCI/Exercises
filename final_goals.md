**L01**

Be able to interpret and use the range index notation we'll be using in this class: a..b
Know how to interpret array diagrams

Know the purpose and contents of a method specification
Know the definition and implications of preconditions and postconditions
Know the definition of loop invariant and be able to illustrate one with an array diagram.

Understand how the binary search algorithm works, and under what conditions.
Be able to execute binary search on paper.

> Here's code for binary search:
>
> ```java
> public static int binarySearch(int[] A, int v) {
>   int s = 0;
>   int e = A.length;
>   while (s < e) {
>     int m = (s + e) / 2;
>     if (A[m] == v) {
>       return m;
>     } else if (v < A[m]) {
>       e = m;
>     } else {
>       s = m + 1;
>     }
>   }
>   return -1;
> }
> ```
>
> Draw an array diagram illustrating the algorithm's loop invariant.

**L02**

Know the motivations for using asymptotic runtime analysis.
Know how to identify constant time operations in simple algorithms.

Know how to count constant time operations in simple algorithms.
Know how to find the asymptotic runtime class (big-O runtime) of an algorithm given a count of its constant-time operations.

Understand the runtime analysis of binary search.
Know how to perform best-case, worst-case, and average-case runtime analysis.

> Give the worst-case asymptotic runtime for each of the following algorithms:
>
> ```java
> public int exp1(int a, int n) {
>   int result = 1;
>   for (int i = 0; i < n; i++) {
>     result *= a; 
>   }
>   return result;
> }
> ```
>
> 
>
> ```java
> public int exp2(int a, int n) {
>   if (n == 0) {
>     return 1;
>   }
>   if (n % 2 == 1) {
>     return a * exp2(a, n-1);
>   } else {
>     int v = exp2(a, n/2)
>     return v * v;
>   } 
> }
> ```
>
> 
>
> ```java
> public static int find1(int[] A) {
> 	int s = 0;
>   for (int i = 0; i < A.length; i++)
>      if (binarySearch(A, i) > 0) {
>        s += binarySearch(A, i);
>      }
> }
> ```
>
> Give your answer in terms of $n$ where $n$ is `A.length`.

> ```java
> /** Precondition: A and B are sorted */
> public static int f2(int[] A, int[] B) {
>   k = 0;
>   int[] C = new int[A.length];
>   for (int i = 0; i < A.length; i++) {
>     while (B[k] < A[i]) {
>       C[i] += B[k];
>     	k += 1
>     }
>   }
> }
> ```
>
> Give your answer in terms of $a = $ `A.length`  and $b = $ `b.length`. 

**L03**

Gain some intuition for why dropping constants is a reasonable thing to do.
Gain familiarity with some of the common runtime classes.

Understand the distinction between interface and implementation in the context of operations on data structures.
Know the meaning of abstract data type.

Be able to execute insertion sort and selection sort on paper.
Be prepared to implement insertion sort and selection sort.

> Best sort for memory-constrained / costly-write device

**L04**

Understand how recursive methods are executed.

Be able to understand and develop recursive methods without thinking about the details of how they are executed.

> BST sum less than coding problem

Understand the distinction between incremental and divide-and-conquer algorithms.
Know the generic steps of a divide-and-conquer algorithm.

**L05**

Thoroughly understand the mechanism of mergesort.
Be able to execute mergesort on paper.

Be prepared to implement the merge helper method of mergesort.

Know how to derive the worst-case runtime of mergesort.

**L06**

Thoroughly understand the mechanism of quicksort.
Be able to execute quicksort on paper.
Be prepared to implement quicksort and its partition helper method.

Understand the best-case and worst-case runtime analysis of quicksort.
Know the average-case runtime of quicksort.

Know the definition of a stable sorting algorithm.
Know the definition of an in-place sorting algorithm.
Be able to categorize all the sorts we've covered with respect to these properties.

**L07**

Know the meaning of a comparison sort.
Be able to execute LSD radix sort on paper.
Be prepared to implement LSD radix sort using bucket sort in the inner loop.

> TF It is not possible to sort $n$ items faster than $O(n \log n)$.

**L08**

Know the definition of a tree.
Know the following basic tree terminology: root, child, parent, leaf, height, depth, subtree, descendant, ancestor

Understand some of the uses for trees:

* To model hierarchical data.
* To implement abstract data types.

Be able to implement a simple tree class and basic operations such as search and size.
Know how to execute on paper and implement pre-order, in-order, and post-order tree traversals.

> BST traversal (a); BST sum less than code

**L09**

Know the purpose and operations of the Set Abstract Data Type.
Know the motivation for and the definition of a binary search tree.
Be able to execute on paper, and be prepared to implement the search and add operations on a BST.

Understand the best-case and worst-case runtime analysis of BST add and contains.

Be able to remove a node from a BST on paper.
Be prepared to implement BST removal.

> BST (e)

**L10**

Know why we want our BSTs to be balanced.
Be able to calculate the balance factor of a binary tree.

Be able to execute BST rotations on paper.
Be prepared to implement BST rotations.

> BST (d)

**L11**

Know the definition and properties of an AVL tree.
Know how AVL insertion rebalances the tree to correct violations of the AVL property.

Understand how rebalance decides what rotations to perform.
Be prepared implement rebalance.

**L12**

Understand the purpose and interface of the Priority Queue ADT.

Know the definition and properties of a heap.
Understand how heaps are stored in practice.
Be prepared to implement add and execute it on paper.

Be prepared to implement the peek, and poll heap operations and execute them on paper.

**L13**

**L14**

Understand the motivation for hash tables, and the workings of its simplistic cousin, the Direct Address Table.

Understand how a Hash Table can be used to store a set of integers.
Know the definition of a collision and how to use the chaining strategy for collision resolution.
Know how to calculate the load factor of a hash table.

Know the purpose and operations of the Map ADT.

Know how to implement the Set ADT using a hash table.
Analyze the worst-case and average-case runtime of hash table `insert`, `contains`, and `remove`.
Know how to implement the Map ADT using any Set implementation.

**L15**

Know how and why to grow and shrink the capacity of a hash table by resizing the array and rehashing its contents.
Be prepared to implement rehashing so it runs in worst-case O(C + n).

Know how to use open addressing with linear or quadratic probing for collision resolution.

Know how to hash types other than integers (e.g., Strings)
Know how hashing is implemented in Java via Object's hashCode method.

**L16**

Know what computer scientists mean when they talk about graphs.

Know the definition of a graph and its basic associated
terminology:

* node/vertex
* edge/arc
* directed, undirected
* adjacent, (in-/out-)degree
* path, cycle

Know little more graph terminology:

* (strongly/weakly) connected
* connected component

Know how a graph can be represented on computers
using an:

* Adjacency list
* Adjacency matrix

Be able to analyze the runtime of simple graph operations on adjacency matrices and adjacency lists.

> TF The runtime of breadth-first search on a graph with v nodes and e edges is always O(v + e), no matter how the graph is stored.

**L17**

Be able to execute and implement depth-first search to search or traverse a graph.

Be able to implement DFS iteratively using a stack.

Be able to execute and implement breadth-first search to search or traverse a graph.

Know how to analyze the runtime of BFS and DFS.

Know the definition of a *connected component*.

**L18**

Know what a weighted graph is.
Understand the intuition and high-level pseudocode for Dijkstra’s single-source shortest paths algorithm.
Be able to execute Dijkstra's algorithm on paper.

Know how to augment Dijkstra's algorithm to keep backpointers in order to reconstruct the sequence of nodes in a shortest path.

Be prepared to implement Dijkstra's algorithm efficiently.

**L19**

Know the purpose and definition of a Trie, and how it is used to implement the Set and Map ADTs.

Be able to execute on paper, implement, and analyze the runtime of contains, insert, and (lazy) delete in a Trie.

**L20**

Understand the motivation for entropy coding.
Be able to use a coding tree to decode and encode a message.

Understand the intuition behind Huffman Coding Trees
Be able to execute on paper and implement construction of Huffman Coding Trees.

