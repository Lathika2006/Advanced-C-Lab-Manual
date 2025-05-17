
## EXP NO:16
C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST. Aim: To write a C program to search a given element in the given linked list.

## Algorithm:

Define the structure for a node in a linked list.
Define the search function to find a specific character in the linked list.
Initialize the head of the linked list as needed.
Call the search function and perform other linked list operations as needed.
## Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node* next;
};
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
struct Node* insertEnd(struct Node* head, char data) {
    struct Node* newNode = createNode(data);
    if (head == NULL) {
        head = newNode;
    } else {
        struct Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
    return head;
}
void search(struct Node* head, char key) {
    struct Node* temp = head;
    int position = 1;
    int found = 0;

    while (temp != NULL) {
        if (temp->data == key) {
            printf("Character '%c' found at position %d.\n", key, position);
            found = 1;
            break;
        }
        temp = temp->next;
        position++;
    }

    if (!found) {
        printf("Character '%c' not found in the linked list.\n", key);
    }
}
void display(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    char searchChar;
    head = insertEnd(head, 'A');
    head = insertEnd(head, 'B');
    head = insertEnd(head, 'C');
    head = insertEnd(head, 'D');
    head = insertEnd(head, 'E');
    display(head);
    printf("\nEnter character to search: ");
    scanf(" %c", &searchChar);
    search(head, searchChar);

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/c24f7edf-0577-4bdd-9b50-b3559cbd721f)


## Result: 
Thus, the program to search a given element in the given linked list is verified successfully.

## EXP NO:17 
PROGRAM TO INSERT A NODE IN A LINKED LIST. Aim: To write a C program to insert a node in a linked list. 
## Algorithm:

Define the structure for a node in a linked list
Define the insert function to insert a new node with character data at the end of the linked list.
Initialize the head of the linked list as needed.
Call the insert function and perform other linked list operations as needed.
## Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node* next;
};
struct Node* head = NULL;
void insert(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL) {
        head = newNode;
    }
    else {
        struct Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}
void display() {
    struct Node* temp = head;
    printf("\nLinked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    insert('A');
    insert('B');
    insert('C');
    insert('D');

    display();

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/49f6e3fc-8d0a-48da-8d5f-1236afc119ac)


## Result:
Thus, the program to insert a node in a linked list is verified successfully.

## EXP NO:18 
C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST Aim: To write a C program to traverse a doubly linked list.

## Algorithm:

Initialize a temporary pointer (temp) to the head of the list.
Use a while loop to traverse the list until the end (temp == NULL) is reached.
Inside the loop, print the data of the current node.
Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a node
struct Node {
    int data;
    struct Node* next;
};

int main() {
    // Create three nodes
    struct Node* head = NULL;
    struct Node* second = NULL;
    struct Node* third = NULL;

    // Allocate memory for nodes
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    // Assign data and link nodes
    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL; // Last node points to NULL

    // Initialize a temporary pointer to head
    struct Node* temp = head;

    // Traverse and print the linked list
    printf("Linked List Elements:\n");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next; // Move to the next node
    }
    printf("NULL\n"); // End of the list

    // Free the allocated memory
    free(head);
    free(second);
    free(third);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/9b902f34-86de-4c54-a8f5-0f8236ac2a6e)


## Result:
Thus, the program to traverse a doubly linked list is verified successfully.

## EXP NO:19 
C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST Aim: To write a C program to insert an element in doubly linked list

## Algorithm:

Create a new node (newNode) and allocate memory for it.
Set the data of the new node to the provided value.
If the list is empty, set the new node as the head.
If the list is not empty, traverse the list to find the last node.
Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
## Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};
void insertEnd(struct Node** head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }

        temp->next = newNode;
        newNode->prev = temp;
    }
}
void display(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
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
    insertEnd(&head, 40);

    display(head);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/9910e708-a1e3-4d45-96e0-679589efd3a8)

## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.

## EXP NO 20:
C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim: 
To write a C function that deletes a given element from a linked list.

## Algorithm:

Check if the Linked List is Empty: o If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
Traverse the Linked List: o Start from the head node and iterate through the list to find the node that contains the given element (data).
Handle Deletion of the First Node: o If the element to be deleted is found in the head node:  Update the head of the linked list to point to the next node (i.e., head = head->next).  Free the memory allocated to the node to be deleted.  Exit the function.
Traverse and Delete from the Middle or End: o If the element is not in the head node, continue traversing the list by checking each node’s next pointer. o When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next). o Free the memory allocated to the node to be deleted.
Handle the Case when the Element is Not Found: o If the element is not found in any node, print a message indicating the element is not present in the list.
End the Function.
## Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
void deleteNode(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;
    if (temp == NULL) {
        printf("The linked list is empty.\n");
        return;
    }
    if (temp != NULL && temp->data == key) {
        *head = temp->next; 
        free(temp);
        printf("Element %d deleted from the list.\n", key);
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
    printf("Element %d deleted from the list.\n", key);
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
void displayList(struct Node* node) {
    if (node == NULL) {
        printf("The linked list is empty.\n");
        return;
    }

    printf("Linked List: ");
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}
int main() {
    struct Node* head = NULL;
    int choice, value;

    while (1) {
        printf("\n--- Menu ---\n");
        printf("1. Insert\n2. Delete\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                insertEnd(&head, value);
                break;
            case 2:
                printf("Enter value to delete: ");
                scanf("%d", &value);
                deleteNode(&head, value);
                break;
            case 3:
                displayList(head);
                break;
            case 4:
                exit(0);
            default:
                printf("Invalid choice! Try again.\n");
        }
    }
    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/caf7880e-4f03-494f-af4b-b35703ee06cc)

## Result: 
Thus, the function that deletes a given element from a linked list is verified successfully.


