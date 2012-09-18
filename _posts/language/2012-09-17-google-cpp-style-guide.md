---
layout: post
title: "Google C++ Style Guide"
category: language 
tags: [C++]
description: |
  [Google C++ Style Guide](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml) ѧϰ�ʼ�. 
---
{% include JB/setup %}

##ͷ�ļ�  
**ÿһ�� `.cc` �ļ�����һ����Ӧ�� `.h` �ļ�.Ҳ��һЩ��������, �絥Ԫ���Դ����ֻ���� `main()` ������ `.cc` �ļ�.**  

###define ����
**������ʽ����: `<PROJECT>_<PATH>_<FILE>_H_`.**  
����, ��Ŀ `foo` �е�ͷ�ļ� `foo/src/bar/baz.h` �ɰ����·�ʽ����:  
{% highlight cpp %}  
    #ifndef FOO_BAR_BAZ_H_  
    #define FOO_BAR_BAZ_H_  
    ��  
    #endif // FOO_BAR_BAZ_H_  
{% endhighlight %}

###ͷ�ļ�����
**����ʹ��ǰ�������ĵط���Ҫʹ��`#include`**  
һ��ͷ�ļ����޸ģ�������ͷ�ļ����������붼��Ҫ�����±���.�ر��ǵ�ͷ�ļ��ְ�������ͷ�ļ���ʱ��.  
**ʲôʱ��ʹ��ǰ��������**  
���ͷ�ļ���ʹ����`Foo`,���ǲ�����Ҫ������`Foo`������,���ǿ�����ǰ������`class Foo`����`#include`,����һ�¼������.   
- ���Խ����ݳ�Ա��������Ϊ`Foo&` �� `Foo*`.    
- ���Խ������Ĳ���/����ֵ����(���Ƕ���)Ϊ`Foo`����.(��һ��������:���`Foo`����`Foo&�Ĳ�����`non-explicit`, `one argument construcor`,���ʱ����Ҫ������
    ����ȥ֧���Զ�����ת��).  
- ���Խ���̬���ݳ�Ա��������Ϊ`Foo`.  

###inline����  
**ֻ�е�����ֻ��10����������ʱ�Ž��䶨��Ϊ��������.**




