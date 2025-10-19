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
    float length, width, area;
    float *ptrLength, *ptrWidth;
    ptrLength = &length;
    ptrWidth = &width;

    printf("Enter length of the rectangle: ");
    scanf("%f", ptrLength);
    printf("Enter width of the rectangle: ");
    scanf("%f", ptrWidth);
    area = (*ptrLength) * (*ptrWidth);
    printf("Area of the rectangle = %.2f\n", area);
    return 0;
}
```
## OUTPUT
![alt text](<output 1.png>)	       	


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
    str = (char *)malloc(8 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    strcpy(str, "WELCOME");
    printf("%s\n", str);
    free(str);
    return 0;
}

```
## OUTPUT
![alt text](<output 2.png>)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 



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
    char name[50];
    int roll;
    float marks;
};

int main() {
    struct Student s;
    fgets(s.name, sizeof(s.name), stdin);
    scanf("%d", &s.roll);
    scanf("%f", &s.marks);

    printf("Name        : %s", s.name);
    printf("Roll Number : %d\n", s.roll);
    printf("Marks       : %.2f\n", s.marks);

    return 0;
}
```
## OUTPUT
![alt text](<output 3.png>)

## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-Electricity Bill Calculation for Multiple Customers Using Structure 

## AIM

To write a C Program to read customer no,prev reading & current reading as input for eb calculation bill for 3 customers(first 100 unit 2 rs per unit,101 to 200 rs.3 per unit and above 200 rs 5 per unit).

## ALGORITHM

1. Start the program.
2. Create an employee structure with name, id, basic salary, hra, da, and gross salary as members.
3. Declare a structure variable to store employee details.
4. Read the employee name, id, basic salary, hra, and da from the user.
5. Calculate gross salary using the formula: gross salary = basic salary + hra + da.
6. Display the employee name, id, basic salary, hra, da, and gross salary.
7. Stop the program.

## PROGRAM
```
#include<stdio.h>
struct Customer {
    int cust_no;
    int prev_reading;
    int curr_reading;
    float bill;};
float calculate_bill(int units){
    float amount = 0.0;
    if(units<=100){
        amount = units*2;}
    else if(units<=200){
        amount=100*2+(units-100)*3;}
    else{
        amount=100*2+100*3+(units-200)*5;}
    return amount;}
int main()
{struct Customer customers[3];
    int i;
    for(i=0;i<3;i++){
        scanf("%d",&customers[i].cust_no);
        scanf("%d",&customers[i].prev_reading);
        scanf("%d",&customers[i].curr_reading);
        int units = customers[i].curr_reading-customers[i].prev_reading;
        customers[i].bill=calculate_bill(units); }
        printf("Details of the EB Customer\n");
        for(i=0;i<3;i++){
            printf("%d      %.2f\n",customers[i].cust_no,customers[i].bill);
        }
    return 0;
}
```
 ## OUTPUT

 ![alt text](<output 4.png>)

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
    char name[50];
    int roll;
    float marks[5];     
    float total;
    float average;
};
int main() {
    struct Student s;
    int i;
    scanf(" %[^\n]", s.name);
    scanf("%d", &s.roll);
    s.total = 0;
    for(i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &s.marks[i]);
        s.total += s.marks[i];
    }
    s.average = s.total / 5;
    printf("Name     : %s\n", s.name);
    printf("Roll No  : %d\n", s.roll);
    printf("Total    : %.2f\n", s.total);
    printf("Average  : %.2f\n", s.average);
    return 0;
}
```
## OUTPUT

 ![alt text](<output 5.png>)

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


