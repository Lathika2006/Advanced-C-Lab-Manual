# Advanced-C-Lab-Manual

## Module 7 Lab Assignment

## EXP NO:1
C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.
## Aim: 
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.
## Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
•	Print "Vaccine Eligibility: No" Else
•	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
## Program:
```
#include <stdio.h>
struct eligible {
    int age;
    char n[50];
};

int main() {
    struct eligible e; 
    printf("Enter name: ");
    scanf("%s", e.n);
    printf("Enter age: ");
    scanf("%d", &e.age);
    if (e.age <= 6) {
        printf("Vaccine Eligibility: No\n");
    } else {
        printf("Vaccine Eligibility: Yes\n");
    }
    return 0;
}
```
## Output:
 ![image](https://github.com/user-attachments/assets/8e129198-5bea-4469-b29b-eb006696973d)

## Result: 
Thus, the program is verified successfully.

## EXP NO:2 
C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION Aim: To write a C program for passing structure as function and returning a structure from a function
## Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
## Program:
```
#include <stdio.h>
struct numbers {
    int a;
    int b;
};
int add(struct numbers n) {
    return n.a + n.b;
}
int main() {
    struct numbers n;  
    printf("Enter value for a: ");
    scanf("%d", &n.a);
    printf("Enter value for b: ");
    scanf("%d", &n.b);
    int result = add(n);
    printf("Sum = %d\n", result);

    return 0;
}
```
## Output:
 ![image](https://github.com/user-attachments/assets/fa8378f4-21d4-484c-96c4-3ee9500eec90)

## Result:
Thus, the program is verified successfully.

## EXP.NO:3 
C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()
## Aim:
To write a C program to read a file name from user
## Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p. Declare a character array name to store the file name.
4.	Prompt the user to enter a file name. Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
•	If successful, continue to the next step.
•	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
## Program:
```
#include <stdio.h>

int main() {
    FILE *p;           
    printf("Enter the file name: ");
    scanf("%s", name);
    printf("File '%s' will be created...\n", name);
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: File could not be created.\n");
        return 1; 
    }

    printf("File '%s' has been opened successfully.\n", name);
    fclose(p);
    printf("File '%s' has been closed.\n", name);

    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/b9e6b2f1-5de3-402a-b0e0-460fd7761ee0)
## Result: 
Thus, the program is verified successfully

## EXP NO:4
PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 
## Aim: 
To write a C program to read, a file and insert text in that file Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
•	If successful, continue to the next step.
•	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
7.	Use a loop to input strings from the user and write them to the file using fputs.
8.	Use fclose to close the file.
9.	Print a message indicating that data has been added successfully.
10.	End the main function.
11.	Return 0 to indicate successful program execution.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[50], text[100];
    int num, i;
    printf("Enter the file name: ");
    scanf("%s", name);

    printf("Enter the number of strings to write: ");
    scanf("%d", &num);
    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error opening the file!\n");
        return 1; 
    }

    printf("File opened successfully.\n");
    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf(" %[^\n]", text); 
        fputs(text, p);
        fputs("\n", p); 
    }
    fclose(p);
    printf("Data has been added successfully.\n");

    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/e2c2d810-6e85-4eb9-bd0e-f42e82f295c1)

## Result:
Thus, the program is verified successfully.

## Ex No 5: 
C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE
## Aim:

The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.
## Algorithm: 

1.Input the number of subjects.
2.Read the integer value n from the user, which represents the number of subjects.
3.Dynamically allocate memory:
4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).
5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.
6.Input the details of each subject
7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.
8.Display the details of each subject
9.Use another for loop to print the name and marks of each subject.
10.Free the allocated memory
11.After all operations are done, call free(s) to release the dynamically allocated memory.
12.Return from the main function
13.End the program by returning 0.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    printf("Enter the number of subjects: ");
    scanf("%d", &n);
    struct subject *s = (struct subject *)malloc(n * sizeof(struct subject));
    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1; 
    }
    for (i = 0; i < n; i++) {
        printf("\nEnter the name of subject %d: ", i + 1);
        scanf("%s", s[i].name);
        printf("Enter the marks for %s: ", s[i].name);
        scanf("%d", &s[i].marks); 
    }
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("\nSubject: %s\n", s[i].name);
        printf("Marks: %d\n", s[i].marks);
    }
    free(s);
    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/5b520449-204b-4916-b342-082263a16ad2)

## Result: 
Thus, the program is verified successfully

##  Module 8 Lab Assignment

## EXP NO:6 
C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER Aim: To write a C program print the lowercase English word corresponding to the number 
## Algorithm
Start
Initialize an integer variable n.
Input Validation
Switch Statement cases.
Case 5: Print "seventy one"
Case 6: Print "seventy two"
Case 13: Print "seventy three"
...
Case 13: Print "seventy nine"
Default: Print "Greater than 13"
Exit the program.
## Program:
```
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);
    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/01010cc3-a197-49b3-9730-9d68802a2e52)

