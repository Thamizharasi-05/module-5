# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int length, breadth, area;
    int *p1, *p2;

    printf("Enter the length and breadth of the rectangle: ");
    scanf("%d %d", &length, &breadth);

    p1 = &length;
    p2 = &breadth;

    area = (*p1) * (*p2);
    printf("Area of rectangle = %d\n", area);

    return 0;
}
```
## OUTPUT
		       	
![Screenshot 2025-04-30 135800](https://github.com/user-attachments/assets/1b475ef4-4548-480a-9ce6-259ffab6421d)

## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str;

    str = (char *)malloc(10 * sizeof(char)); // allocate memory
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    strcpy(str, "WELCOME");
    printf("%s\n", str);

    free(str); // free allocated memory
    return 0;
}
```
## OUTPUT

![Screenshot 2025-04-30 135936](https://github.com/user-attachments/assets/0d92800b-741f-4c9d-ac73-a06b9e225f0d)

## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    char name[20];
    int rollNo;
    float marks;
};

int main() {
    struct Student s;

    printf("Enter student name, roll number, and marks: ");
    scanf("%s %d %f", s.name, &s.rollNo, &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\nRoll No: %d\nMarks: %.2f\n", s.name, s.rollNo, s.marks);

    return 0;
}
```
## OUTPUT

![Screenshot 2025-04-30 140206](https://github.com/user-attachments/assets/1f711593-41d9-4498-9063-7067a2c6b711)

## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Employee {
    char name[20];
    int id;
    float basic, hra, da, gross;
};

int main() {
    struct Employee emp[3];
    int i;

    for(i = 0; i < 3; i++) {
        printf("Enter name, ID, basic, HRA, and DA for employee %d: ", i+1);
        scanf("%s %d %f %f %f", emp[i].name, &emp[i].id, &emp[i].basic, &emp[i].hra, &emp[i].da);
        emp[i].gross = emp[i].basic + emp[i].hra + emp[i].da;
    }

    printf("\nEmployee Details:\n");
    for(i = 0; i < 3; i++) {
        printf("Name: %s | ID: %d | Gross Salary: %.2f\n", emp[i].name, emp[i].id, emp[i].gross);
    }

    return 0;
}

```

 ## OUTPUT

 ![Screenshot 2025-04-30 140401](https://github.com/user-attachments/assets/d297bd45-df54-45e4-ad02-a06f89069df8)

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
    float average;
};

int main() {
    struct Student s[2];
    int i, j;

    for(i = 0; i < 2; i++) {
        printf("Enter name and roll number for student %d: ", i + 1);
        scanf("%s %d", s[i].name, &s[i].rollno);

        s[i].total = 0;
        printf("Enter 5 subject marks: ");
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
            s[i].total += s[i].subject[j];
        }

        s[i].average = s[i].total / 5.0;
    }

    for(i = 0; i < 2; i++) {
        printf("\nStudent: %s\nTotal: %d\nAverage: %.2f\n", s[i].name, s[i].total, s[i].average);
    }

    return 0;
}
```

## OUTPUT

 ![Screenshot 2025-04-30 140608](https://github.com/user-attachments/assets/c420e035-6ab0-4c69-9fd2-330a67319e37)

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


