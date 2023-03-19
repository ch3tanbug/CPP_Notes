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

## Operator in c++
There are 2 types of header files
1. System Header files - it comes with compiler
2. User defined header files - it is written by programmer
3. 
- we can even use "n" or cout<<endl // to create a new line

### Arithmetic operators-
1. `Addition +`
2. `Subtraction -`
3. `Multiplication *`
4. `Division /`
5.`Modulo %`
6. `Increment and Decrement a++ a-- --a ++a`

### Assignment operators
1. `=`

### Comparision operators
1. `==`  exact equal
2. `>=` greater than equal
3. `<=` less than equal
4. `>` greter than
5. `<` less than
6. `!=` not equal

### Logical operator
1. `&&` - and
2. `||` - or 
3. `!` - not

## Reference variables and typecasting
1. :: - this is called scope resolution operator and is used to call the value of global variable in case both local and global have same name
```cpp
        cou<<:a   // here global a is called
        // by default and point number like 34.6 in c++ is considered as double to chnage to float we can use 
        // 34.6f similarly 34.6l means long double
```        
2. & - is used to point a variable for Reference
```cpp
        a=16
        &b=a   // both will contain 16
```        
3. Typecasting - changing the datatype of 1 variable at runtime
```cpp
        int a=6
        cout<<(float)a; or
        cout<<float(a)       // both will work the same we can use any datatype like int char
```        

## Constants manipulators & operator presendence
```cpp
const int a =3; // value can't be changed throughout the program
```

Manipulators helps us in formatting the data-display
1. `endl` - prints new line
2.`#include<iomanip>` contains a manipulator setw // use to right align the data in display
Example -
```cpp
            #include <iostream>
            #include <iomanip>
            using namespace std;
            int main(){
                cout<<setw(4)<<34;  // here(4) means no of spaces
                return 0;
            }
```            
3. Presedence means like `*` is evaluated before `+` and associativity means when presedence is same the expression is either evaluated from right to left or left to right

### Control Structures  
To give flow and logic to program
1. Sequence structure - to perform no of actions in sequence
2. Selection structure - to perform action based on condition 
3. Loop structure - to perform action based on conditon and loop till condition satisfies

```cpp
    // if-else statement
        if(i==3){
            cout<<i;
        }
```    
- Switch case-
```cpp
        switch(expression){
            case 1:{
            code ;
            break;}

            case 2:{
            code;
            break;}

            default:{
            code;}
        }
```        

- If-else ladder
```cpp
        elseif(expression){
            code 
        }
```

## Loops
1. For Loop 
```cpp
        for(int i =0;i<4;i++){
            code
        }
```        
2. While Loop
```cpp 
        int i=1
        while(i<4){
            code;
            i++;
        }
```        
3. Do While Loop (atleast executes one time)
```cpp
        int i=1;
        do{
            code;
            i++;
        }
        while(i<4);
```

## Break & Continue
1. break (exits the loop or code)
```cpp
        if(i==2){
            break;
        }
```        
2. continue (skips current iteration)
```cpp
    if(i==2){
        continue;
    }
```
## Pointers
It is a datatype which stores the address of other variables.
- `&` = address of operator
- `*` = dereference operator
Example-
```cpp
        #include<iostream>
        using namespace std;

        int main(){
            int a,*p;
            a=5;
            p=&a;
            cout<<"address of a is : "<<p;
            cout<<"value of a is : "<<*p;
            return 0;
        }
```        
Pointer to Pointer
```cpp
        int **c=&p;
        // here c will store address of p
        // here *c will store the the thing inside p i.e address of variable p has stored
        // here **c will finally store the value of the variable of which p has stored address
```        
        
## Arrays
Array is a collection of items of similar type stored in contiguous memory locations
```cpp
        datatype arryname[size]={elements};
        int arry1[4]={32,56,76,30};
        arry1[2]=45; // changing the values in array
```

### Arrays and Pointers
Pointer Arithmetic
    - address new = address used + (i*size of datatype);
Example-
```cpp
            #include<iostream>
            using namespace std;

            int main(){
                int arry1[4]={1,2,3,4};
                int *p;
                p=arry1;           // we cannot assign an array to pointer with & to store address
                cout<<"adress of value "<<*p<<" "<<p<<endl;
                cout<<"adress of value "<<*(p+1)<<" "<<p+1<<endl; // *(p+1) is done to move to next element in array
                cout<<"adress of value "<<*(p+2)<<" "<<p+2<<endl;
                return 0;
            }
```

## Structures , Unions & Enums
1. Structure - a user defined datatype that can store heterogeneous data
```cpp
        struct employee{
            int eid;
            char favchar;
            float salary
        };
        struct employee chetan;
        chetan.eid=4;
        chetan.favchar='c';
        chetan.salary=23000000322.32;

                 //  or
                 
        typedef struct employee{       // using typedef for shorcut
        int eid;
        char favchar;
        float salary
        }ep;                          // wrote ep as shortcut
        ep chetan;                    // now we dont have to write struct employee chetan
        chetan.eid=4;
        chetan.favchar='c';
        chetan.salary=23000000322.32;
```    
2. Union - same as structure but based on shared memory model the memory of highest datatype is allocated and then overwritten each time with new value for sharing.

Example-
```CPP
        union money{
            int currency;
            char car;
            int grain;
        };
        union money chetan1;
        chetan1.currency=4;
        chetan1.car='c';
        cout<<chetan1.currency    // will show garbage value due to overwritten property car;
```

3. Enum -  data type consisting of named values like elements, members, etc., that represent integral constants typically used to improve program redability.

Example-
```cpp
        enum meal{breakfast,lunch,dinner};
        meal m1=breakfast;   // prints 0
        meal m2=lunch;       // prints 1
        meal m3=dinner;      // prints 2
```
### Fuctions & Function prototypes
Syntax-
```cpp
        int sum(int a,int b){
            int c=a+b;
            return c;
        }
```    
### Function prototypes 
Used when you declare the function after calling it then prototype can be used above before calling to refer to function and avoid error.

```cpp
        type function-name (arguments);
        int sum(a,b);       // not acceptable
        int sum(int a,int b);       // acceptable
        int sum(int,int);       // acceptable
```
Example-
```cpp
            #include<iostream>
            using namespace std;

            int main(){
                int num1,num2;
                int sum(int a,int b);     // prototype is used here to refer to the function
                cout<<"enter value of no 1 ";
                cout<<"enter value of no 2 ";
                cin>>num1>>num2;
                cout<<sum(num1,num2);
                return 0;
            }
            int sum(int a,int b){
                int c=a+b;
                return c;
            }
```
- Formal parameters are the parameters which we write while writing functions like `sum(int a,int b)`
- Actual parameters are the parameters which we pass in function while callng like `sum(4,5)`
- NOTE - formal parameters take values from actual parameters and perform the task

## Call by value & Call by Reference
1. Call by reference using c++ reference operator (&)
```cpp
        #include<iostream>
        using namespace std;


        int main(){
            int a,b;
            cout<<"Enter number 1";
            cout<<"Enter number 2";
            cin>>a>>b;
            swap(a,b);
            cout<<"new value of a & b are "<<a<<b;
            return 0;
        }
        void swap(int &x,int &y){    // here &x and &y are pointing to memory of a and b through & reference operator
            int temp=x;
            x=y;
            y=temp;
        }
```    
2. Call by reference using Pointers
```cpp
        #include<iostream>
        using namespace std;

        void swap(int *x,int *y);
        int main(){
            int a,b;
            cout<<"Enter number 1";
            cout<<"Enter number 2";
            cin>>a>>b;
            swap(&a,&b);
            cout<<"new value of a & b are "<<a<<b;
            return 0;
        }
        void swap(int *x,int *y){        // using dereference operator to change value at address
            int temp=*x;
            *x=*y;
            *y=temp;
        }
```    
3. Return by reference
```cpp
                #include<iostream>
                using namespace std;

                int & swap(int &x,int &y);
                int main(){
                    int a,b;
                    cout<<"Enter number 1";
                    cout<<"Enter number 2";
                    cin>>a>>b;
                    swap(a,b)=66;  // here we are assigning 66 to the reference of a i.e &x
                    cout<<"new value of a & b are "<<a<<b;
                    return 0;
                }
                int & swap(int &x,int &y){    // here &x and &y are pointing to memory of a and b through & reference operator
                    int temp=x;
                    x=y;
                    y=temp;
                    return x;        // because here x is returned which is the reference of a 
                }                    // we use int & swap while creating function because to tell it function will return a reference value 
```                

