# [《Design Patterns In Modern C++》](https://book.douban.com/subject/30200080/) 的中文版翻译

## 动机

1. 这本书本身是用Modern C++编写的，我是出于熟悉Modern C++用法的目的来学习这本书的代码示例。
2. 因为上过设计模式的课，虽然绝大部分都忘了，但是很容易捡起来，看起来也很熟悉，英文原版我大致浏览了下也不复杂，内容上我应该能hold住。
3. 在比较嘈杂或短的空闲时间也可以翻译，翻译这件事总是有一点点进度的，而且有时候看其他东西或写代码累了来搞下翻译还是可以的。


## to-do

- [x] Chapter1: Introduction. 我直接使用了[@soyoo的翻译结果](https://github.com/soyoo/design_patterns_in_modern_cpp_zh_sample)
- [ ] Chapter2: Builder.
- [x] Chapter3: Factories. 涉及工厂方法、工厂、内部工厂、抽象工厂和函数工厂。



## 一篇引文：从vtable到设计模式——我的C++面向对象学习心得

### 前言

按照很多教程的内容安排，学习C++语法以后很快就会进入到面向对象的学习，在初学者的心中，面向对象有非常重要的地位。但是如何才能快速学习面向对象、多久学会面向对象才算正常，这是新手常见的问题。

面向对象的语法书上都有说，vtable的原理也有非常多的文章进行讲述，这些东西再一再重复没有意义，我想写一些我自己在学习过程中的心得体验。

关于面试对象的语法知识，我唯一觉得需要强调的就是对于vtable的实现，推荐大家用实验的方法，一定要自己写代码亲自操作一遍（按照随便一篇vtable原理的文章动手操作一遍即可），无论是通过单步调试去查看vtable，还是通过编译器的各种命令来查看，都要自己亲自动手操作一下，加深印象。

面向对象的语法风格出现以后，无数的程序员基于这些特性写出了很多代码，各显神通，后来被总结提取出一些可复用的方法论，叫做「设计模式」。设计模式是学习和掌握面向对象思想的重要课程。那么问题来了，何时学习设计模式？如何学习？在理解设计模式之前应该做什么、能做什么？

### 封装、继承、（运行时）多态，哪个才是面向对象最重要的特征

所有的人都知道，面向对象的三大特征是封装继承多态（这里的多态指的是运行时多态，本文中所有多态均指运行时多态），那么哪个特征才是面向对象最重要的特征呢？

先说封装。其实C语言的struct也是一种封装，所以封装并不是面向对象所独有。再看继承，继承可以非常方便地重用代码，相对面向过程来说是一种非常强大的功能，在面向对象刚被发明出来不久的一段时间里，继承被很多人看成面向对象最强大的特征。

到后来，人们发现面向对象最强大的特征是多态，因为代码不仅仅是需要重用，扩展也很重要。「设计模式」中，几乎每种模式，都是用多态来实现的。

一个问题：只支持多态，不支持继承的编程语言，算是面向对象的编程语言吗？

我的答案：不是。虽然继承不如多态重要，但是它不是多余的。多态往往是配合继承才更强大。

### 设计模式的意义

设计模式对于如何用面向对象的思想解决软件中的设计和实现问题提供了一些可重用的思路，它还有一个重要的意义，就是为每种设计思路都取了名字，便于程序员之间的交流。

有些人在设计类的名字的时候就包含了使用的设计模式，比如一个使用了adapter模式的类名字叫xxxAdapter；xxxFactory一看就知道它使用了factory模式，给其它使用和维护这些代码的人节省了大量的时间。

### 何时开始学习设计模式

知乎上见过一个问题：『你想对刚毕业的人说些什么』，这个问题就是一个刚踏入社会的小鲜肉，向在社会上摸爬滚打多年的人取经，想获得一些生存闯关的金句宝典，从而让自己少踩坑。

这样的问题的答案有意义吗？有一些是有的，可以直接理解，但是很多是要结合自己过去的经验教训才能有体会的，知道得早也没有什么收获。

如果面向对象的初学者也提问：「你想对刚学习面向对象的人说什么？」，答案就在设计模式这本书中。

所以何时开始学习设计模式呢？我的答案是任何时候都可以。但是唯一要注意的就是，不要强迫自己去理解，设计模式的书可以摆在那里，想看就看一下，能理解多少就理解多少。但是越早看设计模式这本书，共鸣就越少，因为共鸣是要结合自己写面向对象代码的经验的。

学习面向对象几年以后再看设计模式是否可以行？

我觉得可行，结合自己几年之内在学习各种面向对象的库和自己写代码的经验，学习设计模式会很快。

永远不学设计模式行不行？

我觉得不行，我前面提到了，设计模式不仅仅是总结思想，思想可以通过模仿现有的库来学习，但是设计模式还有一个重要的作用是给模式命名，命名可以更好地与其他程序员沟通交流。

### 如何学习设计模式(即如何学习C++的面向对象思想)

除了学习C++语法，还需要学习一下UML类图，不会的自己去搜，UML有好几种图，其中类图、状态图、序列图最为常用，学这3种即可。

在C++中可以通过学Qt库来学习面向对象。Qt除了可以用来写跨平台的UI，还可以写一些简单的网络程序，在学校里可以用来做各种大作业，无论是学生成绩管理系统、图书管理系统、足球俱乐部，等等，用Qt都可以很好地完成。我学Qt用的是这本书：<<Qt Creator 快速入门 霍亚飞著>>

Qt里面本身就用了很设计模式，从它的类里面继承一个子类，覆盖一个或几个虚函数，就可以将自己的类融入到Qt的体系中。其实这就是学习面向对象的第一步，也是最好的开始，不吃猪肉、先看猪跑，从它的类继承多了，自己也会慢慢理解如何从自己写的类继承。

学习面向对象有什么减少弯路又能加速理解的套路呢？根据我自己的经验总结，对于新手我至少可以说两点。

第一点，前面说了，面向对象最重要的是多态，多态就是使用虚函数，在自己设计的类中，将哪些成员函数定义为虚函数，这是一个重要的问题。对于新手，我的建议是：在搞清规则之前，可以将所有的成员函数都定义为虚函数。（其实在java这样的编程语言中，根本不需要程序员自己去指定哪个成员函数是virtual，从语法上来说，任何一个非static非private的都是virtual。）

在虚函数的定义上，先将所有能定义成虚函数的的成员函数全部声明为virtual，然后再在使用中慢慢做减法，根据自己的理解，将多余的virtual去掉。

第二点，在使用面向对象的时候，尽量使用父类指针，而不是子类指针。100分的设计是永远使用父类指针、永远不使用子类指针。父类指针向子类指针转换需要用dynamic_cast，不使用dynamic_cast的设计就是最好的设计。新手可以遵循这个原则。

当然，在一些非常复杂的系统中，无法做到100分，有时候还是需要向下转换成子类指针，这样的设计肯定是扣分的，但是对于复杂系统肯定有一个平衡。我自己做服务器，所有设计都可以做到永远使用父类指针，但是对于复杂的像客户端unnreal代码，向下转换几乎不可避免。

### 多久学会设计模式才算优秀

初学者都很急于求成，希望一天就能学会。但是从另一个角度来说，一天都能学会的东西，肯定不是什么有价值的东西。

我大概用了4年左右的时间，理解了面向对象。从大一开始学习C++，到大四毕业工作以后一年内设计出来了一个总共有一千多个类的系统，可以按照需求无限扩展。我现在可以设计任意多个类的系统。

我相信很多人比我更优秀，但是我更相信我自己的方法，我的学习方法其实就是不给自己设置时间期限，盲人摸象，今天摸这里明天摸那里，时间长了总会知道大象的全貌。

我是打算用几十年的时间从事编程的工作，到底是一天理解还是几年理解，对我来说并没有区别。至于做题、考试、工作等等，不用理解一样可以完成，按照现有的系统模仿即可。

我很清楚地记得，我第一次体会到面向对象的意义，是模仿MFC的一个机制。MFC在90年代的时候就做到了可以用字符串来动态创建一个对象（C++没有反射机制这在语法层面是无法做到的），MFC用的方法非常简单，将所有的类的名字和其构造函数放在一个全局的链表中，通过字符串在链表中去查找对应的构造函数，从而调用该构造函数new出对应的对象。

需要添加新的功能的时候，只要新添加一个.h一个.cpp，在两个文件中实现一个子类的代码，并调用宏将该类的构造函数添加到全局链表中。

通过添加新文件（一个.h和一个.cpp）的方法，不用修改之前的任何代码，就扩展了程序的功能，这就是面向对象的意义之一。

后来我在鹅厂做服务器，这个方法我一直使用，只是将链表改成了map或unordered_map。以后如果我找到合适的例子，我想通过例子说明此思想的应用，作为面向对象思想理解的入门级素材，我觉得挺好的，当然，那就是另外一篇文章了。

### 总结

设计模式是一些方法论，自己通过学习优秀的C++框架（如Qt）慢慢去体会和应用这些方法，最终可以慢慢理解。

不要刻意急于求成，人生很长，每一步都有它的意义，走过的路哪怕是弯路，都有它的意义。

在理解之前，注重于模仿，即使不理解，靠模仿已经能解决很多问题。

如果硬要问捷径是什么，我的答案就是抓紧时间多写代码，写了几万行代码就慢慢理解了。如果你不能改变几万行这个数字，那就去改变积累几万行代码的时间。比如说从3年缩短到2年，这完全是可能的。

我非常讨厌写长文，这篇文章在没有任何代码凑字数的情况下还是超过了3000字，也是源于我对面向对象思想的热爱，它帮我解决了很多问题，我现在用面向对象的思想来写代码，已经成了一件很自然的事情。

其实面向对象的思想在C++中并不是主流，自从90年代STL被作为标准库纳入C++那一刻起，泛型编程在C++里面就占据了上风，并且后来一直在迅速发展。同样的设计模式在C++中不仅仅可以用面向对象的思想实现，也可以用泛型编程的思想实现，不少时候后者可能更神奇更优雅更高效。

面向对象注重的是代码的扩展和维护，而不是高性能，在一些需要高性能的场合，像我所在的游戏领域需要优化性能的地方，不能用面向对象，以后如果我找到合适的例子作为素材，我会再写一篇「面向对象的缺点」的文章。



## 第三章：工厂方法和工厂模式

### 本章精要

- 工厂方法（factory method）是类的成员函数，可以作为创建对象的一种方式，通常用来替代构造函数。
- 工厂（factory）通常是知道如何创建对象的独立的类，尽管如果你传递构造对象的函数(std::function，函数指针或者函数对象)到某个函数里面，这个参数通常也被称为工厂。
- 抽象工厂（abstract factory），顾名思义，是一个抽象类，可以被生产一系列对象的具体类所继承。抽象工厂在实际中很少见。


工厂相对于构造函数调用有下面几个关键的优势：

- 工厂可以说“不”，这意味着除了选择返回一个对象外，它可以返回一个空指针(nullptr)。
- 命名更有直观意义，且不受限，不像构造函数的函数名必须和类名相同。
- 一个工厂能够生产出许多不同类型的对象。
- 工厂能够表现出多态行为，实例化一个类并通过基类的引用或指针返回实例化后的对象。
- 工厂能够实现缓存(caching)和其他存储优化，他也是其他方法，例如池或单例模式（更多参见第5章内容）实现的自然的选择。

工厂与建造者模式的不同之处在于，对于工厂，您通常一次性创建一个对象，而对于建造者，您通过部分地提供信息来分段地构造对象。

## 注意：

这本书的翻译应该是存在版权问题，但是出于学习的角度来说，如果没有很多人使用也不会有问题，至少在这个项目的初期应该不会引起其他的关注。


