#### static

1. 修饰**全局变量**时，表明一个全局变量只对定义在同一文件中的函数可见。
2. 修饰**局部变量**时，表明该变量的值不会因为函数终止而丢失。
3. 修饰**函数**时，表明该函数只在同一文件中调用。
4. 修饰**类的数据成员**，表明对该类所有对象这个数据成员都只有一个实例。即该实例归 所有对象共有。
5. 用static修饰不访问非静态数据成员的**类成员函数**。这意味着一个静态成员函数只能访问它的参数、类的静态数据成员和全局变量。

#### 类型转换

static_pointer_cast、dynamic_pointer_cast、const_pointer_cast、reinterpret_pointer_cast都是针对智能指针的，如果不加pointer的话，就是针对裸指针进行的转换。

#### 可变参数模板（variadic templates）
>TODO


#### tuple和struct的区别

能用struct还是用struct吧，因为tuple在内存中的存储方式不定？字节对齐的问题

#### std::function

```
template <class Ret, class... Args> class function<Ret(Args...)>;
```

封装各种可调用实体（普通函数、Lambda表达式、函数指针、以及其它函数对象等）。

```c++
    typedef std::function<unsigned long (unsigned long *value)> GetConfigParameterFnPtr;
    typedef std::function<unsigned long (unsigned long value)> SetConfigParameterFnPtr;
```

封装了返回值类型为unsigned long，参数类型为一个unsigned long的函数。



#### using和typedef的区别

在定义一般类型的别名时功能是一样的。

区别

1. 可读性

   以函数指针为例

   ```c++
   typedef void (*FP) (int, const std::string&);
   using FP = void (*) (int, const std::string&);
   //这两句话都定义了一个返回值为空，参数为int和string的一个函数指针的别名
   //很明显下面的可读性更好理解
   ```

2. 定义模板别名

   using能够定义模板别名，typedef不可以。





