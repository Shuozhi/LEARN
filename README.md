（很多都是从别的地方粘贴来的，比较方便嘛～ 我没说是我自己写的哦）

OPPO提前批面试：
突然发现C/C++的一个关键。C++有啥特殊性呢？还不就是贴近底层，这就是它的特点也是它的优势。那我怎么可以忽略内存管理方面的知识呢？！现在开始学吧！
C++学习从浅入深：
https://www.cnblogs.com/luoxn28/p/5510656.html

C语言知识整理（3）：内存管理（详细版）：
https://www.cnblogs.com/yif1991/p/5049638.html


C++变量类型：
       基本类型
                int
                double
                ...
       复合类型
                引用
                指针
                const
       标准库类型
                string
                vector
                迭代器
                pair
       内置数组
                一维数组
                多维数组
内置类型就是最底层的最基本类型，标准库就是经过加工基本库，基本类型就那么几种，int char，double ，经过包装后，形成了很多的模板类，string类型，它比char类型多了什么呢，多了很多的操作，string类包含了基本的加减寻找等操作，比char强大多了。
内置类型指的是C++的标准数据类型，比如int、double...还有由这些类型衍生出的数组、指针等等。
vector是c++标准程序库STL中的成员，一般称为容器(container)，除了vector外，STL还有deque、map、list等等。
内置数据类型是最基本的数据类型，标准库类是一个一个的C++对象



容器的理解：
C++ 语言的核心优势之一就是便于软件的重用。C++ 中有两个方面体现重用：
一是面向对象的继承和多态机制；
二是通过模板的概念实现了对泛型程序设计的支持。
C++ 的标准模板库（Standard Template Library，STL）是泛型程序设计最成功应用的实例。STL 是一些常用数据结构（如链表、可变长数组、排序二叉树）和算法（如排序、查找）的模板的集合，主要由 Alex Stepanov 主持开发，于 1998 年被加入 C++ 标准。
有了 STL，程序员就不必编写大多数常用的数据结构和算法。而且 STL 是经过精心设计的，运行效率很高，比水平一般的程序员编写的同类代码速度更快。
有一种说法，C++ 是用来编写大程序的，如果只是编写几十上百行的小程序，用C语言就可以，没有必要用 C++。
这个说法是不准确的。可以说，写小程序没必要用面向对象的方法，但是用 C++ 还是能够带来很大方便的，因为 C++ 中有 STL。哪怕编写只有十几行的程序，也可能会用到 STL 中提供的数据结构和算法。例如对数组排序，用 STL 中的 sort 算法往往只需要一条语句就能解决，而不用像调用C语言库函数 qsort 那样还要编写比较函数。

数组和容器的区别：
创建方式：
创建数组时必须指定其大小；
而容器不必指定，可动态改变其大小。
存储方式：
数组在内存空间上是连续存储的；
而容器中顺序容器vector和deque是连续存储的（deque与vector 不同的是它支持高效地在其首部插入和删除元素），但list是链式存储的。
访问效率：
访问数组元素时可根据数组下标直接访问相应位置的元素；而容器中顺序容器vector和deque支持对元素的随机访问(也支持下标访问元素，或at()函数，如ivec.at(5)返回容器ivec中第6个元素)，但list不支持。
元素操作：
list支持在容器中间位置插入或删除元素，而其他的不支持。

泛型算法：
泛型算法是STL库里面定义的一些算法，这些算法可以用一个接口操作各种数据类型，因此成为泛型算法。大多算法定义在头文件algorithm和numeric中。意思就是可以用一个接口操作各种类型的算法就是泛型算法。
记住一些泛型算法，还是很必要的，有时候自己写的超长函数功能，其实调用一个库里面自带的函数就解决了。



