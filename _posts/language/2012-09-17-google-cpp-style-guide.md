---
layout: post
title: "Google C++ Style Guide"
category: language 
tags: [C++]
description: |
  Google C++ Style Guide 学习笔记. 
---
{% include JB/setup %}

##头文件  
每一个 ``.cc`` 文件都有一个对应的 ``.h`` 文件.也有一些常见例外, 如单元测试代码和只包含 ``main()`` 函数的 ``.cc`` 文件.  

###define 保护
命名格式当是: ``<PROJECT>_<PATH>_<FILE>_H_``.  
例如, 项目 ``foo`` 中的头文件 ``foo/src/bar/baz.h`` 可按如下方式保护:  
{% highlight C++ %}  
    #ifndef FOO_BAR_BAZ_H_  
    #define FOO_BAR_BAZ_H_  
    …  
    #endif // FOO_BAR_BAZ_H_  
{% endhighlight %}

{% highlight C++ %}  
    #include <iostream>
    using namespace std;
    
    int main()
    {
      cout << "HelloWord";
      return 0;
    }
{% endhighlight %}

<code>
    #include <iostream>
    using namespace std;
    
    int main()
    {
      cout << "HelloWord";
      return 0;
    }
</code>
