---
layout: post
title: "Google C++ Style Guide"
category: language 
tags: [C++]
description: |
  Google C++ Style Guide 学习笔记. 
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

