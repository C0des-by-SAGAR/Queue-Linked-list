# Queue Implementation in C

This documentation provides an overview of the C code that implements a basic queue using a linked list. The code defines essential functions to create, enqueue, dequeue, check if the queue is empty, and display the contents of the queue.

## Table of Contents

1. [Introduction](#introduction)
2. [Code Overview](#code-overview)
    - [Node Structure](#node-structure)
    - [Queue Structure](#queue-structure)
    - [createQueue() Function](#createqueue-function)
    - [isEmpty() Function](#isempty-function)
    - [enqueue() Function](#enqueue-function)
    - [dequeue() Function](#dequeue-function)
    - [displayQueue() Function](#displayqueue-function)
3. [Usage](#usage)
4. [Example](#example)
5. [Compile and Run](#compile-and-run)
6. [Conclusion](#conclusion)

## Introduction<a name="introduction"></a>

This C code demonstrates the implementation of a queue data structure using a linked list. A queue is a linear data structure that follows the First-In-First-Out (FIFO) order, meaning the first element added to the queue will be the first one to be removed. This implementation provides basic operations for managing a queue, including enqueue (add to the rear), dequeue (remove from the front), and display.

## Code Overview<a name="code-overview"></a>

### Node Structure<a name="node-structure"></a>

The `struct Node` structure represents a node in the linked list. Each node contains an integer `data` field and a pointer to the next node.

```c
struct Node {
    int data;
    struct Node* next;
};
```

### Queue Structure<a name="queue-structure"></a>

The `struct Queue` structure represents the queue and includes pointers to the front and rear nodes of the queue.

```c
struct Queue {
    struct Node* front;
    struct Node* rear;
};
```

### createQueue() Function<a name="createqueue-function"></a>

This function creates an empty queue and returns a pointer to it.

```c
struct Queue* createQueue();
```

### isEmpty() Function<a name="isempty-function"></a>

The `isEmpty()` function checks if the queue is empty and returns `1` if it is, and `0` if it is not.

```c
int isEmpty(struct Queue* queue);
```

### enqueue() Function<a name="enqueue-function"></a>

The `enqueue()` function adds an element to the rear of the queue.

```c
void enqueue(struct Queue* queue, int data);
```

### dequeue() Function<a name="dequeue-function"></a>

The `dequeue()` function removes and returns an element from the front of the queue.

```c
int dequeue(struct Queue* queue);
```

### displayQueue() Function<a name="displayqueue-function"></a>

The `displayQueue()` function prints the contents of the queue.

```c
void displayQueue(struct Queue* queue);
```

## Usage<a name="usage"></a>

1. Create a queue using `createQueue()` function.
2. Enqueue elements into the queue using `enqueue()` function.
3. Dequeue elements from the queue using `dequeue()` function.
4. Check if the queue is empty using `isEmpty()` function.
5. Display the contents of the queue using `displayQueue()` function.

## Example<a name="example"></a>

Here's an example of how to use this queue implementation:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    struct Queue* queue = createQueue();
    int choice, data;

    while (1) {
        printf("Queue Operations:\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter the element to enqueue: ");
                scanf("%d", &data);
                enqueue(queue, data);
                break;
            case 2:
                if (!isEmpty(queue)) {
                    printf("Dequeued element: %d\n", dequeue(queue));
                }
                break;
            case 3:
                displayQueue(queue);
                break;
            case 4:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```

## Compile and Run<a name="compile-and-run"></a>

To compile and run the code, use a C compiler such as GCC:

```bash
gcc -o queue queue.c
./queue
```

This will compile the code and execute the program, allowing you to interact with the queue operations.

## Conclusion<a name="conclusion"></a>

This C code provides a basic implementation of a queue data structure using a linked list. It includes functions for creating, enqueuing, dequeuing, checking if the queue is empty, and displaying the contents of the queue. You can use this code as a starting point for more advanced queue-based applications.
