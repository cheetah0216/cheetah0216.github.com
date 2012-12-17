---
layout: post
title: "Google C++ Style Guide"
category: language 
tags: [C++]
description: |
  Google C++ Style Guide翻译
---
{% include JB/setup %}

原文档[Google C++ Style Guide](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml). 
##头文件  
**每一个 `.cc` 文件都有一个对应的 `.h` 文件.也有一些常见例外, 如单元测试代码和只包含 `main()` 函数的 `.cc` 文件.**    

###define 保护
**命名格式当是: `<PROJECT>_<PATH>_<FILE>_H_`.**  
例如, 项目 `foo` 中的头文件 `foo/src/bar/baz.h` 可按如下方式保护:
{% highlight cpp %}
    #ifndef FOO_BAR_BAZ_H_  
    #define FOO_BAR_BAZ_H_  
    …  
    #endif // FOO_BAR_BAZ_H_  
{% endhighlight %}

###头文件依赖
**可以使用前置声明的地方不要使用`#include`**  
一但头文件被修改，包含该头文件的其它代码都需要被重新编译.特别是当头文件又包含其它头文件的时候.  
**什么时候使用前置声明？**  
如果头文件中使用类`Foo`,但是并不需要访问类`Foo`的声明,这是可以用前置声明`class Foo`代替`#include`,包含一下几种情况.   
<li>可以将数据成员类型声明为`Foo&` 或 `Foo*`.</li>
<li>可以将函数的参数/返回值声明(不是定义)为`Foo`类型.(有一个例外是:如果`Foo`或者`Foo&`的参数有`non-explicit`, 
`one argument construcor`,这个时候需要完整的定义去支持自动类型转换).</li> 
<li>可以将静态数据成员类型声明为`Foo`.</li>

###inline函数
**只有当函数只有 10 行甚至更少时才将其定义为内联函数.**  
对于存取函数以及其它函数体比较短, 性能关键的函数, 鼓励使用内联.当函数体比较小的时候, 内联该函数可以令目标代码更加高效. 对于存取函数以及其它函数体比较短, 性能关键的函数, 鼓励使用内联.  
<li>一个较为合理的经验准则是, 不要内联超过 10 行的函数. 谨慎对待析构函数, 析构函数往往比其表面看起来要更长, 因为有隐含的成员和基类析构函数被调用!</li>
<li>另一个实用的经验准则: 内联那些包含循环或 `switch` 语句的函数常常是得不偿失 (除非在大多数情况下, 这些循环或 `switch` 语句从不被执行).</li>
有些函数即使声明为内联的也不一定会被编译器内联, 这点很重要; 比如虚函数和递归函数就不会被正常内联. 通常, 递归函数不应该声明成内联函数.虚函数内联的主要原因则是想把它的函数体放在类定义内, 为了图个方便, 抑或是当作文档描述其行为, 比如精短的存取函数.  

###-inl.h 文件
**复杂的内联函数的定义, 应放在后缀名为 -inl.h 的头文件中.**  
<li>`inline`函数的定义放在`.h`文件中,实现放在`.c`文件中.除非在可读性和性能上有明显的优势才将实现也放在`.h`文件中.</li>
<li>如果内联函数的定义比较短小, 逻辑比较简单, 实现代码放在 `.h` 文件里没有任何问题. 比如, 存取函数的实现理所当然都应该放在类定义内. 出于编写者和调用者的方便, 较复杂的内联函数也可以放到 `.h` 文件中, 如果你觉得这样会使头文件显得笨重, 也可以把它萃取到单独的 `-inl.h` 中. 这样把实现和类定义分离开来, 当需要时包含对应的 `-inl.h` 即可.</li>
<li>`-inl.h` 文件还可用于函数模板的定义. 从而增强模板定义的可读性.</li>

###函数参数顺序
**定义函数时, 参数顺序依次为: 输入参数, 然后是输出参数.**  
C/C++ 函数参数分为输入参数, 输出参数, 和输入/输出参数三种. 输入参数一般传值或传 `const` 引用, 输出参数或输入/输出参数则是`非-const` 指针.   

###include 的路径及顺序
**使用标准的头文件包含顺序可增强可读性, 避免隐藏依赖: C 库, C++ 库, 其他库的 .h, 本项目内的 .h.**  
项目内头文件应按照项目源代码目录树结构排列, 避免使用 `UNIX` 特殊的快捷目录 . (当前目录) 或 .. (上级目录). 例如, `google-awesome-project/src/base/logging.h` 应该按如下方式包含:  
{% highlight cpp %}
    #include “base/logging.h”
{% endhighlight %}
例子:
{% highlight cpp %}
    #include "foo/public/fooserver.h" // 优先位置
    #include <sys/types.h>
    #include <unistd.h>
    #include <hash_map>
    #include <vector>
    #include "base/basictypes.h"
    #include "base/commandlineflags.h"
    #include "foo/public/bar.h"
{% endhighlight %}


