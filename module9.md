EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

#include <stdio.h>

#define MAX 5

int stack[MAX];
int top = -1;

void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        stack[++top] = value;
        printf("%d pushed to stack\n", value);
    }
}

int pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
        return -1;
    } else {
        return stack[top--];
    }
}

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);

    display();

    pop();
    printf("After popping, the stack is:\n");
    display();

    push(60);
    printf("After pushing 60, the stack is:\n");
    display();

    return 0;
}



Output:

10 pushed to stack
20 pushed to stack
30 pushed to stack
40 pushed to stack
50 pushed to stack
Stack elements are:
50 40 30 20 10 
After popping, the stack is:
40 30 20 10 
After pushing 60, the stack is:
60 40 30 20 10 



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

#include <stdio.h>

#define MAX 5

float stack[MAX];
int top = -1;

void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow: Cannot push %f, stack is full.\n", value);
    } else {
        stack[++top] = value;
        printf("%f pushed to stack\n", value);
    }
}

int main() {
    float value;

    printf("Enter a floating-point number to push into the stack: ");
    scanf("%f", &value);
    push(value);

    printf("Enter another floating-point number to push into the stack: ");
    scanf("%f", &value);
    push(value);

    return 0;
}


Output:

Enter a floating-point number to push into the stack: 3.14
3.140000 pushed to stack
Enter another floating-point number to push into the stack: 1.618
1.618000 pushed to stack



Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
    } else {
        printf("Queue elements are: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    queue[++rear] = 10;
    if (front == -1) front = 0;
    queue[++rear] = 20;
    queue[++rear] = 30;
    queue[++rear] = 40;

    display();

    return 0;
}


Output:

Queue elements are: 10 20 30 40 



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

#include <stdio.h>

#define MAX 5

float queue[MAX];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow: Cannot enqueue %f, queue is full.\n", value);
    } else {
        if (front == -1) front = 0;
        queue[++rear] = value;
        printf("%f enqueued to queue\n", value);
    }
}

int main() {
    float value;

    printf("Enter a floating-point number to enqueue into the queue: ");
    scanf("%f", &value);
    enqueue(value);

    printf("Enter another floating-point number to enqueue into the queue: ");
    scanf("%f", &value);
    enqueue(value);

    return 0;
}




Output:


Enter a floating-point number to enqueue into the queue: 3.14
3.140000 enqueued to queue
Enter another floating-point number to enqueue into the queue: 2.71
2.710000 enqueued to queue





Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:



#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void dequeue() {
    if (front == -1) {
        printf("Queue is empty. Cannot delete element.\n");
    } else {
        printf("Element %d dequeued from queue\n", queue[front]);
        front++;
        if (front > rear) {
            front = rear = -1;
        }
    }
}

int main() {
    queue[++rear] = 10;
    if (front == -1) front = 0;
    queue[++rear] = 20;
    queue[++rear] = 30;
    
    printf("Before dequeue:\n");
    dequeue();  // Delete the front element
    
    printf("After dequeue:\n");
    dequeue();  // Delete the next front element
    
    return 0;
}




Output:



Before dequeue:
Element 10 dequeued from queue
After dequeue:
Element 20 dequeued from queue




Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
