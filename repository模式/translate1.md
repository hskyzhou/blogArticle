##Using Repository Pattern in Laravel 5
## 在laravel5中使用仓库模式

These days there is a lot of buzz about software design patterns, and one of the most frequently asked questions is “How can I use some pattern with some technology“.
这些天有许多关于软件设计模式的嗡嗡声，并且其中最常见的问题是"我如何在某些技术中使用某种模式"

 In the case of Laravel and the Repository pattern, I see often questions like “How I can use repository pattern in Laravel 4” or nowadays “..in Laravel 5”.
 如果是在laravel和仓库模式下，我通常看到的问题, 如 "我如何在laravel4中使用仓库模式", 或者如今的"...在laravel5中".

Important thing you must remember is that design patterns do not depend on specific technology, framework or programming language.
你必须要记得的事情是, 设计模式不依赖特定技术，框架或者编程语言.

Contents 内容 
1 Introduction  介绍
2  It’s all about interfaces 所有的接口
3 Directory structure  目录结构
4 A Repository Implementation 仓库实现
5 Criteria Queries 条件查询
5.1 Creating A New Criteria 创建一个新条件
5.2 Using Criteria In The Controller 在控制器中使用条件
6 Package Installation 安装包
7 Conclusion 讨论 
8 Credits 关于作者

### Introduction 介绍
If you have really understood Repository Pattern then it does not matter what framework or programming language you are going to use. 
如果你真正理解设计模式跟你正在使用的框架或者编程语言没有关系。
What is important is that you understand the principle behind the Repository pattern. 
理解仓库模式背后的本质才是重要的
Then you can implement it in whatever technology you want. 
然后你可以实现它用你想用的任何技术。
With that in mind, let’s start with the definition of the Repository pattern:
记住这一点之后，让我们开始仓库模式的定义:

A Repository mediates between the domain and data mapping layers, acting like an in-memory domain object collection. 
仓库在领域逻辑和数据映射出呢过,就像内存领域对象集合
Client objects construct query specifications declaratively and submit them to Repository for satisfaction. 
客户对象声明性的构造查询规范并且提交到仓库为了满足情况。
Objects can be added to and removed from the Repository, as they can from a simple collection of objects, and the mapping code encapsulated by the Repository will carry out the appropriate operations behind the scenes.
客户可以从仓库被添加和移除,