## Result:
Thus, the program is verified successfully

## EXP NO:7 
C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 . Aim: To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3. 
## Algorithm:

Start
Declare char array a[50] outer loop for each digit from 0 to 3
Initialize counter c to 0
For each character in the string print count c for current digit, followed by a space
Increment h to move to the next digit
End
## Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int h, i, c;
    printf("Enter a string of digits: ");
    scanf("%s", a);
    for(h = 0; h <= 3; h++) {
        c = 0; 
        for(i = 0; i < strlen(a); i++) {
            if(a[i] == h + '0') {
                c++;
            }
        }
        printf("%d ", c); 
    }

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/18a129d2-06cd-4e29-8857-ae77e41345e3)

## Result: 
Thus, the program is verified successfully

## EXP NO:8 
C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER. Aim: To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:

Start

Declare variables s (pointer to an array of strings) and n (number of strings)

Memory Allocation Dynamically allocate memory for s to store an array of strings

Input Read the number of strings n from the user Dynamically allocate memory for each string in s

Permutation Generation Loop

Memory Deallocation Free the memory allocated for each string in s Free the memory allocated for s

End

## Program:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}
void permute(char **s, int l, int r) {
    if (l == r) {
        for (int i = 0; i <= r; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } else {
        for (int i = l; i <= r; i++) {
            swap(&s[l], &s[i]);
            permute(s, l + 1, r);
            swap(&s[l], &s[i]); 
        }
    }
}

int main() {
    int n;
    char **s;
    printf("Enter the number of strings: ");
    scanf("%d", &n);
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); 
        if (s[i] == NULL) {
            printf("Memory allocation failed for string %d.\n", i + 1);
            return 1;
        }
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }
    printf("\nAll permutations of the strings:\n");
    permute(s, 0, n - 1);
    for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/0613b2b4-4205-4848-9bdf-ce38cb04dec0)


## Result:
Thus, the program is verified successfully

## EXP NO:9 
C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW. Aim: To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:

Start
Declare integer variables n, i, j, min
Read the value of n from the user
Calculate the length of the side of the square matrix: len = n * 2 - 1
Matrix Generation Loop
Calculate min as the minimum distance to the borders
End
## Program:

```
#include <stdio.h>

int main() {
    int n, i, j;
    printf("Enter a number: ");
    scanf("%d", &n);

    int len = 2 * n - 1;  

    for(i = 0; i < len; i++) {
        for(j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int right = len - 1 - j;
            int bottom = len - 1 - i;

            int min = top;
            if(left < min) min = left;
            if(right < min) min = right;
            if(bottom < min) min = bottom;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/06111757-988e-4c85-bbec-1eb93715e23f)


## Result:
Thus, the program is verified successfully

## EXP NO:10 C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

Start.
Define a function square() with no parameters. This function will return an integer value.
Inside the function: o Declare an integer variable to store the number. o Ask the user to input a number. o Calculate the square of the number (multiply the number by itself). o Return the squared value.
In the main function: o Call the square() function and display the result.
End.
## Program:
```
#include <stdio.h>
int square() {
    int num, result;

    printf("Enter a number: ");
    scanf("%d", &num);

    result = num * num;

    return result;
}

int main() {
    int sq;
    sq = square();
    printf("Square of the number is: %d\n", sq);

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/29aae2ab-b63c-4393-b2f9-1899ca87b326)


## Result: 
Thus, the program is verified successfully

## Module 9 Lab Assignment

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

## Module 10 Lab Assignment

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




## EXP NO:21 PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:

To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```
      #include<stdio.h>
      int max_of_four(int a,int b,int c,int d)
      {
      if(a>b && a>c && a>d)
      {
      return a;
      }
      else if(b>a && b>c && b>d)
      {
      return b;
      }
      else if(c>a && c>b && c>d)
      {
      return c;
      }
      else
      {
      return d;
      }
      }
      int main()
      {
      int n1,n2,n3,n4,greater; 
      scanf("%d%d%d%d",&n1,&n2,&n3,&n4); 
      greater=max_of_four(n1,n2,n3,n4); 
      printf("%d",greater);
      }
```

## Output:

