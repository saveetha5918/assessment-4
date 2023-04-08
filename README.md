# include < stdio.h >
# include < conio.h >
struct  player
{
char name[20] ;
int runs ;
} ;

int  main( )
{
int i, s = 0 ;
struct player a[11] ;
printf("\n Enter Name of Player Runs Scored \n") ;
printf(" ---------------------------------------------\n") ;
for(i = 0; i <= 10; i++ )
{
      printf(" Enter %d Player Name : ", i + 1) ;
      scanf("%s",a[i].name) ;
      printf(" Enter %d Player Runs : ", i + 1) ;
      scanf("%d",&a[i].runs);
}
for(i = 0; i<=10; i++ )
      s = s + a[i].runs ;

printf("\n ---------------------------------------------\n") ;
printf("\n Runs Scored by Player \n") ;
printf(" Name \t\tRuns\n") ;
for(i = 0; i <= 10; i++ )
{
      printf(" %s \t\t%d\n", a[i].name, a[i].runs) ;
}
printf(" Total Runs Scored by Team: %d", s) ;
return 0 ;
}
















@@ -0,0 +1,33 @@
# include < stdio.h >
# include < conio.h >
struct  student
{
int roll_num ; char name[20] ; struct Date
{
      int D ;
      int M ;
      int Y ;
} bd, ad ;
} ;

int  main( )
{
int r ;
struct student a ;
printf("\n Enter Student Details\n" ) ;
printf("----------------------------------------------------\n" ) ;
printf(" Enter Roll-Number : ") ;
scanf("%d", &a.roll_num ) ;
printf(" Enter Name : " ) ;
scanf("%s",a.name ) ;
printf(" Enter Birth-Date : ") ;
scanf("%d-%d-%d", &a.bd.D, &a.bd.M, &a.bd.Y ) ;
printf(" Enter Admission-Date : ") ;
scanf("%d-%d-%d", &a.ad.D, &a.ad.M, &a.ad.Y) ;
r = a.ad.Y-a.bd.Y ;
printf("----------------------------------------------------\n") ;
printf("\n Approximate Age of Student at the Time of Admission\n") ;
printf("----------------------------------------------------\n") ;
printf("\t%d Years", r) ;
return 0 ;
}