C++中，有哪4种与类型转换相关的关键字？各有什么特点？应该在什么场合下使用: 
C++中，四个与类型转换相关的关键字：static_cast、const_cast、reinterpret_cast、dynamic_cast。
static_cast
特点：静态转换，在编译处理期间。 
应用场合：主要用于C++中内置的基本数据类型之间的转换，但是没有运行时类型的检测来保证转换的安全性。
用于基类和子类之间的指针或引用之间的转换，这种转换把子类的指针或引用转换为基类表示是安全的；进行下行转换，把积累的指针或引用转换为子类表示时，由于没有进行动态类型检测，所以是不安全的。
把void类型的指针转换成目标类型的指针（不安全）。
不能用于两个不相关的类型转换。
不能把const对象转换成非const对象。
const_cast
特点：去常转换，编译时执行。 
应用场合：const_cast操作不能在不同的种类间转换。相反，它仅仅把它作用的表达式转换成常量。它可以使一个本来不是const类型的数据转换成const类型的，或者把const属性去掉。 
reinterpret_cast
特点： 重解释类型转换 
应用场合：它有着和c风格强制类型转换同样的功能；它可以转化任何的内置数据类型为其他的类型，同时它也可以把任何类型的指针转化为其他的类型；它的机理是对二进制进行重新的解释，不会改变原来的格式。
dynamic_cast < type-id > ( expression )
该运算符将expression转换成type_id类型的对象。type_id必须是类的指针，类的引用或者空类型的指针。
　　a、如果type_id是一个指针类型，那么expression也必须是一个指针类型，如果type_id是一个引用类型，那么expression也必须是一个引用类型。
　　b、如果type_id是一个空类型的指针，在运行的时候，就会检测expression的实际类型，结果是一个由expression决定的指针类型。
　　c、如果type_id不是空类型的指针，在运行的时候指向expression对象的指针能否可以转换成type_id类型的指针。
　　d、在运行的时候决定真正的类型，如果向下转换是安全的，就返回一个转换后的指针，若不安全，则返回一个空指针。
　　e、主要用于上下行之间的转换，也可以用于类之间的交叉转换。上行转换时和static_cast效果一样，下行转换时，具有检测功能，比static_cast更安全



操作系统：

1）用户态切换到内核态的3种方式  
a. 系统调用  
这是用户态进程主动要求切换到内核态的一种方式，用户态进程通过系统调用申请使用操作系统提供的服务程序完成工作，而系统调用的机制其核心还是使用了操作系统为用户特别开放的一个中断来实现，例如Linux的int 80h中断。 
系统调用实质上是一个中断，而汇编指令int 就可以实现用户态向内核态切换，iret实现内核态向用户态切换  
b. 异常  
当CPU在执行运行在用户态下的程序时，发生了某些事先不可知的异常，这时会触发由当前运行进程切换到处理此异常的内核相关程序中，也就转到了内核态，比如缺页异常。  
c. 外围设备的中断  
当外围设备完成用户请求的操作后，会向CPU发出相应的中断信号，这时CPU会暂停执行下一条即将要执行的指令转而去执行与中断信号对应的处理程序，如果先前执行的指令是用户态下的程序，那么这个转换的过程自然也就发生了由用户态到内核态的切换。比如硬盘读写操作完成，系统会切换到硬盘读写的中断处理程序中执行后续操作等。   
这3种方式是系统在运行时由用户态转到内核态的最主要方式，

其中系统调用可以认为是用户进程主动发起的，异常和外围设备中断则是被动的。   

2）具体的切换操作  
从触发方式上看，可以认为存在前述3种不同的类型，但是从最终实际完成由用户态到内核态的切换操作上来说，涉及的关键步骤是完全一致的，没有任何区别，都相当于执行了一个中断响应的过程，因为系统调用实际上最终是中断机制实现的，而异常和中断的处理机制基本上也是一致的，关于它们的具体区别这里不再赘述。关于中断处理机制的细节和步骤这里也不做过多分析，涉及到由用户态切换到内核态的步骤主要包括：  
[1] 从当前进程的描述符中提取其内核栈的ss0及esp0信息。  
[2] 使用ss0和esp0指向的内核栈将当前进程的cs,eip,eflags,ss,esp信息保存起来，这个  
过程也完成了由用户栈到内核栈的切换过程，同时保存了被暂停执行的程序的下一  
条指令。  
[3] 将先前由中断向量检索得到的中断处理程序的cs,eip信息装入相应的寄存器，开始  
执行中断处理程序，这时就转到了内核态的程序执行了。

(55）源代码到可执行文件过程
.c文件经过编译器、汇编器之后得到目标文件.o，目标文件再与库进行链接得到可执行文件.out。 
库其实就是一组目标文件的打包，这些目标文件中都是一些常用的代码。
看操作系统笔记本第三章