## Inline functions (reduces time for execution)
When we maeke a function inline the the function call is replaced by the the actual code inside the function
never use inline function when you make too many calls to a function as it will increase its size and thus the motive 
of function is destroyed.
    
```cpp
    inline int produ(int a,int b){
        return a*b;
    }

    int main(){
        produ(4,5) // here the call is replaced by actual code given above
    }
```

- When static keyword is used, variable or data members or functions can not be modified again.
- It is allocated for the lifetime of program.It is not like other temporary variables in a function it retains 
the value. static variable means the variable will just used one time  in the function.

```cpp
    int product(int a,int b){
    static int c =0;             // is runned only one time
    c++;
    return a*b+c;
    }

Default arguments
    int product(int a,int b=6){               // default arguments should always be to 
    return a*b
    }
```    

You can overwrite the argumets like product(4,5) but if pass only one argument the other argument will be taken from default argument.

### Constant arguments
These are the arguments we pass with the const keyword to tell the compiler that these values should not be changed even accidentaly.

```cpp
     int strlen(const char *p){
        code                               // mostly used with pointers and reference variables
     }
```

## Recursion
When a function calls itself until a specified condition is met.
Example-
```cpp
    #include<iostream>
    using namespace std;

    int factorial(int n){
        if(n<=1){
            return 1;
        }
        return n*factorial(n-1);
    }
    int main(){
        int a;
        cout<<"enter a number ";
        cin>>a;
        cout<<"the factorial is "<<factorial(a);
        return 0;
    }
```
## Function Overloading
When a single name of function is used to perform different tasks
    
Points to remember when doing function Overloading (arguments)-
    - They should have a different type
    - They should have a different number 
    - They should have a different sequence of parameters.

Example-
```cpp
        int volume(int n){
            return n*n*n;
        }
        int volume(int n,int m){
            return(3.14*n*n*m)
        }
        int main(){
            cout<<"volume of cube is "<<volume(3);
            cout<<"volume of cylinder is "<<volume(3,6);
        }
```

## Procedure Oriented Programming(POP)
1. Consists of writing a set of instructions for the computer to follow.
2. Main focus is on functions and not the flow of data.
3. Functions can either use local or global data.
4. Data moves openly from function to function.


##  Object Oriented Programming in C++(OOPs)
1. Works on the concept of classes and objects
2. A class is a template to create objects.
3. Treats data as a critical element.
4. Decomposes the problem in objects and builds data and functions around the objects

## Basic concepts in Object oriented Programming
1. `Classes` - basic templates for creating objects
2. `Objects` - basic runtime entities
3. `Data abstraction and encapsulation` - wrapping data and functions into single unit 
4. `Inheritance` - Properties of one class can be inherited to others.
5. `Polymorphism` - ability to take more than one forms
6. `Dynamic binding` - code which will execute is unknown until the program runs 
7. `Message Passing` - Object.message (information) call format

### Benifits-
1. Better code reusability using object and Inheritance
2. Principle of data hiding helps build secure systems
3. Multiple objects can co-exist without any interference
4. Software complexity can easily be managed

## Classes, Public and Private access modifiers
Syntax-
```cpp
        class employee{
            private:              
            int a,b,c;
            public:
            int d,e;
            void setdata(int a1,int a2,int a3);             // prototype inside class
        }
        void employee :: setdata(int a1,int b1, int c1){         // we are refrencing function to class to avoid clash between two same name functions using ::(scope resolution operator)
                code 
        }
```

- Private variables can only be accessed by functions inside a class and we can't set them like `obj.name="anything"` can only set them through functions inside class

- C++ intitially called C with classes by stroutstroup
    1. `class` --> extension of structures in C
    2. `structure had limitations` -->
        members are public
        No methods
    3. `classes` --> classes can have methods and Properties and can make few members as private and public


## Nesting of Member Functions

1. `exit(0)` -> used to exit a program on certain condition generally used with if-else or loops.
2. `string.at(index)` --> used to extarct characters from string by inptutting index can be used after importing #include<string> libraray

Example -
```cpp    
    #include<iostream>
    #include<string>

    using namespace std;

    class binary{
        string s;
        void checkbin(void);
        public:
        void read(void);
        void onecomp(void);
        void display(void);
        };

    void binary :: read(void){
        cout<<"Enter a binary number "<<endl;
        cin>>s;
    }

    void binary :: checkbin(void){
        for(int i=0;i<s.length();i++){
            if(s.at(i)!='0' && s.at(i)!='1'){
                cout<<"Enter a valid binary number "<<endl;
                exit(0);
            }
        }
    }

    void binary :: onecomp(void){
        checkbin();                         // here we nested a private function and now this cannot be called from main like obj.checkbin()
        for(int i=0;i<s.length();i++){
            if(s.at(i)=='0'){
                s.at(i)='1';
            }
            else{
                s.at(i)='0';
            }
        }
    }

    void binary :: display(void){
        for(int i=0;i<s.length();i++){
            cout<<s.at(i);
        }
        cout<<endl;

    }
    int main(){
        binary bin1;
        bin1.read();
        bin1.onecomp();
        bin1.display();
        return 0;
    }
```

## Memory Allocation in Classes
Member functions in classes share same memory space for evry object whereas variables like name, email etc share different memory for different objects.

### Using Arrays in Classes
                   
Example-
```cpp                   
        #include<iostream>
        using namespace std;

        class shop{
                int itemid[100];
                int itemprice[100];
                int counter;
                public:
                void initcounter(void){counter=0;};
                void setprice(void);
                void displayprice(void);
        };

        void shop:: setprice(void){
                cout<<"Enter the id of your product "<<"no "<<counter+1<<endl;
                cin>>itemid[counter];
                cout<<"Enter price of your product "<<"no "<<counter+1<<endl;
                cin>>itemprice[counter];
                counter++;
        }

        void shop:: displayprice(void){
                for(int i=0;i<counter;i++){
                        cout<<"The price of item id "<<itemid[i]<<" is "<<itemprice[i]<<endl;
                }
        }

        int main(){
                shop obj1;
                obj1.initcounter();
                obj1.setprice();
                obj1.setprice();
                obj1.setprice();
                obj1.displayprice();
                return 0;
        }
```        
### Static variables in Classes
In simple words static variable is one variable which is shared by all the members of a class.
                                                                                             
Syntax-
```cpp                                                                                             
        // static datatype variable name;
            static int empid;

        // to call them or initialize them outside class
            datatype classname :: variable name;
            int employee :: empid; 
```    
Example -
```cpp                                                                                             
        #include<iostream>
        using namespace std;

        class employee{
                int id;
                static int count;   // will take memory only one time and then keeps updating no new memory for each object
                public:
                void setdata(void){
                        cout<<"Enter the id: "<<endl;
                        cin>>id;
                        count++;
                }
                void getdata(void){
                        cout<<"ID of this employee is "<<id<<" and employee number is "<<count<<endl;
                }
        };

        int employee:: count;

        int main(){
                employee rahul,chetan,lovish;
                rahul.setdata();
                rahul.getdata();
                chetan.setdata();
                chetan.getdata();
                lovish.setdata();
                lovish.getdata();
                return 0;
        }

    //Note- To initialize a static variable we must initialize it outside the class as it will give an error inside the class
    
    classs employee{
        static int empid=1000;  // this will give error
    };
    int employee :: empid=1000;     // this is correct as it is outside class
```
    
## Static Functions 
It is created when we want that the function should only access the static members of a class.
    
