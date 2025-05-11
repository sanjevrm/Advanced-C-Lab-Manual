EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
int search(struct Node* head, int value) {
    struct Node* current = head;
    while (current != NULL) {
        if (current->data == value) {
            return 1; // Element found
        }
        current = current->next;
    }
    return 0; 
}
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node* head = NULL;  
    struct Node* temp = NULL;
    head = createNode(10);
    temp = createNode(20);
    head->next = temp;
    temp = createNode(30);
    head->next->next = temp;

    int value;
    printf("Enter the value to search in the linked list: ");
    scanf("%d", &value);
    if (search(head, value)) {
        printf("Element %d found in the linked list.\n", value);
    } else {
        printf("Element %d not found in the linked list.\n", value);
    }

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/2098badb-dec2-4d8d-bcef-8d1160a693cf)


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
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
int search(struct Node* head, int value) {
    struct Node* current = head;
    while (current != NULL) {
        if (current->data == value) {
            return 1; 
        }
        current = current->next;
    }
    return 0; 
}
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node* head = NULL;  
    struct Node* temp = NULL;
    head = createNode(10);
    temp = createNode(20);
    head->next = temp;
    temp = createNode(30);
    head->next->next = temp;

    int value;
    printf("Enter the value to search in the linked list: ");
    scanf("%d", &value);
    if (search(head, value)) {
        printf("Element %d found in the linked list.\n", value);
    } else {
        printf("Element %d not found in the linked list.\n", value);
    }

    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/40c89f90-6712-43b5-809f-0385e8efbf53)

 
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
```
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};


void traverse(struct Node* head) {
    struct Node* temp = head;  
    
    
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;          
    }
    printf("\n");
}

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}

int main() {

    struct Node* head = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);
    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;
    printf("Doubly Linked List: ");
    traverse(head);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/be0c38ef-8ceb-46cb-ab98-42652d32fa4e)

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
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};
void insertEnd(struct Node** head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = *head;

    newNode->data = value;
    newNode->next = NULL; 
    newNode->prev = NULL;
    if (*head == NULL) {
        *head = newNode;
        return;
    }

    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
void traverse(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL; 
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    printf("Doubly Linked List after insertion: ");
    traverse(head);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/b215256c-d437-41a5-9b9c-2623018f2115)

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
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};

void deleteNode(struct Node** head, int key) {
    struct Node *temp = *head, *prev = NULL;

    if (*head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    if (temp != NULL && temp->data == key) {
        *head = temp->next; // Move head to the next node
        free(temp);         // Free the old head
        printf("Element %d deleted successfully.\n", key);
        return;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted successfully.\n", key);
}
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

void insertEnd(struct Node** head, int newData) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    newNode->data = newData;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    while (last->next != NULL)
        last = last->next;

    last->next = newNode;
}

int main() {
    struct Node* head = NULL;
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);

    printf("Original Linked List:\n");
    printList(head);
    deleteNode(&head, 20);
    printf("Linked List after deleting 20:\n");
    printList(head);
    deleteNode(&head, 50);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/880ea215-fd85-4206-b3fa-319c58beb774)


Result:

Thus, the function that deletes a given element from a linked list is verified successfully.





