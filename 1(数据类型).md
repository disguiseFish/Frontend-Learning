
一.数据类型
1.What data types does JavaScript have and how do they differ(1.JavaScript有哪些数据类型，它们的区别？)
 
JavaScript has eight data types: Undefined, Null, Boolean, Number, String, Object, Symbol, and BigInt.(JavaScript共有八种数据类型，分别是...)

Where Symbol and BigInt are new data types in ES6:(其中 Symbol 和 BigInt 是ES6 中新增的数据类型：)
Symbol represents a unique and immutable data type created to resolve possible global variable conflicts.(Symbol 代表创建后独一无二且不可变的数据类型，它主要是为了解决可能出现的全局变量冲突的问题。)

BigInt is a numeric type of data that can represent integers in any precision format. BigInt can be used to safely store and manipulate large integers, even if the Number is outside the range of safe integers that number can represent.(BigInt 是一种数字类型的数据，它可以表示任意精度格式的整数，使用 BigInt 可以安全地存储和操作大整数，即使这个数已经超出了 Number 能够表示的安全整数范围。)

These data can be divided into raw data types and reference data types:(这些数据可以分为原始数据类型和引用数据类型：)

Stack: raw data type(栈：原始数据类型（Undefined、Null、Boolean、Number、String）)

Heap: References data types (objects, arrays, and functions)(堆：引用数据类型（对象、数组和函数）)

The difference between the two types is the storage location:(两种类型的区别在于存储位置的不同：)

The original data type is a simple data segment directly stored in the stack, which occupies a small space and has a fixed size, and belongs to the frequently used data, so it is stored in the stack;(原始数据类型直接存储在栈（stack）中的简单数据段，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储；)

An object whose data type is stored in the heap, occupying a large space and having an unfixed size. If stored in the stack, it will affect the performance of the program. The reference data type stores a pointer on the stack that points to the starting address of the entity in the heap. When the interpreter looks for a reference value, it first retrieves its address in the stack and then retrieves the entity from the heap.(引用数据类型存储在堆（heap）中的对象，占据空间大、大小不固定。如果存储在栈中，将会影响程序运行的性能；引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址。当解释器寻找引用值时，会首先检索其在栈中的地址，取得地址后从堆中获得实体。)


The concepts of heap and stack exist in data structures and operating system memory(堆和栈的概念存在于数据结构和操作系统内存中，在数据结构中：)

 In the data structure, the access mode of the data in the stack is first in, last out.(在数据结构中，栈中数据的存取方式为先进后出。)

 The heap is a priority queue that is sorted by priority, which can be specified by size.(堆是一个优先队列，是按优先级来进行排序的，优先级可以按照大小来规定。)

In operating systems, memory is divided into stack and heap areas:(在操作系统中，内存被分为栈区和堆区：)

 The stack memory is automatically allocated and released by the compiler to store the parameter values of functions and the values of local variables. It operates like a stack in a data structure.(栈区内存由编译器自动分配释放，存放函数的参数值，局部变量的值等。其操作方式类似于数据结构中的栈。)

Heap area memory is usually freed by the developer allocation, and if the developer does not free it, it may be reclaimed by the garbage collection mechanism at the end of the program.(堆区内存一般由开发着分配释放，若开发者不释放，程序结束时可能由垃圾回收机制回收。)