Syntax-
```cpp
         //To create function inside class-
         static datatype funcname(argumets){
            commands;
         }
         //To call the function inside main
         classname :: funcname();
```    
Example-
```cpp    
        #include<iostream>
        using namespace std;

        class employee{
                int id;
                static int count;   // will take memory only one time and then keeps updating no new memory for each object
                public:
                void setdata(void){
                        cout<<"Enter the id: "<<endl;
                        cin>>id;
                        count++;
                }
                void getdata(void){
                        cout<<"ID of this employee is "<<id<<" and employee number is "<<count<<endl;
                }
                static void getcount(void){    // creating static function
                        cout<<"The value of count is "<<count<<endl;
                }
        };

        int employee:: count;

        int main(){
                employee rahul,chetan,lovish;
                rahul.setdata();
                rahul.getdata();
                employee :: getcount();  // calling static function
                chetan.setdata();
                chetan.getdata();
                employee :: getcount();
                lovish.setdata();
                lovish.getdata();
                employee :: getcount();
                return 0;
        }
```
    
## Array of objects -
Example-    
```cpp    
        #include<iostream>
        using namespace std;

        class employee{
                int id;
                int salary;
                public:
                void setid(void){
                        salary=122;
                        cout<<"Enter id of employee "<<endl;
                        cin>>id;
                }
                void getid(void){
                        cout<<"The id of this employee is "<<id<<endl;;
                }
        };

        int main(){
                employee company1[4];
                for(int i=0;i<4;i++){
                        company1[i].setid();
                        company1[i].getid();
                }
                return 0;
        }
```
                                      
### Passing Objects of classes as function arguments-
```cpp                                      
    #include<iostream>
    using namespace std;

    class complex{
            int a;
            int b;
            public:
            void setdata(int v1,int v2){
                    a=v1;
                    b=v2;
            }
            void setdatabysum(complex v1,complex v2){    // passing objects of a class as arguments
                    a=v1.a+v2.a;
                    b=v1.b+v2.b;
            }
            void print(void){
                    cout<<"Your compex number is "<<a<<"+ "<<b<<"i"<<endl;
            }
    };

    int main(){
            complex c1,c2,c3;
            c1.setdata(1,2);
            c1.print();
            c2.setdata(3,4);
            c2.print();
            c3.setdatabysum(c1,c2);
            c3.print();
            return 0;
    }
```                   
## Friend Functions
Friend functions are not member functions of any class rather just a foreign function that get permission from the class to be able to fetch private data. The permission to the function in class is given as follows-

```cpp    
    class complex{
        friend complex sumcomplex(complex o1,complex o2);     // declaration in class to give access 
        //friend class-name function-name(arguments)
    };
    complex sumcomplex(complex o1,complex o2){
        any commands;
    }
```
    
### Properties of friend function-
1. Not in the scope of class 
2. Since it is not in the scope of class , it cannot be called from object of that class in below example
`c1.sumcomplex()==invalid.`   
3. Can be invoked without the help of any object.
4. Usually contains the objects as arguments.
5. Can be declared inside public or private section of the class

Example-
```cpp    
        #include<iostream>
        using namespace std;

        class complex{
                int a;
                int b;
                public:
                friend complex addsum(complex o1,complex o2);  // declaring friend function
                void setnumber(int n1,int n2){
                        a=n1;
                        b=n2;
                }
                void printnumber(void){
                        cout<<"your number is "<<a<<" + "<<b<<"i"<<endl;
                }
        };

        complex addsum(complex o1,complex o2){
                complex o3;
                o3.setnumber((o1.a+o2.a),(o1.b+o2.b));
                return o3;
        }

        int main(){
                complex c1,c2,sum;
                c1.setnumber(1,4);
                c1.printnumber();
                c2.setnumber(5,8);
                c2.printnumber();
                sum=addsum(c1,c2);
                sum.printnumber();
                return 0;
        }
```
    
### Friend classes and Member friend functions
Individually declaring functions of other class as friends-
```cpp    
        #include<iostream>
        using namespace std;

        class complex;        // telling compiler that complex class exits so that no error is reciever in calculator class

        class calculator{
                public:
                int add(int a , int b){
                        return (a+b);
                }
                int sumrealcomplex(complex,complex);  // cant define fucntion here because cant acess private members of class complex until class complex is declared
                int sumcompcomplex(complex,complex);
        };

        class complex{
                int a;
                int b;
                friend int calculator :: sumrealcomplex(complex,complex);  // making sumrealcomplex friend function
                friend int calculator :: sumcompcomplex(complex,complex);
                public:
                void setnumber(int n1,int n2){
                        a=n1;
                        b=n2;
                }
                void printnumber(void){
                        cout<<"your number is "<<a<<" + "<<b<<"i"<<endl;
                }
        };

        int calculator :: sumrealcomplex(complex o1,complex o2){   // defining function here because now class complex is declared and we can access the private members
                return(o1.a+o2.a);
        }
        int calculator :: sumcompcomplex(complex o1,complex o2){   // defining function here because now class complex is declared and we can access the private members
                return(o1.b+o2.b);
        }

        int main(){
                complex a1,b1;
                a1.setnumber(1,3);
                b1.setnumber(7,8);
                calculator calc;
                int sum=calc.sumrealcomplex(a1,b1);
                int sumc=calc.sumcompcomplex(a1,b1);
                cout<<"The sum of real part of complex number is "<<sum<<endl;
                cout<<"The sum of complex part of complex number is "<<sumc<<endl;
                return 0;
        }
```
    
Declaring the entire other class as friend (using the same code above)
```cpp    
        #include<iostream>
        using namespace std;

        class complex;        // telling compiler that complex class exits so that no error is reciever in calculator class

        class calculator{
                public:
                int add(int a , int b){
                        return (a+b);
                }
                int sumrealcomplex(complex,complex);  // cant define fucntion here because cant acess private members of class complex until class complex is declared
                int sumcompcomplex(complex,complex);
        };

        class complex{
                int a;
                int b;
                friend class calculator;  // making the whole class friend
                public:
                void setnumber(int n1,int n2){
                        a=n1;
                        b=n2;
                }
                void printnumber(void){
                        cout<<"your number is "<<a<<" + "<<b<<"i"<<endl;
                }
        };

        int calculator :: sumrealcomplex(complex o1,complex o2){   // defining function here because now class complex is declared and we can access the private members
                return(o1.a+o2.a);
        }
        int calculator :: sumcompcomplex(complex o1,complex o2){   // defining function here because now class complex is declared and we can access the private members
                return(o1.b+o2.b);
        }

        int main(){
                complex a1,b1;
                a1.setnumber(1,3);
                b1.setnumber(7,8);
                calculator calc;
                int sum=calc.sumrealcomplex(a1,b1);
                int sumc=calc.sumcompcomplex(a1,b1);
                cout<<"The sum of real part of complex number is "<<sum<<endl;
                cout<<"The sum of complex part of complex number is "<<sumc<<endl;
                return 0;
        }
```
- Make a program that swaps the values of variables of two different classes
```cpp    
        #include<iostream>
        using namespace std;

        class c2;  // forward declaration
        class c1{
                int val;
                public:
                friend void exchange(c1 &,c2 &);  // can be declared anywhere either in private or in public
                void setdata(int a){
                        val=a;
                }
                void display(void){
                        cout<<val<<endl;
                }
        };

        class c2{
                int val;
                friend void exchange(c1 &,c2 &);   // making exchange as a friend function
                public:
                void setdata(int a){
                        val=a;
                }
                void display(void){
                        cout<<val<<endl;
                }
        };

        void exchange(c1 &a,c2 &b){            // using &(reference operator) to swap values
                int temp=a.val;
                a.val=b.val;
                b.val=temp;
        }

        int main(){
                c1 a1;
                c2 a2;
                a1.setdata(4);
                a2.setdata(8);
                exchange(a1,a2);
                cout<<"The value of a1 after swapping is : ";
                a1.display();
                cout<<endl;
                cout<<"The value of a2 after swapping is : ";
                a2.display();
                return 0;

        }
```
## Constructors
Constructor is a special member function with same name as of class. It is used to initialize the objects of its class. It is invoked whenever an object is created.

Syntax-
```cpp    
            #include<iostream>
            using namespace std;

            class complex{
                    int a,b;
                    public:
                    complex(void);   // declaring a constructor must be same as class name
                    void printnumber(void){
                    cout<<"your number is "<<a<<" + "<<b<<"i"<<endl;
                    }
            };
            complex :: complex(void){          // defining a connstructor (default constructor with no values)
                    a=10;
                    b=0;
            }
            int main(){
                    complex c;
                    c.printnumber();
                    return 0;

            }
```
### Characteristics of constructor -
1. It should be declared in public section of the class.
2. They are automatically invoked whenver an object is created.
3. They cannot return values and do not have return types.
4. It can have default arguments.
5. We cannot refer to their address.

