# CPP_Notes

A brief collection of curated notes created for those who want to learn C++.

## Authors

- [@ch3tan_bug](https://www.linkedin.com/in/chetan-kashyap)

## Introduction
Created by Bjarne Stroustrup in 1974 as an extension of C language.
### Why to use-
1. `fast execution`
2. `more control over system resources`
3. `memory management`
4. `High performance`

Major changes happened in c++ in 2011 2014 2017

### Basic structure of a C++ program
```cpp
    #include <iostream>  // header files (iostream used for mainly input ouput operations)
    using namespace std; // indicates that the object cin and cout are defined inside the namespace whose name is std
    int main(){          // main() is entry point of any program and int is return type that tells what type of value will be returned
        cout<<"Hello World";
        return 0;        // 0 indicates successfull termination of program
    }    
```

## Variables & Comments
1. Low level - near to hardware  // like the language of 0s and 1s
2. High level - more logically sound and far from hardware // like simple english

`Variables` - containers to store data

`Comments(//)`- Generally done to improve redability of the program & computer doesn't executes it

`single line comment` - //

`multi-line comment` - /* anything */

### Syntax to create Variable
```cpp
        datatype variable name = value;
        int a =6;
```

## Datatypes
Type of data a variable can hold

1. Built-in datatype
    1. `int` - integer (1,0,8)
    2. `Float` - 3.4,-5.6
    3. `Char` - 'a','b'
    4. `Double` - more precision than float 5.667657
    5. `Boolean` - true or false (prints 1 if true 0 if false)
```cpp    
        bool a=true;
        cout<<a;  // will print 1
```        
2. Userdefined Datatypes
    1. `struct` 
    2. `Union`
    3. `Enum`
3. Derived Datatypes
    1. `Array`
    2. `Function` 
    3. `Pointers`
    
### Scope(Region in which the variable exists)-
1. Local Variables - Local variables are declared inside the braces `{}` of any function and can be accessed only from there
    
2. Global Variables - Global variables are declared outside any function and can be accessed from anywhere
we can have the same name for local and global variables but presedence will be given to local variable first.
    
Example-
```cpp    
        #include<iostream>
        using namespace std;;
        int global=6;  // global variable
        void glo(){
            cout<<global
        }
        int main(){
            int global=7;  // local variable
            cout<<global;  // will print 7
            glo()   // calling funtion will print 6
            return 0;
        }
```        

### Rules to declare a variable in C++ -
1. Variable names can range from 1 to 255 characters
2. All must begin with a letter of alphabet or an _(underscore)
3. After the first initial letter variable name can also contain letters and numbers
4. Variable names are case-sensitive
5. No spaces or special characters are allowed
6. Cannot use a reserved keyword for a variable name 

### Basic input/output in C++
In c++ sequence of bytes corresponding to input and output are commonly known as streams
1. `Input stream` - direction of flow of bytes takes place from input device (for ex keyboard) to main memory
2. `Output Stream` - direction of flow of bytes takes place from main memory to output device (ex monitor)

`<<` - called insertion operator // used with cout

`>>` - Extraction operator // used with cin
