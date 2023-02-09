# 数据结构

## 第一节 绪论

### 基础概念：

三要素：逻辑结构、存储结构、数据的运算

抽象数据类型（ADT）：数据对象、数据关系、基本操作集合

逻辑结构：

1. 线性：一般线性表、栈、队列、串、数组、广义表
2. 非线性：集合、树、图

存储结构：顺序、链式、索引、散列

数据运算

## 第二节 线性表

### 定义：

相同数据类型  有限序列  可以为空表

有且仅有一个直接前驱、一个直接后继

### 基本操作：

初始化表：InitList(&L)

求表长：Length(L)

按值查找操作：LocateElem(L,e)

按位查找操作：GetElem(L,i)

插入操作：ListInsert(&L,i,e)在第i个位置上插入指定元素e

删除操作：ListDelete(&L,i,e)删除第i个位置上的元素，并用e返回删除元素的值。

输出操作：PrintList(L)

判空操作：Empty(L)

销毁操作：DestoryList(&L)  销毁线性表，并释放线性表L所占用的内存空间

### 顺序表

特点：表中元素的逻辑顺序与其物理顺序相同

线性表中的元素的位序是从1开始的，数组元素下表从0开始

#define InitSize 100

typedef struct{

ElemType *data;

int MaxSize,length;

}SeqList;

C:初始动态分配语句为

L.data = (ElemType*)malloc(sizeof(ElemType)*InitSize);

C++:初始动态分配语句为

L.data = new ElemType[InitSize];

随机访问。时间O（1）

存储密度高，每个节点值存储数据元素

因为物理相邻，所以插入及删除需要移动大量元素。

### 单链表

节点结构：data  next

tyoedef struct LNode{       //定义单链表结点类型

​	ElemType data;              //数据域

​	struct LNode *next;      //指针域

}LNode,*LinkList;