### Parameterized and Default constructor
- A constructor that accepts no parameters is called a default constructor.
- A constructor that accepts parameters is called a parameterized constructor.
    
- Creating a program to calculate distance between two points using parameterized constructor and friend fucntion
```cpp
        #include<iostream>
        #include<cmath>
        using namespace std;

        class point{
                int x,y;
                friend point distance(point,point);
                public:
                point(int a,int b){  // parameterized constructor
                        x=a;
                        y=b;
                }
                void display(void){
                        cout<<"The point is ("<<x<<" , "<<y<<")"<<endl;
                }
        };
        point distance(point a,point b){        // friend function
                float distance1 = (b.x-a.x)*(b.x-a.x);
                float distance2 = (b.y-a.y)*(b.y-a.y);
                float finaldist = sqrt(distance1+distance2);
                cout<<"The difference between point is "<<finaldist;

        }
        int main(){
                point p(1,2);
                p.display();
                point q(7,8);
                q.display();
                distance(p,q);
                return 0;
        }
```
    
- Note - Constrcutors can also be given pre-defined value in arguments while declaring like  
```cpp
complex(int a,int b=9){   // assigning b=9 by default
            x-a;
            y=b;
        }
        int main(){
            complex c1(4);  // automatically b will get 9
        }
```
    
## Constructor Overloading
Similarly like function overloading Constrcutors can also be overloaded
    
Example-
```cpp    
        #include<iostream>
        using namespace std;

        class complex{
                int a,b;
                public:
                complex(int x,int y){
                        a=x;
                        b=y;
                }
                complex(int x){      // constructor over-loading
                        a=x;
                        b=0;
                }
                complex(){
                        a=0;
                        b=0;
                }
                void printnumber(void){
                cout<<"your number is "<<a<<" + "<<b<<"i"<<endl;
                }
        };

        int main(){
                complex c1(4,5);
                c1.printnumber();
                complex c2(5);
                c2.printnumber();
                complex c3;
                c3.printnumber();
                return 0;
        }
```
    
## Dynamic initialization of objects using constructor
When creating multiple constructors for dynamic initialization a blank constructor like 
`constructor(){}` must be created so that before dynamically allocating the constrcutor to objects according to 
their types the compiler can give them an empty constrcutor and avoid errors.

Example-
```cpp    
        #include<iostream>
        using namespace std;

        class bankdeposit{
                int principal,years;
                float interestrate,returnvalue;
                public:
                bankdeposit(){}; // ceating an empty constructor
                bankdeposit(int p,int y,float r); //r can be like 0.04
                bankdeposit(int p,int y,int r); // r can be value like 14
                void show();
        };
        bankdeposit :: bankdeposit(int p,int y,float r){
                principal=p;
                interestrate=r;
                years=y;
                returnvalue=principal;
                for(int i=0;i<y;i++){
                        returnvalue=returnvalue*(1+r);
                }
        }
        bankdeposit :: bankdeposit(int p,int y,int r){
                principal=p;
                interestrate=float(r)/100;
                years=y;
                returnvalue=principal;
                for(int i=0;i<y;i++){
                        returnvalue=returnvalue*(1+interestrate);
                }
        }
        void bankdeposit :: show(){
                cout<<endl<<"The principal amount was "<<principal<<endl<<" Return value after "<<years<<" years is"
                <<returnvalue<<endl;
        }

        int main(){
                bankdeposit bd1,bd2,bd3;
                int p,y;
                int R;
                float r;
                cout<<" Enter the value of p, y and r: "<<endl;
                cin>>p>>y>>r;
                bd1=bankdeposit(p,y,r);
                bd1.show();
                cout<<" Enter the value of p, y and R: "<<endl;
                cin>>p>>y>>R;
                bd2=bankdeposit(p,y,R);
                bd2.show();
                return 0;
        }
```
    
## Copy Constructor
Copy constructor is used to copy the members of one object to another by calling the constrcutor. When
no copy constrcutor is present in the class the compiler calls its own copy constructor.

Example-
```cpp    
    #include<iostream>
    using namespace std;

    class number{
            int a;
            public: 
            number(){};
            number(int n){
                    a=n;
            }
            number(number &n){      // creating a copy constructor
            a=n.a;
            }
            void display(){
                    cout<<"The number for this object is "<<a<<endl ;
                        }
    };

    int main(){
            number x,y,z(45);
            z.display();
            // Various ways to invoke copy constructor
            y=number(z); // copy constrcutor will be called
            y.display();
            x=y; // copy constrcutor will not be called
            number x1=y;  // copy constructor will be called
            x1.display();
            return 0;
    }
```
    
## Destructor
It is used to clear the dynamic allocated memory whenever a constructor is destroyed. It does not accept any arguments nor returns any value. It is implicitly called by the compiler itself.
    
Syntax to define destructor -
```cpp    
        ~classname(arguments){
            code
        }

    example to understand destructor-
        #include<iostream>
        using namespace std;

        int count=0;
        class num{
                public:
                num(){
                        count++;
                        cout<<"This is the time when constructor is called for object number "<<count<<endl;
                }
                ~num(){
                        cout<<"This is the time when destructor is called for object number "<<count<<endl;
                        count--;
                }
        };

        int main(){
                cout<<"entering main"<<endl;
                cout<<"creating an object"<<endl;
                num num1;
                {
                        cout<<"Entering this block "<<endl;
                        cout<<"Creating two more objects "<<endl;
                        num n2,n3;
                        cout<<"Exiting this block"<<endl;
                }
                cout<<"back to main"<<endl;
                return 0;
        }
```
    
### Inheritance in C++
1. The concept of reusability in C++ is supported using Inheritance.
2. We can reuse the properties of an existing class by inheriting from it.
3. The existing class is called the base class.
4. The new class which is inherited is called the derived class.
5. Reusing classes saves time and money.
6. There are different types of inheritance in C++.

### Importance of inheritance in C++ :
1. Reusability is a very important feature of OOPs.
2. In C++ we can reuse a class and add additional features to it.
3. Reusing classes saves time and money.
4. Reusing already tested and debugged class will save a lot of effort of developing and debugging the same thing again.

### Forms of inheritance in C++ :
1. Single inheritance - A derived class with only one base class
2. Multiple inheritance - A derived class with more than one base class
3. Hierarchial inheritance - Several derived classes from single base class
4. Multilevel inheritance - Deriving a class from already derived class
5. Hybrid inheritance - 
    1. Hybrid inheritance is a combination of multiple inheritance and multilevel inheritance.
    2. A class is derived from two classes as in multiple inheritance.
    3. However, one of the parent classes is not a base class.

- Syntax for making derived class 
```cpp
    class derived-class-name : visibility-mode base-class-name{
        class members methods etc.
    }
```
- Note- Default visibility mode is private.
- Public-visibility-mode : Public members of the base class becomes public members of derived class.
- Private-visibility-mode : Public members of the base class becomes private members of derived class.
- Note- Private members of a base class will never be inherited.

Example to understand visibility -
```cpp
        #include<iostream>
        using namespace std;

        //Base class
        class employee{
                public:
                int id;
                float salary;
                employee(int id1){
                        id=id1;
                        salary=34.00;
                }
                employee(){};
        };
        class programmer : employee{    // making a derived class 
                public:
                programmer(int impid){
                        id=impid;
                }
                int languagecode=9;
                void getdata(){
                        cout<<id<<endl;
                }
        };

        int main(){
                employee john(34),rocky(23);
                cout<<john.salary<<endl;
                cout<<rocky.salary<<endl;
                programmer skillif(35);
                cout<<skillif.languagecode<<endl;
                skillif.getdata();
                // can't access id directly by skillif.id cause we inherited members privately
                return 0;
        }
```
    
