# Experiment-9
# Name-Pratyush Saha
# Prn-24070123078
Pointers are a powerful feature in C++ that allow you to directly work with memory addresses.

📌 What is a Pointer?

A pointer is a variable that stores the memory address of another variable.

🧠 Basic Syntax
type* ptr; // Or: type *ptr;


type is the type of data the pointer will point to.

* declares a pointer.

& (address-of operator) gets the memory address.

* (dereference operator) accesses the value at the address.

✅ Example: Basic Pointer
#include <iostream>
using namespace std;

int main() {
    int x = 42;
    int* ptr = &x;

    cout << "Value of x: " << x << endl;
    cout << "Address of x: " << &x << endl;
    cout << "Pointer ptr holds: " << ptr << endl;
    cout << "Value pointed to by ptr: " << *ptr << endl;

    return 0;
}

🧪 Common Pointer Operations
Operation	Example	Meaning
&x	Address of x	Gives memory address of variable
*ptr	Dereferencing	Access value at the memory address
ptr = &x	Point to x	Store address of x in pointer
📚 Pointer with Arrays
int arr[3] = {10, 20, 30};
int* p = arr;

cout << *p << endl;     // 10
cout << *(p + 1) << endl; // 20


Arrays and pointers are closely related: arr is essentially a pointer to the first element.

🧵 Pointer with Strings
char* str = "Hello"; // C-style string
cout << str << endl;


Note: This is a pointer to a string literal; modifying it is undefined behavior. Use char str[] = "Hello"; for mutable strings.

🔁 Pointers and Functions

Pointers are used to pass variables by reference, allowing functions to modify the original value.

void modify(int* p) {
    *p = 100;
}

int main() {
    int x = 10;
    modify(&x);
    cout << x << endl; // 100
}

⚠️ Common Mistakes

Uninitialized pointer:

int* p; // dangerous if used without initialization


Dangling pointer: Points to memory that has been deleted or gone out of scope.

Memory leaks: When new is used without delete.

📌 Bonus: Dynamic Memory Allocation
int* p = new int;     // Allocates memory for one int
*p = 50;

delete p;             // Free the memory


For arrays:

int* arr = new int[5];
// use arr[0] to arr[4]
delete[] arr;         // Free the memory