![image](https://github.com/user-attachments/assets/4e36cc21-dceb-48a3-b17c-38330d0340ac)


## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
## EXP NO:22 PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:

To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```
      void calculate_the_max(int n,int k)
      {
      int a=0,o=0,x=0; 
      for(int i=1;i<=n;i++)
      {
      for(int j=1+i;j<=n;j++)
      {
      if((i&j)>a && (i&j)<k)
      {
      a=i&j;
      }
      if((i|j)>o && (i|j)<k)
      {
      o=i|j;
      }
      if((i^j)>x && (i^j)<k)
      {
      x=i^j;
      }
      }
      }
      printf("%d\n%d\n%d\n",a,o,x);
      }
      int main()
      {
      int n,k; 
      scanf("%d%d",&n,&k); 
      calculate_the_max(n,k);
      }

```
## Output:


![image](https://github.com/user-attachments/assets/84670585-2f3b-4a51-ae30-8ceab71d1faf)


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
## EXP NO:23 PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:

To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:

```
      #include<stdio.h> int main()
      {
      int noshel,noque; 
      scanf("%d%d",&noshel,&noque); 
      int shelarr[noshel][noshel];
      int nobookarr[noshel]; 
      int k=0,c=0;
      for(int i=0;i<noque;i++)
      {
      int queno; scanf("%d",&queno); 
      if(queno==1)
      {
      int shelno,nopage; 
      scanf("%d%d",&shelno,&nopage); 
      shelarr[shelno][k]=nopage; 
      nobookarr[shelno]=c+=1;
      k=k+1;
      }
      else if(queno==2)
      {
      int pshelno,pbookno; 
      scanf("%d%d",&pshelno,&pbookno); 
      printf("%d",shelarr[pshelno][pbookno]);
      }
      else if(queno==3)
      {
      int ppshelno; 
      scanf("%d",&ppshelno); 
      printf("%d",nobookarr[ppshelno]);
      }
      }
      }
```

Output:


![image](https://github.com/user-attachments/assets/50f759fb-8f86-405c-bb21-29606b1f4177)



## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
## EXP NO:24 PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:

To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:

```
      #include<stdio.h> 
      int main()
      {
      int n; 
      scanf("%d",&n); 
      int a[n];
      int sum=0;
      for(int i=0;i<n;i++)
      {
      scanf("%d",&a[i]); 
      sum=sum+a[i];
      }
      printf("%d",sum);
      }

```
## Output:

![image](https://github.com/user-attachments/assets/f6e8b4c5-80b0-43df-a6a9-9fb79deba764)


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.

 
## EXP NO 25 PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE

## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```
     #include<stdio.h>
     #include<string.h>
     int main()
     {
         char str[100];
         fgets(str,sizeof(str),stdin);
         int len=sizeof(str);
         int count=1;
          for(int i=0;i<len-1;i++){
              if(str[i]==' ')
              count++;
              
          }
          printf("Total number of words in the string is :%d",count);
         return 0;
     }

```
## Output:

![image](https://github.com/user-attachments/assets/b87e870b-04f9-4812-bbc8-d6762d222d3b)


## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.



## EXP NO 26 PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:


      struct Node
      {
      int data;
      struct Node *next;
      }*head;
      void display()
      {
      struct Node *p; p=head; while(p!=NULL)
      {
      printf("%d\n",p->data); p=p->next;
      }
      }


## Output:

![image](https://github.com/user-attachments/assets/ed3fa147-5c7b-4942-a71c-9f2f171134e6)



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



## EXP.NO :27 PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:

     struct Node
     {
     int data;
     struct Node *next;
     }*head; void pop()
     {
     if(head==NULL)
     {
     printf("stack is empty");
     }
     else
     {
     head=head->next;
     }
     }


## Output:

![image](https://github.com/user-attachments/assets/edde0fba-5b7e-4521-bc6a-3b66b304543d)




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
## EXP NO:28 PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

      struct Node
      {
      char data;
      struct Node *next;
      }*front=NULL,*rear=NULL; 
      void display()
      {
      if(front==NULL)
      {
      printf("queue is empty");
      }
      else
      {
      printf("queue elements:\n"); 
      while(front!=NULL)
      {
      printf("%c\n",front->data); 
      front=front->next;
      }
      }
      }


## Output:

![image](https://github.com/user-attachments/assets/3bf496e0-95d9-489b-a3a3-09bfbeea94e3)


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
## EXP NO:29 PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:


     struct Node
      {
      int data;
      struct Node *next;
      }*front=NULL,*rear=NULL; 
      void enqueue(int data)
      {
      struct Node *p=(struct Node*)malloc(sizeof(struct Node)); 
      p->data=data;
      p->next=NULL; 
      if(front==NULL)
      {
      front=rear=p;
      }
      else
      {
      rear->next=p; 
      rear=p;
      }
      }


## Output:

![image](https://github.com/user-attachments/assets/c7d8a2b4-a8a9-4c1d-8d4a-84adac1cc60c)


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



## EXP NO:30 FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:

      struct Node
      {
         char data;
         struct Node *next;
      }*front=NULL,*rear=NULL;
      void peek()
      {
          printf("%c",front->data);
      }


## Output:


![image](https://github.com/user-attachments/assets/bea488b0-ba1b-486c-a771-6b9e1f56f319)



## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
