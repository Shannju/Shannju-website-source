---
title: c++ | STL之vector
date: 2022-10-01 00:00:00
categories:
- 学习
tags:
- c++
---



 

> 2023年3月1日更新
>
> 南京大学计算机科学与技术系 2022年秋 高级程序设计课程期末考试中，最后一题是手写模板类vector 。



STL 标准模板库（Standard Template Library，*STL*） 是写cpp时很容易遇到的一个库，非常的好用。

>  标准模板库（Standard Template Library，STL）是[惠普实验室](https://baike.baidu.com/item/惠普实验室/489303?fromModule=lemma_inlink)开发的一系列软件的统称。它是由Alexander Stepanov、Meng Lee和David R Musser在[惠普实验室](https://baike.baidu.com/item/惠普实验室/489303?fromModule=lemma_inlink)工作时所开发出来的。虽说它主要出现到C++中，但在被引入C++之前该技术就已经存在了很长时间。STL的代码从广义上讲分为三类：algorithm（算法）、container（容器）和iterator（[迭代器](https://baike.baidu.com/item/迭代器/3803342?fromModule=lemma_inlink)），几乎所有的代码都采用了[模板类](https://baike.baidu.com/item/模板类/6768650?fromModule=lemma_inlink)和模板函数的方式，这相比于传统的由函数和类组成的库来说提供了更好的代码重用机会。 
>
> ---baidu

借此高级程序设计上机的好机会，在此复习一下我STL中最喜欢的vector，这是我唯一自己半实现过的库，斗胆称一声略微了解。

**c++有了vector，就像南大有了麦当当，以色列有了耶路撒冷！**你可以忘记动静态数组忘记越界访问忘记烫烫烫的往事。与其他的容器比较，vector是和数组最相似的：里面什么都能放，无论结构体还是vector套vector；顺序存储，支持下标访问；迭代器与其他的不同可以每次加n。如果课程没有特殊要求，又不想使用数据库来管理文件，vector一定是我们的首选。

那么就来看一看吧

### 1. 构造vector

```cpp
  vector<int> v0;
  vector<int> v1(10); // vector(int nSize):创建一个vector,元素个数为nSize

  vector<char> v2(10, 'A');
  // vector(int nSize,const t& t):创建一个vector，元素个数为nSize,且值均为t

  //数组方式
  int i[5] = {1, 2, 3, 4, 5};
  vector<int> v3(i, i + 2);  //得到i索引值为3以后的值 {3,4,5}
  vector<char> v4(i, i + 2); //可以转化类型
  vector<vector<int>> v5;    //二位vector 成员是一个一维的vector< int>

  //迭代器方式--迭代器见后面
  // vector(begin,end):复制[begin,end)区间内另一个数组的元素到vector中
  string str("1234567890");                //直接创建一个String类的字符串
  vector<char> v6(str.begin(), str.end()); //利用迭代器获取起始和末尾的位置,进行输出

```

### 容量

**Capacity**

1. [size()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns the number of elements in the vector.
2. [max_size()](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/) – Returns the maximum number of elements that the vector can hold.
3. [capacity()](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/) – Returns the size of the storage space currently allocated to the vector expressed as number of elements.
4. [resize(n)](https://www.geeksforgeeks.org/vector-resize-c-stl/) – Resizes the container so that it contains ‘n’ elements.
5. [empty()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns whether the container is empty.
6. [shrink_to_fit()](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/) – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.
7. [reserve() ](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/)– Requests that the vector capacity be at least enough to contain n elements.

### 访问

#### 数组访问

```c
 for （i=0;i<v.size();i++）
	visit arr [i] //略
```

#### 迭代器访问

```CPP
 vector<int>::iterator it;
//*声明一个迭代器，来访问vector容器，作用：遍历或者指向vector容器的元素*/
//or
auto ite;
*for* (ite = obj.begin(); ite != obj.end(); ite++)
{
 cout << *ite << " ";
}
```

### 增删

#### push_back pop_back

主要是在尾部插入元素：push_back(elem)和尾部弹出元素：pop_back()

```cpp
pop_back()//无输入无返回值
push_back(elem)//放一个类型一样的元素插在最后，无返回
```

这两个都很友好，但是...

#### clear()

清除容器中所有数据

#### erase

删除指定元素：erase（）看着很强大的一个函数，其实会导致下标的变化，于是遍历变得困难，

> erase函数可以用于删除vector容器中的一个或者一段元素，
>
> 在删除一个元素的时候，其参数为**指向相应元素的迭代器**，
>
> 而在删除一段元素的时候，参数为指向一段元素的**开头的迭代器**以及指向**结尾元素的下一个元素的迭代器；**
>
> 在进行单个元素删除后，传入的迭代器指向不变，仍然指向被删除元素的位置，而被删除元素之后的所有元素都向前移动一位，也就是该迭代器实际上是**指向了原来被删除元素的下一个元素**。
>
> 删除一段元素后，传入的迭代器指向也是不变的，仍然指向原来传进去时候的位置，修改的是删除段后面的元素的位置。



