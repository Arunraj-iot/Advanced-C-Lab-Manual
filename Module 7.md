EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim: To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
```

1. Declare structure eligible with age (integer) and n (character array)
2. Declare variable e of type eligible
3.Input age and name using scanf, store in e
4. If e.age <= 6
5. Print "Vaccine Eligibility: No" Else
6. Print "Vaccine Eligibility: Yes"
7. Print details (e.age, e.n)
8. Return 0
```
Program:
```
#include <stdio.h>
struct eligible {
    char name[50];
    int age;
};

int main() {
    struct eligible e[10];
    int n, i;

    printf("Enter number of persons: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        printf("\nEnter name: ");
        scanf("%s", e[i].name);
        printf("Enter age: ");
        scanf("%d", &e[i].age);
    }

    printf("\n--- Vaccine Eligibility ---\n");
    for(i = 0; i < n; i++) {
        printf("\nName: %s", e[i].name);
        printf("\nAge : %d", e[i].age);

        if(e[i].age > 6)
            printf("\nEligible for Vaccine\n");
        else
            printf("\nNot Eligible for Vaccine\n");
    }

    return 0;
}
```
Output:
```

Enter number of persons: 3

Enter name: Ravi
Enter age: 5

Enter name: Meena
Enter age: 8

Enter name: Karan
Enter age: 6

Vaccine Eligibility 

Name: Ravi
Age : 5
Not Eligible for Vaccine

Name: Meena
Age : 8
Eligible for Vaccine

Name: Karan
Age : 6
Not Eligible for Vaccine
```
Result: Thus the program is verified successfully.


EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION Aim: To write a C program for passing structure as function and returning a structure from a function

Algorithm:
```

1. Define structure numbers with members a and b.
2. Declare variable n of type numbers.
3. Prompt the user to enter values for a and b.
4. Input values for a and b into n using scanf.
5. Call the add function with n as an argument.
6. Print the result returned by the add function.
7. Return 0
```
Program:
```

#include <stdio.h>

// Structure definition
struct numbers {
    int a;
    int b;
};

struct numbers add(struct numbers n) {
    struct numbers result;
    result.a = n.a + n.b;  
    result.b = 0;          
    return result;
}

int main() {
    struct numbers n1, res;

    printf("Enter two numbers: ");
    scanf("%d %d", &n1.a, &n1.b);

    res = add(n1);

    printf("Sum = %d\n", res.a);

    return 0;
}
```
Output:
```

Enter two numbers: 10 20
Sum = 30
```
Result: Thus, the program is verified successfully


EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim: To write a C program to read a file name from user

Algorithm:
```
1. Include the necessary header file stdio.h.
2. Begin the main function.
3. Declare a file pointer p. Declare a character array name to store the file name.
4. Prompt the user to enter a file name. Use scanf to input the file name into the name array.
5. Print a message indicating that the file with the specified name has been created successfully.
6. Use fopen to open a file with the name provided by the user in write mode ("w").
7. If successful, continue to the next step.
8. If unsuccessful, print an error message and exit the program with a non-zero status.
9. Print a message indicating that the file has been opened successfully.
10. Use fclose to close the file.
11. Print a message indicating that the file has been closed.
12. End the main function.
13. Return 0 to indicate successful program execution.
```
Program:
```
#include <stdio.h>

int main() {
    FILE *p;
    char name[50];

    printf("Enter the file name: ");
    scanf("%s", name);

    // Open file in write mode
    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error! Cannot create file.\n");
        return 1;
    }

    printf("File '%s' created successfully.\n", name);
    printf("File opened successfully for writing.\n");

    fprintf(p, "This is a sample text written into the file.\n");

    fclose(p);
    printf("File closed successfully.\n");

    return 0;
}
```
Output:
```
Enter the file name: sample.txt
File 'sample.txt' created successfully.
File opened successfully for writing.
File closed successfully.
```
Result: Thus, the program is verified successfully


EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 

Aim: To write a C program to read, a file and insert text in that file 

Algorithm:
```
1. Include the necessary header file stdio.h.
2. Begin the main function.
3. Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
4. Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
5. Use fopen to open a file with the name provided by the user in write mode ("w").
6. If successful, continue to the next step.
7. If unsuccessful, print an error message and exit the program with a non-zero status.
8. Print a message indicating that the file has been opened successfully.
9. Use a loop to input strings from the user and write them to the file using fputs.
10. Use fclose to close the file.
11. Print a message indicating that data has been added successfully.
12. End the main function.
13. Return 0 to indicate successful program execution.
```
Program:
```
#include <stdio.h>

int main() {
    FILE *p;
    char name[50], text[100];
    int num, i;

    printf("Enter file name: ");
    scanf("%s", name);

    printf("Enter number of lines to write: ");
    scanf("%d", &num);

    // Open file in write mode
    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error! Cannot create or open file.\n");
        return 1;
    }

    printf("\nFile '%s' opened successfully.\n", name);

    for (i = 0; i < num; i++) {
        printf("Enter text line %d: ", i + 1);
        scanf(" %[^\n]", text);   
        fputs(text, p);
        fputs("\n", p);          
    }

    fclose(p);
    printf("\nData added successfully to file '%s'.\n", name);

    return 0;
}
```
Output:
```
Enter file name: notes.txt
Enter number of lines to write: 3

File 'notes.txt' opened successfully.
Enter text line 1: COVID vaccine drive starts today
Enter text line 2: Students must register online
Enter text line 3: Carry your ID card for verification

Data added successfully to file 'notes.txt'.
```
Result: Thus, the program is verified successfully


Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim: The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm: 
```
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
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    struct subject *s;
    int n, i;

    printf("Enter number of subjects: ");
    scanf("%d", &n);

    // Dynamic memory allocation
    s = (struct subject *)malloc(n * sizeof(struct subject));

    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    for (i = 0; i < n; i++) {
        printf("\nEnter subject name: ");
        scanf("%s", s[i].name);
        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }

    // Display subject details
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject: %s\tMarks: %d\n", s[i].name, s[i].marks);
    }
    free(s);

    return 0;
}
```
Output:
```
Enter number of subjects: 3

Enter subject name: Maths
Enter marks: 85

Enter subject name: Science
Enter marks: 90

Enter subject name: English
Enter marks: 88

--- Subject Details ---
Subject: Maths     Marks: 85
Subject: Science   Marks: 90
Subject: English   Marks: 88
```
Result: Thus, the program is verified successfully