## Single Inheritance
Example -
```cpp
        #include<iostream>
        using namespace std;

        class base{
                int data1;  // private by deafult and inheritable
                public:
                int data2;
                void setdata();
                int getdata1();
                int getdata2();

        };

        void base :: setdata(){
                data1=10;
                data2=20;
        }

        int base :: getdata1(){
                return data1;
        }

        int base :: getdata2(){
                return data2;
        }

        class derived : public base{ // class is being derived publically
                int data3;
                public:
                void process();
                void display();
        };

        void derived :: process(){
                data3=data2*getdata1();
        }

        void derived :: display(){
                cout<<"value of data1 is: "<<getdata1()<<endl;
                cout<<"value of data2 is: "<<data2<<endl;
                cout<<"value of data3 is: "<<data3<<endl;
        }

        int main(){
                derived der;
                der.setdata();
                der.process();
                der.display();
                return 0;
        }
```    

## Protected Acess Modifier in C++
A protected member variable or function is very similar to a private member but it provided one additional benefit that they can be accessed in child classes which are called derived classes

### For a protected member :
                           Public Derivation    Private Derivation      Protected Derivation
    1. Private members     Not inherited        Public                  Not inherited
    2. Protected members   Protected            Private                 Protected
    3. Public members      Public               Private                 Protected

Example-
```cpp
        #include<iostream>
        using namespace std;

        class base{
                protected:
                int a;
                private:
                int b;
        };

        class derived : protected base{};
        int main(){
                base b;
                derived d;
                cout<<d.a;  // will not wor as a is protected and will be inherited as protected only member functions of derived class can access it.
                return 0;
        }
```
    
## Multilevel Inheritance
Notes:
- If we are inheriting B from A and C from B: `[A--->B--->C]`
    1. A is the base class for B and B is the base class for C 
    2. A--->B--->C is called inheritance path
    
Example-
```cpp
        #include<iostream>
        using namespace std;

        class student{
                protected:
                int rollno;
                public:
                void setno(int);
                void getno(void);
        };

        void student :: setno(int n){
                rollno=n;
        }

        void student :: getno(){
                cout<<"The roll no is: "<<rollno<<endl;
        }  

        class exam : public student{
                protected:
                float maths;
                float physics;
                public:
                void setmarks(float,float);
                void getmarks(void);
        };

        void exam :: setmarks(float n1,float n2){
                maths=n1;
                physics=n2;
        }

        void exam :: getmarks(){
                cout<<"The marks obtained in maths are: "<<maths<<endl;
                cout<<"The marks obtained in physics are: "<<physics<<endl;
        }

        class result : public exam{
                float percentage;
                public:
                void display(){
                        getno();
                        getmarks();
                        cout<<"Your percentage is "<<(maths+physics)/2<<"%"<<endl;
                }
        };

        int main(){
                result chetan;
                chetan.setno(11);
                chetan.setmarks(94.0,93.0);
                chetan.display();
                return 0;
        }
```    

## Multiple Inheritance
- Syntax-
```cpp
        class derived : visibility-mode base1 , visibility-mode base2{
            class body of derived
        }
```

Example of multiple inheritance -
```cpp
        #include<iostream>
        using namespace std;

        class base1{
                protected:
                int base1int;
                public:
                void set_base1int(int a){
                        base1int=a;
                }
        };

        class base2{
                protected:
                int base2int;
                public:
                void set_base2int(int a){
                        base2int=a;
                }
        };

        class derived : public base1 , public base2{   // you can add as much base classes you want by writing class name with comma
                public:
                void show(){
                        cout<<"The value of base1 is "<<base1int<<endl;
                        cout<<"The value of base2 is "<<base2int<<endl;
                        cout<<"The sum of both is "<<(base2int+base1int)<<endl;
                }
        };

        int main(){
                derived chetan;
                chetan.set_base1int(4);
                chetan.set_base2int(9);
                chetan.show();
                return 0;
        }
```
## Ambiguity Resolution in Inheritance
Many times two or more classes have the function created with the same name and when a class is derived from those
two classes ambiguity occurs. To solve this we can define a function in the derived class and tell it to use 
a function from a particular class.

Example for the same -
```cpp
        #include<iostream>
        using namespace std;

        class base1{
                public:
                void greet(){
                        cout<<"Hey how are you ?"<<endl;
                }
        };
        class base2{
                public:
                void greet(){
                        cout<<"kaise ho ? "<<endl;
                }
        };

        class derived : public base1,public base2{
                int a;
                public:
                void greet(){              // resolving the ambiguity by telling compiler to use base1 greet whenever greet is called in the derived class
                        base1::greet();
                }
        };

        int main(){
                base1 base1obj;
                base2 base2obj;
                derived dervobj;
                dervobj.greet();   // will use base1 greet function because we defined it above 
                return 0;
        }
```

If the derived class has a function written with the same name as the base class the compiler will use the 
local function or override the base inherited function whenever an object from the derived class calls that function.

## Virtual Base Class 
Consider an instance where two classes are derived from a single base class "A" and further those two derived
classes are also used to derived a new class. Diagram for reference
`A-->B&C-->D` in this situation when b and c will give their variables to D they might give the copy of variables
recieved from A two times ( as they both inherited same variable to A ) this results in ambiguity and to solve 
this virtual base class is formed.
    
Syntax- 
```cpp
        derived class : virtual inheritance-mode base class{
            code
        }
        derived : virtual public student{
            code
        }
```    

Example-
```cpp
        #include<iostream>
        using namespace std;

        class student{
                protected:
                int rollno;
                public:
                void setnumber(int a){
                        rollno=a;
                }
                void printnumber(){
                        cout<<"Your roll no is : "<<rollno<<endl;
                }
        };

        class test : virtual public student{   // inheriting from student as virtual class 
                protected:                     // we can write virtual public base class or public virtual base class both does the same thing
                float maths,physics;
                public:
                void setmarks(float m1,float m2){
                        maths=m1;
                        physics=m2;
                }
                void printmarks(){
                        cout<<"Your result is here: "<<endl
                        <<"Maths "<<maths<<endl
                        <<"Phsics "<<physics<<endl;
                }
        };

        class sports : virtual public student{   // inheriting from virtual base class student 
                protected:
                float score;
                public:
                void setscore(float sc){
                        score=sc;
                }
                void printscore(){
                        cout<<"Your P.T score is: "<<score<<endl;
                }
        };

        class result : public test , public sports{
                private:
                float total;
                public:
                void display(){
                        total=maths+physics+score;
                        printnumber();  // resolved ambiguity and prints rollno inherited from student only once due to virtual class
                        printmarks();
                        printscore();
                        cout<<"Your total score is: "<<total<<endl;
                }
        };

        int main(){
                result chetan;
                chetan.setnumber(11);
                chetan.setmarks(75.00,93.00);
                chetan.setscore(95.00);
                chetan.display();

                return 0;
        }
```

## Constrcutors in Derived class 
1. We can use constructors in derived classes in C++
2. If base class constructor does not have any arguments, there is no need of constrcutor in derived class.
3. But if there are one or more arguments in the base class constructor, derived class need to pass arguments to the base class constrcutor.
4. If both base and derived class have constructors, base class constrcutor is executed first.

## Constrcutors in Multiple Inheritance
1. In multiple inheritance, base classes are constructed in the order in which they appear in the class declaration.
2. In multilevel inheritance, the constructors are executed in the order of inheritance.

## Special Syntax-
    1. C++ supports an special syntax for passing arguments to multiple base classes.
    2. The constructor of the derived class recieves all the arguments at once and then will pass the calls to the respective base classes.
    3. The body is called after all the constructors are finished executing.

`derived-constructor(arg1,arg2,arg3,....):base1-constructor(arg1,arg2):base2-constructor(arg3,arg4){
        ....
    }base1-constructor(arg1,arg2)`

## Special case for Virtual Base Class -
1. The constructors for virtual base classes are invoked before an nonvirtual base class.
2. If there are multiple virtual base classes, they are invoked in order declared.
3. Any non-virtual base class are then constructed before the derived class constructor is executed.

Example of order of execution of constructor -

Case 1-
```cpp
                class A : public B {
                        // order of execution B() then A()
                }
```

Case 2-
```cpp
                class A: public B,public C{
                        // order of execution constructor B() -> C() -> A()
                }
```