@@ -0,0 +1,42 @@
#include<stdio.h>
/* Defining Structre*/
struct bank
{
     int acc_no;
     char name[20];
     int bal;
}b[3];
void check(struct bank b[],i
{
     int i;
     printf("\nCustomer Details whose Balance < 100 Rs. \n");
     printf("----------------------------------------------\n");
     for(i=0;i<n;i++)
     {
          if(b[i].bal<100)
          {
               printf("Account Number : %d\n",b[i].acc_no);
               printf("Name           : %s\n",b[i].name);
               printf("Balance        : %d\n",b[i].bal);
               printf("------------------------------\n");
          }
     }
}
int main()
{
     int i;
     for(i=0;i<3;i++)
     {
          printf("Enter Details of Customer %d\n",i+1);
          printf("------------------------------\n");
          printf("Enter Account Number : ");
          scanf("%d",&b[i].acc_no);
          printf("Enter Name           : ");
          scanf("%s",b[i].name);
          printf("Enter Balance        : ");
          scanf("%d",&b[i].bal);
          printf("------------------------------\n");
     }
     check(b,3);           
     return 0;
}











@@ -0,0 +1,48 @@
#include <stdio.h>
#include <stdlib.h>

struct Employee 
{
    int eno;
    char ename[100];
    float salary;
};

int main() 
{
    int n, i;
    struct Employee employees[100];

    printf("Enter the number of employees: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) 
	{
        printf("Enter details of employee %d:\n", i+1);

        printf("Enter employee number: ");
        scanf("%d", &employees[i].eno);

        printf("Enter employee name: ");
        scanf("%s", employees[i].ename);

        printf("Enter employee salary: ");
        scanf("%f", &employees[i].salary);
    }
    int max_index = 0;
    float max_salary = employees[0].salary;

    for (i = 1; i < n; i++) {
        if (employees[i].salary > max_salary) 
		{
            max_salary = employees[i].salary;
            max_index = i;
        }
    }
    printf("\nDetails of employee with highest salary:\n");
    printf("Employee number: %d\n", employees[max_index].eno);
    printf("Employee name: %s\n", employees[max_index].ename);
    printf("Employee salary: %.2f\n", employees[max_index].salary);

    return 0;
}











@@ -0,0 +1,87 @@
#include <stdio.h>
#include <string.h>

#define MAX_BOOKS 100

struct Book {
    char title[50];
    char author[50];
    int year;
};

struct Library {
    struct Book books[MAX_BOOKS];
    int count;
};
struct Library {
    struct Book books[MAX_BOOKS];
    int count;
};

void add_book(struct Library *lib) {
    if (lib->count == MAX_BOOKS) {
        printf("Library is full\n");
        return;
    }
    struct Book book;
    printf("Enter book details:\n");
    printf("Title: ");
     scanf("%s", book.title);
    printf("Author: ");
    scanf("%s", book.author);
    printf("Year: ");
    scanf("%d", &book.year);
    lib->books[lib->count] = book;
    lib->count++;
    printf("Book added to the library\n");
}

void display_books(struct Library lib) {
    if (lib.count == 0) {
        printf("No books in the library\n");
        return;
    }
    printf("Books in the library:\n");
    for (int i = 0; i < lib.count; i++) {
        printf("%d. %s, %s (%d)\n", i+1, lib.books[i].title, lib.books[i].author, lib.books[i].year);
    }
}
void list_book_count(struct Library lib) {
    printf("Total number of books in the library: %d\n", lib.count);
}

int main() {
    struct Library lib = {0};
    int choice;
    do {
        printf("\nMenu:\n");
        printf("1. Add book details\n");
        printf("2. Display book details\n");
        printf("3. List all books of given author\n");
        printf("4. List the count of books in the library\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                add_book(&lib);
                break;
            case 2:
                display_books(lib);
                break;
            case 3:
                list_books_by_author(lib);
                break;
            case 4:
                list_book_count(lib);
                break;
            case 5:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice\n");
        }
    } while (choice != 5);
    return 0;
}
0 comments on commit 09a8a20










@@ -0,0 +1,52 @@
#include<stdio.h>
struct student
{
     int rno;
     char name[20];
     int marks[3];
     int total;
     float avg;
}stud[2];
int main()
{
     int i,j;
     struct student s;
     for(i=0;i<2;i++)
     {
      printf("Enter Record for Student-%d \n",i+1);
          printf("\n");
          printf("Enter Roll-No. : ");
          scanf("%d",&stud[i].rno);
          printf("Enter Name: ");
          scanf("%s",stud[i].name);
          stud[i].total=0;
          for(j=0;j<3;j++)
          {
               printf("Enter Marks of Subject %d : ",j+1);
               scanf("%d",&stud[i].marks[j]);
               stud[i].total=stud[i].total+stud[i].marks[j] ;
               stud[i].avg=stud[i].total/3.0;
          }
          printf("\n");
     }
     for(i=0;i<2;i++)
     {
          for(j=i+1;j<2;j++)
          {
               if(stud[i].total<stud[j].total)
               {
                    s=stud[i];
                    stud[i]=stud[j];
                    stud[j]=s;
               }
          }
     }
     printf("Records in Descending Order.\n (According to Total-Marks)");
     printf("\n");
     printf("\n ROLLNO   NAME  TOTAL-MARKS  AVG\n");
     for(i=0;i<2;i++)
     {
          printf("\n %d\t %s\t %d\t %.2f",stud[i].rno,stud[i].name,stud[i].total,stud[i].avg);
     }
     return 0;
}








@@ -0,0 +1,23 @@
#include <stdio.h>

union Data {
    int i;
    float f;
};

int main() 
{
    union Data data;

    printf("Enter an integer value: ");
    scanf("%d", &data.i);

    printf("The value you entered is: %d\n", data.i);

    printf("Enter a float value: ");
    scanf("%f", &data.f);

    printf("The value you entered is: %f\n", data.f);

    return 0;
}










@@ -0,0 +1,24 @@
 #include <stdio.h>
#include <string.h>

union Student 
{
    char name[50];
    float gpa;
};

int main() 
{
    union Student student;

    printf("Enter the student's name: ");
    fgets(student.name, 50, stdin);

    printf("Enter the student's GPA: ");
    scanf("%f", &student.gpa);

    printf("Student's name: %s", student.name);
    printf("Student's GPA: %.2f\n", student.gpa);

    return 0;
}










@@ -0,0 +1,41 @@
#include <stdio.h>
#define PI 3.14159

union Shape 
{
    float radius;
    struct 
	{
        float length;
        float width;
    } 
	rectangle;
};

int main() 
{
    union Shape shape;
    char choice;

    printf("Enter the type of shape you want to calculate (C for circle, R for rectangle): ");
    scanf("%c", &choice);

    if (choice == 'C' || choice == 'c') 
	{
        printf("Enter the radius of the circle: ");
        scanf("%f", &shape.radius);
        printf("Area of the circle is: %.2f\n", PI * shape.radius * shape.radius);
    } 
	else if (choice == 'R' || choice == 'r') 
	{
        printf("Enter the length of the rectangle: ");
        scanf("%f", &shape.rectangle.length);
        printf("Enter the width of the rectangle: ");
        scanf("%f", &shape.rectangle.width);
        printf("Area of the rectangle is: %.2f\n", shape.rectangle.length * shape.rectangle.width);
    } 
	else 
	{
        printf("Invalid choice!\n");
    }
    return 0;







