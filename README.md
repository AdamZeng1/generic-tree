We usually visualize trees with children nodes spreading out horizontally beneath their parent nodes, but **GenericTree** allows you to output the tree in text format to the terminal with a *vertical* orientation. In this style, what is usually the “leftmost” child of the root node (that is, the first child in the node’s collection of children) will actually be displayed at the top, above the other children of the root node. 

Here is a small example for comparison. Suppose the root node is A, its first child (the “leftmost” child) is B, and its rightmost child is C. In a typical tree diagram, that would be displayed as in Fig. 2, with A on top, B on the left, and C on the right. Nodes at the same level in the tree appear in the same horizontal row: 

  A

 /  \

B   C

*Fig. 2: A horizontal tree diagram*

However, if you create this tree as a **GenericTree** object and output it to **std::cout**, you will see the following vertical diagram (Fig. 3), which more closely resembles a file directory or nested list display style. The root node is still displayed at the top, but the leftmost child is then displayed topmost. Nodes at the same level in the tree appear in the same vertical column: 

**Additional STL Data Structures** 

Besides the **GenericTree** class template that we provide, you’ll notice that the provided code makes use of several Standard Template Library (STL) data structures, especially **std::vector**, **std::stack**, and **std::queue**. You can see how these are used in the provided code, and you might want to use them when you solve the problems. Additional documentation about those and other STL structures can be found readily on the web: 

http://www.cplusplus.com/reference/vector/vector/ https://en.cppreference.com/w/cpp/container/vector 

In particular, these member functions are quite useful: (for **std::vector**) **push_back**; (for **std::stack**) **push**, **top**, and **pop**; (for **std::queue**) **push**, **front**, and **pop**. 

**Programming Objectives** **Study the Code** 

Since we have provided you with several files with examples and complete classes and functions to use, it’s best to begin by reading the code that you are given. There are comments throughout and many hints about how to do the exercises. Some of the example functions and **GenericTree** member functions show coding techniques directly applicable to the exercises. 

**Complete the Exercises** 

Your task for this project is to complete the two exercises located in the **GenericTreeExercises.h** file. **Exercise 1: treeFactory** 

This function is passed a **GenericTree** object as input by reference (so no copying is done), and you need to modify that object in-place so that it becomes the tree illustrated in the code comments. Because an existing tree is passed in for direct modification, you should check if it has any existing contents and delete those contents properly first. There are examples in the provided code files showing how to construct a **GenericTree** using its member functions. The tree you want to recreate is shown here (you can also see this represented in the exercise source code): 

4
 |
 |_ 8
 |    |
 |    |_ 16 
 |    |     |_ 42
 |    |_ 23
 |
 |_ 15 

*Fig. 4: The expected treeFactory results* 

**Exercise 2: traverseLevels** 

This function needs to perform a level-order traversal of the input tree, and make a record of the data it finds (in order) using the std::vector class. The code comments provide some discussion about the design considerations that go into implementing this; for example, note that level-order traversal and breadth-first search are often natural to implement using a queue, while pre-order traversal and depth-first search are often implemented most simply using a stack. If you use a data structure to keep track of which nodes to traverse next and in what order, you should probably store pointers to nodes rather than full copies of the nodes themselves. There are examples of various similar functions in the provided code files. 

You may also want to think about the different costs or benefits of writing functions like these recursively (the function making calls to itself on smaller and smaller problems) versus iteratively (looping explicitly). There are some notes about that in the provided code comments as well. 