Case 3-
```cpp
                class A: public B, virtual public C{
                        // order of execution C() then B() then A()
                }
```

### Example of constructor execution in derived class :
```cpp
        #include<iostream>
        using namespace std;

        class base{
                int data;
                public:
                base(int i){
                        data=i;
                        cout<<"Base class constructor called"<<endl;
                }
                void printdatabase1(){
                        cout<<"The value of data is "<<data;
                }
        };

        class base2{
                int data2;
                public:
                base2(int i){
                        data2=i;
                        cout<<"Base2 class constructor called"<<endl;
                }
                void printdatabase2(){
                        cout<<"The value of data is "<<data2;
                }
        };

        class derived : public base,public base2{     // if we make this like public base2,public base then base2 will run first but if we do same thing while assigning base contructors value through derived class it would not work
                int derived1,derived2;
                public:
                derived(int a,int b,int c,int d):base(a),base2(b){  // derived class constructor calling both base class constructor and supplying them with value
                        derived1=c;
                        derived2=d;
                        cout<<"Derived class constructor called"<<endl;
                }
                void printdataderived(){
                        cout<<"The value of derived1 is "<<derived1<<endl;
                        cout<<"The value of derived2 is "<<derived2<<endl;
                }
        };

        int main(){
                derived chetan(1,2,3,4);
                chetan.printdatabase1();
                return 0;
        }
```

## Initialization list in constructor
Syntax for initialization list in constructor- 
```cpp
                contsructor(argument-list) : initialization-section{
                        assignment+othercode
                }
```

Example-
```cpp
                #include<iostream>
                using namespace std;

                class test{
                        int a,b;   // to run b(j),a(i+b) we should write here int b,a;
                        public:
                        test(int i,int j) : a(i),b(j){ 
                // a will get value of i and b will get value of j because constructor list is initialize
                // we can also use test(int i,int j) : a(i),b(a+j) as a is declared first but 
                // we cannot use test(int i,int j) : b(j),a(i+b) because a is declared first and will get value first so till time a gets value b is still garbage value
                                cout<<"Constrcutor is called "<<endl;
                                cout<<"The value of a is "<<a<<endl;
                                cout<<"The value of b is "<<b<<endl;
                        }
                };

                int main(){
                        test obj1(4,5);
                        return 0;
                }
```

## The new keyword
It is used to dynamically assign an integer 

Syntax and example-
```cpp
                int *ptr = new int(40)  // will store 40 in value of pointer ptr
```      

It is replacement of code where we first declare and initialize a varibale just like a temporary variable 

## Continue memory allocation using pointers
By declaring a pointer and storing array in that using new keyword we can achieve contionous memory allocation

Example -
```cpp
                #include<iostream>
                using namespace std;

                int main(){
                        int *arr= new int[4];
                        arr[0]=1;
                        *(arr+1)=2;   // same as arr[1]=2
                        arr[2]=3;
                        arr[3]=4;
                        cout<<"The value at arr[0] is: "<<arr[0];
                        cout<<"The value at arr[1] is: "<<arr[1];
                        cout<<"The value at arr[2] is: "<<arr[2];
                        return 0;
                }
```
## Delete keyword/operator in c++
Delete is used to deallocate memory for a C++ class object, the object's destructor is called before the object's memory is deallocated (if the object has a destructor). Delete is used to delete a single object initiated using new keyword whereas delete[] is used to delete a group of objects initiated with the new operator.

Example (same as above using delete operator)-
```cpp
        #include<iostream>
        using namespace std;

        int main(){
                int *arr= new int[4];
                arr[0]=1;
                arr[1]=2;
                arr[2]=3;
                arr[3]=4;
                delete [] arr;  // delets the whole memory allocation and now program will print garbage value
                cout<<"The value at arr[0] is: "<<arr[0];
                cout<<"The value at arr[1] is: "<<arr[1];
                cout<<"The value at arr[2] is: "<<arr[2];
                return 0;
        }
```

## Pointers to Objects
We can use the -> operator to run any function on bhalf of the object that the pointer is pointing to.

Like-
```cpp
                complex *ptr=new complex;
                ptr->getdata();  // same work as below just two different syntax
                (*ptr).getdata()
```                
Example-
```cpp
                #include<iostream>
                using namespace std;

                class complex{
                        int real,imaginary;
                        public:
                        void getdata(){
                                cout<<"The real part is : "<<real<<endl;
                                cout<<"The imaginary part is : "<<imaginary<<endl;
                        }
                        void setdata(int a,int b){
                                real=a;
                                imaginary=b;
                        }

                };

                int main(){
                        complex c1;
                        // complex *ptr=&c1;
                        //or
                        complex *ptr=new complex;
                        c1.setdata(4,5);
                        c1.getdata();
                        // (*ptr).setdata(7,8); is exactly same as
                        ptr->setdata(7,8);
                        (*ptr).getdata();
                        return 0;
                }
```
## Array of pointers pointing to many objects
If we use a pointer to point to an array of objects the *ptr will store the address of the first object in 
the array and to access the rest we can add 1 to the pointer

Example -
```cpp
                #include<iostream>
                using namespace std;

                class shop{
                        int id;
                        float price;
                        public:
                        void setdata(int a,float b){
                                id=a;
                                price=b;
                        }
                        void getdata(){
                                cout<<"Code of this item is "<<id<<endl;
                                cout<<"Price of this item is "<<price<<endl;
                        }
                };

                int main(){
                        int size=2;
                        int p,i;
                        float q;
                        shop *ptr=new shop[size];
                        shop *ptrtmp=ptr;
                        for(i=0;i<size;i++){
                                cout<<"Enter Id and price of item "<<i+1;
                                cin>>p>>q;
                                //(*ptr).setdata(p,q)
                                ptr->setdata(p,q);
                                ptr++;
                        }       
                        for(i=0;i<size;i++){
                                cout<<"Item number: "<<i+1<<endl;
                                ptrtmp->getdata();
                                ptrtmp++;
                        }
                        return 0;
                }
```

## This Pointer in C++
While defining a function we cannot use same name for a varibale and ana argument as this will return garbage value
```cpp
                int a;
                void func1(int a){
                        a=a;      // this will return a garbage value
                }
```        

To solve this problem this keyword in c++ comes to rescue:
1. this->a=a // here this->a is referring to the private member of class
2. this is a keyword which is a pointer which points to the object which invokes the member function 
        
Example-
```cpp
                #include<iostream>
                using namespace std;

                class a1{
                        int a;
                        public:
                        a1 & setdata(int a){
                                this->a=a;
                                return *this;  // will return the object who called this member function and we can apply further functions on that
                        }
                        void getdata(){
                                cout<<"The value of a is "<<a;
                        }
                };

                int main(){
                        a1 c;
                        c.setdata(7).getdata();
                        return 0;
                }
```

## Polymorphism in C++
One name and multiple forms eg- function overloading, virtual function,operator overloading

Two types of Polymorphism in c++ :
1. Compile time Polymorphism (you already know what function gonna run) - operator overloading , function overloading
2. Run-time Polymorphism (object is binded and function is ran after the program executes)

## Pointers to Derived Classes in C++
Although we can point a pointer of base class with object of derived class but in case we invoke any member function,
the base class function will be called.

Sametype of pointers bind with functions of same type(or class) like complex *ptr pointer will bind with any member
function of same class this is what is called late binding.

Notes:
```cpp
                #include<iostream>
                using namespace std;

                class baseclass{
                        public:
                        int var_base;
                        void display(){
                                cout<<"displaying base class variable var_base "<<var_base<<endl;
                        }
                };
                class derivedclass : public baseclass{
                        public:
                        int var_derived;
                        void display(){
                                cout<<"displaying base class variable var_base "<<var_base<<endl;
                                cout<<"displaying base class variable var_derived "<<var_derived<<endl;
                        }

                };

                int main(){
                        baseclass *ptr=new derivedclass;  // base class pointer pointing derived class
                        ptr->var_base=34;  // can be set as it is member of base class
                        // ptr->var_derived=75 // cannot be set as it is a member of derived class
                        ptr->display();
                        derivedclass *dptr=new derivedclass; // derived class pointer pointing drived class
                        dptr->var_base=995;
                        dptr->var_derived=998;
                        dptr->display();
                        return 0;
                }
```

