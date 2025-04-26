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

```

## Output:

//paste your output here

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

```

## Output:

//paste your output here

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

```

## Output:

//paste your output here

## Result:
Thus, the program to display queue elements using array is verified successfully.

## EXP NO:
14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY. Aim: To write a C program to insert elements in queue using array.

## Algorithm:

Declare global variables for the size, rear, front, and the queue itself.
Define the enqueue function to add a float to the queue.
Initialize the rear, front, and size of the queue as needed.
Call the enqueue function as needed.
## Program:
```

```

## Output:

//paste your output here

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

```

## Output:

//paste your output here

## Result: 
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
