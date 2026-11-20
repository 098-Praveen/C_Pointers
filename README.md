WHAT IS POINTER?
pointer is a variable which can store the address of another variable.
or 
pointers are used to store address of memory location in a ram.

here address represents 
every byte of ram has unique address 
first bytes address is called base address
address is always represented in heaxa decimal form.

size of pointer in 32 bit machine 
in bytes = 4 bytes 
in hexadecimal= 8 hexadigits
in bits= 32 bits

size of pointer in 64 bit machine
in bits = 64 bits
in bytes = 8 bytes
in hexadecimal= 16 hexadigits

how can you access the value at the address without using the variable 
with the help of base address stored in a pointer.

for int
printf("ptr)=== 4 bytes
printf("ptr")===8 bytes

for char 
printf("ptr")==1 byte
printf("*ptr")== 8 bytes

for short
printf("ptr") == 8 bytes
printf("*ptr")== 2 bytes.

int x=50;
int *ptr=&x;

NOTE:
ptr also has an address other than in it.

address of x=3000
address of ptr=4000

what is the value of x? = 50
what is the value of ptr? = 3000
what is &x? = 3000
what is &ptr? = 4000
MODIFICATION THROUGH THE POINTER WITHOUT USING THE VARIABLE:

#include<stdio.h>
int main()
{
  int a=10;
  int *p=&a;
     
  *p=50;
  printf("%d\n",*p);
  a=100;
  printf("%d",*p);
}



POINTER ASSIGNMENT AND VALUE ASSIGNMENT:
int a = 10;
int b = 20;

int *p = &a;
int *q = &b;

a address = 1000
b address = 2000
p address = 3000
q address = 4000

p = q;

What is the value of p now? = address of b
What is the value of *p now? = 20
Did the value of a change? = no
Did the value of b change? = no 
What is the difference between p = q and *p = *q?
p=q address is assigned
*p=*q value is assigned

TWO POINTERS POINTING TO THE SAME VARIABLE:

int a = 10;

int *p = &a;
int *q = &a;

*p = 50;

printf("%d\n", a);
printf("%d\n", *q);

What is the first output? = 50
What is the second output? = 50
Why does modifying *p affect the value accessed through *q? cause points to same location.

CHANGING POINTERS TARGET:
int a = 10;
int b = 20;

int *p = &a;
P POINTS TO A 
p = &b;
NOW P POINTS TO B

HERE ONLY THE ADDRESS CHANGES IN P BUT THE VALUES REMAINED IN A AND B

int a = 10;
int b = 20;

int *p = &a;

*p = 30;

p = &b;

*p = 40;

a= 30
b=40
*p=40
*p points to b

POINTER DECLARATION AND INITIALIZATION:
DECLARATION:
int *p;
creates a pointer variable but doesn't initialize it.
INITIALIZATION:

int a=10;
int *p=&a;

CREATE A POINTER AND INITIALIZES IT WITH THE ADDRESS OF A.
3. ASSIGNMENT:

int b=20;
p=&b;
changes the address stored in p

IS THIS VALID:
int *p;
*p=100

here we are not giving any valid address so it is undefined behavior bcz we it points to invalid memory location
to fix
int a;
*p=&a;
*p=100;

OR METHOD 2:
int *p=NULL

and again never deference that null pointer if do so then undefined behavior.
POINTER AND VARIABLE RELATIONSHIP:

int a = 10;
int b = 20;

int *p = &a;

*p = 30;

int *q = p;

*q = 40;

p = &b;

*p = 50;

a = ? = 40
b = ? = 50
*p = ? = 50
*q = ? = 40
Which variable does p point to? = b
Which variable does q point to? = a

POINTER TYPES:
int a = 10;
char b = 'A';
float c = 10.5;

int *p1 = &a;
char *p2 = &b;
float *p3 = &c;

int *  access the int value
char * access the char value
float * access the float values

but what like 
int a=10
int *p=&a;
char *p=&a;

DOES THE POINTER TYPE AFFECT POINTER ARITHEMATIC?
int a=10;
int *p=&a;
here p++:
oxa00---oxa004

char b='A':
char *q=&b;
p++ means oxa000 to oxa001

pointer arithmetic formula
address + sizeof(data type)

POINTER TYPES AND TYPE COMPATIBILITY:
int a = 10;
int *p = &a;
char *q = &a;
first was right and second declaration is error 
because q is a character pointer and &a is an integer pointer
DIFFERENT POINTER TYPES ARE NOT AUTOMATICALLY INTERCHANGEBLE

char *q=(char *)&a;

here we are not changing the int to character object
but converting to pointer type to char