## Virtual Functions
Virtual functions are used to override the default behaviour of the base class pointer pointing to derived class
when we make a base class function virtual we can use a base class pointer pointing to derived class to refer to a function
in derived class.

Example -
```cpp
                #include<iostream>
                using namespace std;

                class baseclass{
                        public:
                        int var_base;
                        virtual void display(){   // declaring function as virtual
                                cout<<"displaying base class variable var_base "<<var_base<<endl;
                        }
                };
                class derivedclass : public baseclass{
                        public:
                        int var_derived;
                        void display(){
                                cout<<"displaying base class variable var_base "<<var_base<<endl;
                                cout<<"displaying base class variable var_derived "<<var_derived<<endl;
                        }

                };

                int main(){
                        baseclass *bptr;
                        baseclass objbase;
                        derivedclass objder;
                        bptr=&objder;  // pointer pointing to derived class object
                        bptr->display();  // runs display function of derived class
                        return 0;
                }
```
Rules for Virtual Functions :
1. They cannot be static
2. They are accessed by object pointers
3. Virtual functions can be a friend of another class
4. A function in base class might not be used
5. If a virtual function is derived in base class there no necessity of redefining it in the derived class

Example -
```cpp
                #include<iostream>
                #include<cstring>
                using namespace std;

                class yt{
                        protected:
                        string title;
                        float rating;
                        public:
                        yt(string s,float r){
                                title=s;
                                rating=r;
                        }
                        virtual void display(){};
                };

                class ytvideo : public yt{
                        float videolength;
                        public:
                        ytvideo(string s,float r, float vl) : yt(s,r){
                                videolength=vl;

                        }
                        void display(){
                                cout<<"This video has amazing tiite "<<title<<endl;
                                cout<<"Ratings: "<<rating<<endl;
                                cout<<"Length of this video is "<<videolength<<" minutes"<<endl;
                        }
                };

                class yttext : public yt{
                        int words;
                        public:
                        yttext(string s,float r,int wc) : yt(s,r){
                                words=wc;
                        }
                        void display(){
                                cout<<"This text tutoria has  amazing tiite "<<title<<endl;
                                cout<<"Ratings of this text : "<<rating<<endl;
                                cout<<"No of words for this tutorial are: "<<words<<" words"<<endl;
                        }
                };

                int main(){
                        string title;
                        float rating,vidlength;
                        int words;
                        // for yt video
                        title=" Amazing CPP tutorial ";
                        rating=4.8;
                        vidlength=12.9;
                        ytvideo obj1(title,rating,vidlength);
                        // obj1.display();
                        // for yt text
                        title=" Amazing CPP text ";
                        rating=4.13;
                        words=197;
                        yttext obj2(title,rating,words);
                        // obj2.display();
                        yt *lect[2];
                        lect[0]=&obj1;
                        lect[1]=&obj2;

                        lect[0]->display();

                        return 0;
                }
```

## Abstract Base class & Pure virtual Functions
When defining a base class we add a virtual function in it and when we redefine that function in a derived class
the derived class object calls the redefined derived class function but when there is no redifination of virtual function
in the derived class the virtual function of base class is called when we want that there should always be a redefination 
of the base class virtual function in the derived class we make the function pure virtual or do nothing function.

syntax-
```cpp
        virtual void display()=0; // if there is no redifination in derived class it will give an error
```
Abstarct base class is a concept which says that we should create a base class for derving other classes but an 
object is never made out of that class or it is a class that atleast have one pure virtual function.

## File I/O in C++
- File is a collection of data stored on the memory or disk
- Input stream helps the program to read from a file whereas an output stream helps the program to write to a file.

To work with files in C++ we need some classes which are stored in the header file <fstream> and we need to include these header files into the program.

The useful classes for working with files in C++ are -
1. `fstreambase`
2. `ifstream` --> derived from fstreambase
3. `ofstream` --> derived from fstreambase

In order to start working with a file we first have to open the file in a C++ program and there are primarily
two ways of opening a file in C++ -
1. Using the constructor - `ofstream objectname ("filename");`
2. Using the member function open() of the class - `ofstream objectname;
                                                          object.open("filename");`

### Syntax for writing to a file:
```cpp
                ofstream objectname("filename");
                object<<string;
```

Syntax for reading from a file:
```cpp
                ifstream objectname("filename");
                object>>string; // one word reading
                getline(object,string); // reading a whole line;
```

When reading with ifstream and using `in>>string;` it reads only one word and terminates after spaces or new
line to solve this we use `getline(in,stringname)` so that a full line can be read.

Sample program to create and write to a file :
```cpp
                #include<iostream>
                #include<fstream>
                using namespace std;

                int main(){
                        string st="Hello welcome to my github C++ ";
                        // Opening file using constructor and writing to it
                        ofstream out("samplefile.txt"); // write operation & out is an object name (can be any)
                        out<<st;
                        return 0;
                }
```        
Sample program to read from a file:
```cpp
                #include<iostream>
                #include<fstream>
                using namespace std;

                int main(){
                        string st2;
                        // Opening files using constructor and reading from it
                        ifstream in("samplefile.txt"); // read operation
                        in>>st2; // reads one word till space or new line & in is an object name and can be any
                        getline(in,st2);  //reads whole line 
                        cout<<st2;
                        return 0;
                }
```
Program to let user enter name store it in a file and read the content :
```cpp
                #include<iostream>
                #include<fstream>
                using namespace std;

                int main(){
                        // connecting our file with hout stream
                        ofstream hout("samplefile.txt");  // opening file using first method i.e constructor
                        string name;
                        cout<<"Enter your name ";
                        cin>>name;
                        // writing a string to the file
                        hout<<"My name is "+ name;
                        hout.close(); // will close the output stream
                        // connectig our file with hin stream
                        ifstream hin("samplefile.txt");
                        string readname;
                        // reading line from the file
                        getline(hin,readname);
                        cout<<readname;
                        hin.close();
                        return 0;
                }
```        
## Reading from a file using .eof() end of file function -
```cpp
                #include<iostream>
                #include<fstream>
                #include<string>
                using namespace std;

                int main(){
                        ofstream out;
                        out.open("samplefile.txt");  // opening file the other way using member function of class
                        out<<"This is me \n";
                        out<<"This also me \n";
                        out<<"This is also also me  \n";
                        out.close();
                        ifstream in;
                        string st;
                        in.open("samplefile.txt");
                        while(in.eof()==0){           // .eof() is used for end of file
                                getline(in,st);
                                cout<<st<<endl;
                        }
                        in.close();
                        return 0;
                }
```

## Templates in C++ 
Templates are also known as classes with parameters because here we declare only one class and can call
that class with multiple datatypes. A template is a base for many classes.

Syntax for Class template-
```cpp
                template <class t>   // t can be anything float char int
                class vector{
                        t *arr;
                        public:
                        vector(){};   // coding of class a usual
                }
                int main(){
                        vector<int> myvector(constrcutor args if any) // creating object with template
                        vector<float> myfloatvector();
                }
        Using Class templates to find out dot-product :
                #include<iostream>
                using namespace std;

                template <class t>   // using template
                class vector{
                        public:
                        t *arr;
                        int size;
                        vector(int m){
                                size=m;
                                arr=new t[size];
                        } 
                        t dotproduct(vector &v){
                                t d=0;
                                for(int i=0;i<size;i++){
                                        d+=this->arr[i]*v.arr[i];
                                }
                                return d;
                        }
                };

                int main(){
                        vector<float> v1(3);
                        v1.arr[0]=1.4;
                        v1.arr[1]=3.3;
                        v1.arr[2]=0.1;
                        vector<float> v2(3);
                        v2.arr[0]=0.1;
                        v2.arr[1]=1.90;
                        v2.arr[2]=4.1;
                        float a=v1.dotproduct(v2);
                        cout<<a<<endl;
                        return 0;
                }
```

