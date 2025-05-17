
## EXP NO:11
C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim: 
To write a C program to display stack elements using an array. 

## Algorithm:

Include Necessary Header Files
Declare Global Variables
Define the Display Function
Main Function (or Other Relevant Code)
Initialize the stack and top as needed.
Perform stack operations (push, pop, etc.).
Use the display function to visualize the stack's contents
## Program:
```
#include <stdio.h> 
#define SIZE 5       
int stack[SIZE];
int top = -1;
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}
int main() {
    int choice, value;

    while(1) {
        printf("\n*** Stack Operations Menu ***\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice (1-4): ");
        scanf("%d", &choice);

        switch(choice) {
            case 1: 
                if(top == SIZE - 1) {
                    printf("Stack Overflow! Cannot push more elements.\n");
                } else {
                    printf("Enter value to push: ");
                    scanf("%d", &value);
                    top++;
                    stack[top] = value;
                    printf("%d pushed into the stack.\n", value);
                }
                break;

            case 2: 
                if(top == -1) {
                    printf("Stack Underflow! Stack is empty.\n");
                } else {
                    printf("Popped element is: %d\n", stack[top]);
                    top--;
                }
                break;

            case 3: 
                display();
                break;

            case 4:
                printf("Exiting the program.\n");
                return 0;

            default:
                printf("Invalid choice! Please enter between 1 and 4.\n");
        }
    }

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/0502f42e-8559-4553-80e4-a53e1869da98)


## Result:
Thus, the program to display stack elements using an array is verified successfully.

## EXP NO:12
PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY. Aim: To create a C program to push the given element in to a stack using array.

## Algorithm:

Declare global variables for the stack size, top index, and the stack itself.
Define the push function to add a floating-point number to the stack.
Initialize the stack size, top index, and the stack itself.
Call the push function as needed.
## Program:

```
#include <stdio.h>
#define MAX 5 
float stack[MAX];
int top = -1;
void push(float num) {
    if(top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", num);
    } else {
        top++;
        stack[top] = num;
        printf("%.2f pushed to stack at position %d\n", num, top);
    }
}

int main() {
    push(10.5);
    push(20.75);
    push(30.25);
    push(40.0);
    push(50.5);
    push(60.0);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/9a9f9628-29f8-450e-8ab2-adbf6527f3bc)

## Result:
Thus, the program to push the given element in to a stack using array is verified successfully

## EXP NO:13
C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY. Aim: To write a C program to display queue elements using array

## Algorithm:

Declare global variables for the queue, rear, front, and iteration.
Define the display function to print the elements of the queue.
Initialize the queue, rear, and front as needed.
Call the display function and perform other queue operations as needed.
Program:
```
#include <stdio.h>

#define MAX 5  
int queue[MAX];
int front = -1, rear = -1;
int i; 
void display() {
    if (front == -1) {
        printf("\nQueue is empty.\n");
    } else {
        printf("\nQueue elements are: ");
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("\nQueue is full. Cannot insert %d.\n", value);
    } else {
        if (front == -1) front = 0; 
        rear++;
        queue[rear] = value;
        printf("\nInserted %d into the queue.\n", value);
    }
}
void dequeue() {
    if (front == -1 || front > rear) {
        printf("\nQueue is empty. Cannot delete.\n");
    } else {
        printf("\nDeleted %d from the queue.\n", queue[front]);
        front++;
    }
}

int main() {
    display();

    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);

    display();

    dequeue();
    dequeue();

    display();

    enqueue(60);

    display();

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/b79073a8-2beb-470d-9fab-b25570fe9956)


## Result:
Thus, the program to display queue elements using array is verified successfully.

## EXP NO 14 C:
PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY. Aim: To write a C program to insert elements in queue using array.

## Algorithm:

Declare global variables for the size, rear, front, and the queue itself.
Define the enqueue function to add a float to the queue.
Initialize the rear, front, and size of the queue as needed.
Call the enqueue function as needed.
## Program:
```
#include <stdio.h>
#define MAX 5
float queue[MAX];
int front = -1;
int rear = -1;
int size = MAX;
void enqueue(float value) {
    if (rear == size - 1) {
        printf("Queue is full. Cannot enqueue %.2f\n", value);
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
        printf("%.2f enqueued to queue.\n", value);
    }
}

int main() {
    enqueue(1.1);
    enqueue(2.2);
    enqueue(3.3);
    enqueue(4.4);
    enqueue(5.5);
    enqueue(6.6);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/d9acefbd-e1bf-4246-ac61-644fb3f34e7e)


## Result:
Thus, the program to insert elements in queue using array is verified successfully.

## EXP NO:15
C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

Check if the Queue is Empty o If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
Delete the Front Element o If the queue is not empty, the element at the front index is deleted. o Increment the front pointer by 1 to remove the element and point to the next element in the queue.
Check if the Queue Becomes Empty After Deletion: o After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
End the Function.
## Program:

```
#include <stdio.h>

#define SIZE 5 
int queue[SIZE];
int front = -1, rear = -1;

void delete() {
    if (front == -1) {
        printf("Queue is empty. Cannot delete.\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;

        if (front > rear) {
            front = rear = -1;
            printf("Queue is now empty after deletion.\n");
        }
    }
}
void insert(int value) {
    if (rear == SIZE - 1) {
        printf("Queue is full. Cannot insert %d.\n", value);
    } else {
        if (front == -1) front = 0; 
        rear++;
        queue[rear] = value;
        printf("Inserted %d into queue.\n", value);
    }
}
void display() {
    if (front == -1) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    insert(10);
    insert(20);
    insert(30);
    display();

    delete();
    display();

    delete();
    display();

    delete();
    display();

    delete(); 
    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/e6d3c162-8c67-4c2f-b84e-242c21aab0d5)


## Result: 
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
