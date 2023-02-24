# Activities

## Task 1:

- Refer to the following link. Discuss how Stacks based on linked lists works:
  https://www.cs.usfca.edu/~galles/visualization/StackLL.html
  The link provided is a visualization tool that demonstrates how a stack based on linked lists works. Here's how it works:

1. At the beginning, the stack is empty, and the top of the stack points to null.

2. To add an item to the stack, we create a new node and set its data to the value we want to push onto the stack. We then set the next pointer of the new node to point to the current top of the stack. Finally, we update the top pointer to point to the new node.

3. To remove an item from the stack (pop), we first check if the stack is empty (i.e., if the top pointer is null). If the stack is not empty, we store the value of the top node's data in a variable, update the top pointer to point to the next node in the list, and then delete the old top node.

4. To view the current top item on the stack, we simply return the value of the data stored in the top node.

The visualization tool provides an interactive display of this process, allowing users to add and remove items from the stack and observe how the linked list structure changes. As items are added to the stack, new nodes are created and linked to the previous nodes. As items are removed from the stack, the top pointer is updated to point to the next node in the list, and the old top node is deleted.

## Task 2:

The following snippet is from `./src/stack.cpp` lines 25-31.

```cpp
void push(StackNode **root, int new_data)
{
    StackNode *stackNode = newNode(new_data);
    stackNode->next = *root;
    *root = stackNode;
    cout << new_data << endl;
}
```

- Discuss in groups how the code works?

// This code implements the push function for a stack data structure using a linked list. Here's how it works:

The function takes two arguments: a pointer to a pointer to a StackNode, which points to the root of the stack, and an integer new_data, which is the value to be pushed onto the stack.

The function creates a new StackNode using the newNode function (not shown here), which initializes the node with the given data and sets its next pointer to null.

The function sets the next pointer of the new node to point to the current root of the stack.

The function sets the root pointer to point to the new node, effectively making the new node the new root of the stack.

Finally, the function outputs the value that was pushed onto the stack using cout.

- Why do we need to use double pointers?

// the reason is that the root pointer needs to be modified by the push function, which means that we need to pass a pointer to the root pointer. If we only passed a pointer to the root node itself, then any modifications made to the pointer within the function would not persist outside of the function. By passing a pointer to the pointer, we can modify the actual root pointer and have that change be reflected outside of the function. This is a common technique used in C and C++ when working with pointers to pointers.

## Task 3: Individual (At home)


// The provided link is a set of exercises focused on understanding and practicing asymptotic analysis and upper bounds in computer algorithms. The exercises cover topics such as big-O notation, worst-case analysis, and time complexity of various algorithms.

The exercises are presented in a variety of formats, including multiple-choice questions, fill-in-the-blank questions, and free-response questions. They provide immediate feedback and explanations for each answer choice, making it easy to learn and understand the concepts being tested.

The exercises cover a wide range of difficulty levels, making them suitable for beginners as well as more advanced learners. They also cover a variety of algorithms and data structures, including sorting algorithms, search algorithms, and graph algorithms.

Overall, the exercises provide a useful resource for anyone looking to improve their understanding of asymptotic analysis and upper bounds in computer algorithms. They can be used as a standalone learning tool or as a supplement to a more comprehensive course or textbook.