### Class Templates with multiple parameters
Syntax-
```cpp
                template <class t1,class t2,as much you want>
                class anything{
                        class body;
                }
                int main(){
                        anything_class<int,float> obj1;
                }
```        
Example:
```cpp
                #include<iostream>
                using namespace std;

                template <class t1,class t2>
                class myclass{
                        public:
                        t1 data1;
                        t2 data2;
                        myclass(t1 a,t2 b){
                                data1=a;
                                data2=b;
                        }
                        void display(){
                                cout<<this->data1<<endl;
                                cout<<this->data2<<endl;
                        }
                };

                int main(){
                        myclass<int,char> obj(7,'c');
                        obj.display();
                        return 0;
                }
```
### Class Templates with default parameters
Synatax :
```cpp
                template <class t1=int,class t2=float>
                class myclass{
                        body
                }
                int main(){
                        myclass <> obj1
                }
```

Example -
```cpp
               #include<iostream>
                using namespace std;

                template <class t1=int,class t2=float>  // declaring template with default args
                class chetan{
                        public:
                        t1 a;
                        t2 b;
                        chetan(t1 a,t2 b){
                                this->a=a;
                                this->b=b;
                        }
                        void display(){
                                cout<<"The value of a is "<<a<<endl;
                                cout<<"The value of a is "<<b<<endl;
                        }

                };

                int main(){
                        chetan<> c(4,6.7);  // uses defult suppiled datatypes when no args passed
                        c.display();
                        chetan<int,char> c1(4,'c');  // over-riding default args
                        c1.display();
                        return 0;
                }
```                

## Function Template in C++
Aame syntax as class templates refer the example below :
```cpp
                #include<iostream>
                using namespace std;

                template <class t1,class t2>
                float funcaverage(t1 a,t2 b){
                        t2 avg=(a+b)/2;
                        cout<<"Your average is "<<avg<<endl;
                }

                int main(){
                        funcaverage(6,6.45);
                        return 0;
                }
```                

## Member Function Templates & Overloading Template Functions
We can even overload function with same name where some functions are templatised and some are simple functions

Example -
```cpp
                #include<iostream>
                using namespace std;

                template <class t>
                class chetan{
                        public:
                        t data;
                        chetan(t a){
                                data=a;
                        }
                        void display();
                };
                template <class t>
                void chetan<t> :: display(){  // this is the way to write templatised function outside class
                        cout<<data<<endl;
                } 

                int func(int a){
                        cout<<"I am normal func() "<<endl;
                }

                template <class t>
                void func(t a){
                        cout<<"I am templatised func() "<<endl;
                }

                int main(){
                        chetan<char> obj1('c');
                        obj1.display();
                        func(4); // here normal func() will be called due to highest priority of exact match
                        func('c'); // templatised func will be called
                        return 0;
                }
```

## Standard Template Library (STL)
It is a libraray of generic classes and functions. Because when we use STL we are resuing well tested  components.

Components of STL :
1. `Containers` - stores data and uses template classes
2. `Algorithms` - Procedure to process data and used to do various works like searching sorting and uses template functions
3. `Iterators` - Object point to an element in a container. It is handeled just like pointers and connects Algorithms with containers.

Types of Containers :
1. `Sequence containers` - stores data in linear fashion eg- vector, list, dequeue
2. `Associative containers` - use to direct access data/fast access eg- set, multiset, map, multimap
3. `Derived containers` - Real world modelling eg- stack , queue, priority queue
        
### Vector -
1. Random Access = fast
2. Insertion/Deletion at middle = slow
3. Insertion/Deletion at the end = fast
        
### List -
1. Random Acess =slow
2. Insertion/Deletion at middle = fast
3. Insertion/Deletion at the end = fast
        
- Associative Containers - All operations fast except random access
- Derived Conatiners - Depends

### Vectors
Vectors are sequence containers representing arrays that can change in size.
syntax:
```cpp
                vector<datatype> variable_name;
```                
Synatax or creating iterators:
```cpp
                vector<datatype> :: iterator iteratorname = vectorname.begin();
```                
Example to understand Vector :
```cpp
                #include<iostream>
                #include<vector>
                using namespace std;

                void display(vector<int> &v){
                        for(int i=0;i<v.size();i++){
                                cout<<v[i]<<" ";
                        }
                        cout<<endl;
                }

                int main(){
                        vector<int> vec1; // creating zero length integer vector
                        vector<char> vec2(5); // 5-element character vector
                        vector<char> vec3(vec2); // 5-element character vector from vec-2
                        vector<int>vec4(3,4);// will display 4 but 3 times
                        int element;
                        for (int i=0;i<4;i++){
                                cout<<"Enter an element to add to this vector "<<endl;
                                cin>>element;
                                vec1.push_back(element);  // adds element to last
                        }
                        // vec1.pop_back();  // removes last element
                        display(vec1);
                        vector<int> :: iterator iter = vec1.begin(); // creating an iterator named iter which is basically a pointer pointing to first element
                        // vec1.insert(iter,566); // inserting new element at position iter
                        // display(vec1);
                        vec1.insert(iter+1,5,788); // will add 788 5 times
                        display(vec1);
                        display(vec4);
                        return 0;
                }
```

## List in C++
must include list as a header file to use

Various functions of list through a program :
```cpp
                #include<iostream>
                #include<list>
                using namespace std;

                void display(list<int> &lst){
                        list<int> :: iterator it;
                        for(it=lst.begin();it!=lst.end();it++){
                                cout<<*it<<" ";
                        }
                        cout<<endl;

                }

                int main(){
                        list<int> list1; //list of 0 length
                        list<int> list2(3); // empty list of sie 7
                        list1.push_back(5); // adds element at the last of the list
                        list1.push_back(7);
                        list1.push_back(1);
                        list1.push_back(9);
                        list1.push_back(12);
                        display(list1);
                        list<int> :: iterator iter;
                        iter=list2.begin();
                        *iter=34;
                        iter++;
                        *iter=99;
                        iter++;
                        *iter=14;
                        display(list2);
                        list1.pop_back(); // deletes the last element in the list
                        list1.remove(1); // remove all occurences of the given element
                        list1.sort(); // sorts the list
                        list1.merge(list2); // merges the list 
                        list1.reverse(); // reverses the list
                        list1.swap(list2); // swaps the contents of the list
                        display(list1);

                        return 0;
                }
``` 

## Map in C++ ( Can be considered like an object in Javascript or Dictionary in Python )
Maps are associative containers that store elements in a mapped fashion. Each element has a key value and a mapped value. No two mapped values can have the same key values.

Basic Functions with map -
1. `begin()` – Returns an iterator to the first element in the map.
2. `end()` – Returns an iterator to the theoretical element that follows the last element in the map.
3. `size()` – Returns the number of elements in the map.
4. `max_size()` – Returns the maximum number of elements that the map can hold.
5. `empty()` – Returns whether the map is empty.
6. `pair insert(keyvalue, mapvalue)` – Adds a new element to the map.
7. `erase(iterator position)` – Removes the element at the position pointed by the iterator.
8. `erase(const g)` – Removes the key-value ‘g’ from the map.
9. `clear()` – Removes all the elements from the map.
        
Example -
```cpp
                #include<iostream>
                #include<map>
                #include<string>
                using namespace std;

                int main(){
                        map<string,int> marksmap;
                        marksmap["chetan"]=99;
                        marksmap["rohan"]=73;
                        marksmap["gohan"]=14;
                        map<string,int> :: iterator iter;
                        marksmap.insert({{"newentry",1}}); // inserting a new element
                        iter=marksmap.begin(); // setting iter to beginning of map
                        for(iter=marksmap.begin();iter!=marksmap.end();iter++){ 
                                cout<<(*iter).first<<" "<<iter->second<<"\n"; // accessing key and value using iter(pointer)
                        }
                        cout<<"The size is: "<<marksmap.size(); // size of map
                        return 0;
                }
```

## Function Objects in C++ or Functor
- To use must include header file functional
- Function wrapped in a class so that it is available like an object

Example -
```cpp        
                #include<iostream>
                #include<functional>
                #include<algorithm>
                using namespace std;

                int main(){
                        int arr[]={1,2,55,67,88,9};
                        sort(arr,arr+5,less<int>()); // sorts from 1 to 5 and the function object less<int>() implements x<y
                        for(int i=0;i<6;i++){
                                cout<<arr[i]<<endl;
                        }
                        return 0;
                }
```                
