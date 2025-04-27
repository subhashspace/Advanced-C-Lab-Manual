EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

void search(struct Node* head, char key) {
    struct Node* current = head;
    int position = 0;
    while (current != NULL) {
        if (current->data == key) {
            printf("Element '%c' found at position %d\n", key, position);
            return;
        }
        current = current->next;
        position++;
    }
    printf("Element '%c' not found in the linked list\n", key);
}

int main() {
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;

    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 'A';
    head->next = second;

    second->data = 'B';
    second->next = third;

    third->data = 'C';
    third->next = NULL;

    char key;
    printf("Enter character to search in the linked list: ");
    scanf("%c", &key);
    search(head, key);

    return 0;
}




Output:



Enter character to search in the linked list: B
Element 'B' found at position 1



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

void insert(struct Node** head, char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    while (last->next != NULL) {
        last = last->next;
    }

    last->next = newNode;
}

void printList(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    printf("Linked List: ");
    printList(head);

    return 0;
}



Output:

Linked List: A -> B -> C -> NULL

 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:


#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

void traverse(struct Node* head) {
    struct Node* temp = head;
    
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;

    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 1;
    head->next = second;
    head->prev = NULL;

    second->data = 2;
    second->next = third;
    second->prev = head;

    third->data = 3;
    third->next = NULL;
    third->prev = second;

    printf("Doubly Linked List: ");
    traverse(head);

    return 0;
}




Output:


Doubly Linked List: 1 <-> 2 <-> 3 <-> NULL




Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:



#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

void insertEnd(struct Node** head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    while (last->next != NULL) {
        last = last->next;
    }

    last->next = newNode;
    newNode->prev = last;
}

void traverse(struct Node* head) {
    struct Node* temp = head;
    
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    insertEnd(&head, 1);
    insertEnd(&head, 2);
    insertEnd(&head, 3);

    printf("Doubly Linked List: ");
    traverse(head);

    return 0;
}




Output:



Doubly Linked List: 1 <-> 2 <-> 3 <-> NULL




Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void deleteElement(struct Node** head, int value) {
    if (*head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // Handle the case where the element to be deleted is the head node
    if (temp != NULL && temp->data == value) {
        *head = temp->next; 
        free(temp); 
        printf("Element %d deleted.\n", value);
        return;
    }

    // Traverse the list to find the node to delete
    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    // If element was not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", value);
        return;
    }

    // Update the next of the previous node to skip the node to be deleted
    prev->next = temp->next;
    
    // Free the memory of the node to be deleted
    free(temp);
    printf("Element %d deleted.\n", value);
}

void traverse(struct Node* head) {
    struct Node* temp = head;

    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

void insertEnd(struct Node** head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    while (last->next != NULL) {
        last = last->next;
    }

    last->next = newNode;
}

int main() {
    struct Node* head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);
    
    printf("Original Linked List: ");
    traverse(head);

    deleteElement(&head, 20);
    printf("After Deleting 20: ");
    traverse(head);

    deleteElement(&head, 10);
    printf("After Deleting 10: ");
    traverse(head);

    deleteElement(&head, 50);  // Element not found
    printf("After Trying to Delete 50: ");
    traverse(head);

    return 0;
}





Output:

Original Linked List: 10 -> 20 -> 30 -> 40 -> NULL
Element 20 deleted.
After Deleting 20: 10 -> 30 -> 40 -> NULL
Element 10 deleted.
After Deleting 10: 30 -> 40 -> NULL
Element 50 not found in the list.
After Trying to Delete 50: 30 -> 40 -> NULL




Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





