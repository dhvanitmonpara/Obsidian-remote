# Pointers 

Data type which holds the address of other data types.

```cpp
    int a=3;
    int* b;
    b = &a;

    cout<<"The value at address b is "<<*b<<endl;
    cout<<"The value at address b is "<<b<<endl;

```

In above code, when you use `b` it defines and prints address of `a` but when you use `*b` it points to `a` and prints value of `a`, so use `*b` instead of `b`.

Simply run this code if you want to understand pointers.

```cpp
#include <iostream>
using namespace std;

int main(){

    int a=10;
    int*b = &a;

    cout<<endl<<"This is a => "<<a;
    cout<<endl<<"This is &b => "<<&a;
    cout<<endl<<"This is b => "<<b;
    cout<<endl<<"This is *b => "<<*b;
    cout<<endl<<"This is &b => "<<&b<<" (You can ignore this btw, this is just address of b which is not useful to you)";

    return 0;
}
```

# Pointer to pointer

```cpp
    int** c = &b;
    cout<<"The address of b is "<<&b<<endl;
    cout<<"The address of b is "<<c<<endl; 
    cout<<"The value at address c is "<<*c<<endl; 
    cout<<"The value at address value_at(value_at(c)) is "<<**c<<endl; 
```
