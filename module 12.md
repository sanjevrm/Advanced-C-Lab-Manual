

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;          
    struct Node* next;  
};
struct Node* head = NULL;
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));  
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }
    newNode->data = value;       
    newNode->next = head;         
    head = newNode;               
}
void display() {
    struct Node* temp = head;  
    if (temp == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data); 
        temp = temp->next;         
    }
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push\n2. Display Stack\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        
        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);  
                break;
                
            case 2:
                display();  
                break;
                
            case 3:
                exit(0); 
                
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
         
```
Output:

![image](https://github.com/user-attachments/assets/8a58f7b2-2040-43b2-ab01-82bfc68a646a)


Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
};
struct Node* head = NULL;
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));  
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }
    newNode->data = value;        
    newNode->next = head;         
    head = newNode;               
}
void pop() {
    if (head == NULL) {  
        printf("Stack is empty.\n");
        return;
    }
    
    struct Node* temp = head;  
    head = head->next;         
    free(temp);                
    printf("Element popped from the stack.\n");
}
void display() {
    struct Node* temp = head;  
    if (temp == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    
    printf("Stack elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;         
    }
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push\n2. Pop\n3. Display Stack\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        
        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);  
                break;
                
            case 2:
                pop();  
                break;
                
            case 3:
                display();  
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
Output:

![image](https://github.com/user-attachments/assets/9a350955-204c-4c3e-87cc-19919be1bec3)


Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;          
    struct Node* next;  
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));  
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }
    newNode->data = value;        
    newNode->next = NULL;         
    
    if (rear == NULL) {           
        front = rear = newNode;
    } else {
        rear->next = newNode;     
        rear = newNode;           
    }
}
void display() {
    if (front == NULL) {  
        printf("Queue is empty.\n");
        return;
    }
    
    struct Node* temp = front;  
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;          
    }
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Display Queue\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);  
                break;

            case 2:
                display();  
                break;

            case 3:
                exit(0);  

            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/817676e4-f160-43c3-86ad-a429ce0fcbdb)


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next; 
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
   
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }
    
    newNode->data = value; 
    newNode->next = NULL;   
    
    
    if (rear == NULL) {
        
        front = rear = newNode;
    } else {
        
        rear->next = newNode;
       
        rear = newNode;
    }

    printf("Element %d inserted into the queue.\n", value);
}
void display() {
    if (front == NULL) {  
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;  
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;          
    }
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Display Queue\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);  
                break;

            case 2:
                display();  
                break;

            case 3:
                exit(0);  

            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/e9e80970-e7f8-4548-bca5-eb7db68bd4ce)

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next;  
};
struct Node* front = NULL;
struct Node* rear = NULL;
void enqueue(int value) {
   
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }
    
    newNode->data = value; 
    newNode->next = NULL;  
   
    if (rear == NULL) {
        
        front = rear = newNode;
    } else {
       
        rear->next = newNode;
        
        rear = newNode;
    }

    printf("Element %d inserted into the queue.\n", value);
}
int peek() {
    if (front == NULL) {
        printf("Queue is empty. No elements to peek.\n");
        return -1;  
    }
    return front->data;  
}
void display() {
    if (front == NULL) {  
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front;  
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);  
        temp = temp->next;          
    }
    printf("\n");
}

int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Peek\n3. Display Queue\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);  
                break;

            case 2:
                value = peek();  
                if (value != -1) {
                    printf("Front element is: %d\n", value);
                }
                break;

            case 3:
                display();  
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

Output:

![image](https://github.com/user-attachments/assets/af50ab52-2b6e-4a05-98e6-9ba43c09a27a)


Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


