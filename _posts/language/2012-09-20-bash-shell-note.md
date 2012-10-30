---
layout: post
title: "Bash Shell学习总结"
category: language 
tags: [shell]
description: |
  Bash Shell 备忘. 
---
{% include JB/setup %}

[Bash shell](http://en.wikipedia.org/wiki/Bash_(Unix_shell)).

##bash技巧
###得到PID("$$")
{% highlight bash %}
    TEMPFLIE = tmp.$$
    echo "TEMPFILE"
{% endhighlight %}

###"&&","||"技巧
{% highlight bash %}
    #--> [ $# -ne 2 ] && echo "swap: 2 arguments needed" && return 1
{% endhighlight %}

###bash算术运算('let')
{% highlight bash %}
    num1=1
    num2=2
    result1=0
    result2=0
    let result1=num1+num2
    result2=num1+num2
    echo $result1
    echo $result2
{% endhighlight %}

##bash实例-字符串操作
###得到字符串长度
{% highlight bash %}
    RPMName=$1
    Length=${#RPMName}
{% endhighlight %}

###获取范围内字符串
{% highlight bash %}
    TEMP=${RPMName:0:($Length-4)}
{% endhighlight %}

###字符串连接
{% highlight bash %}
    DEBName=$TEMP".deb"
{% endhighlight %}

###得到文件名
{% highlight bash %}
    test="/home/usr/bash/test.c"
    ${test##^/} (将^替换)^-->*

    result:
    test.c
{% endhighlight %}

###得到目录地址
{% highlight bash %}
   test="/home/usr/bash/test.c"
   ${test%/^} (将^替换)^-->*

   result:
   /home/usr/bash
{% endhighlight %}

###得到文件类型/后缀名
{% highlight bash %}
    filename="/home/test/temp.cpp"
    echo ${filename##^.} (将^替换)^-->*
    
    result: 
    cpp
{% endhighlight %}

###bash 前后缀操作
{% highlight bash %}
    filename="/home/test/temp.foo.tar.gzip"
    echo ${filename##^.} 
    echo ${filename#^.} 
    echo ${filename%%.^}
    echo ${filename%.^}
    (将^替换)^-->*
{% endhighlight %}

###遍历给定目录下的所有文件(不支持递归)
{% highlight bash %}
    readpath="/home/liufei/test"  
    for file in $readpath/*  
    do  
       echo "$file"  
    done  
{% endhighlight %}

##bash实例-awk，cut，sed，grep
###得到最新文件名
{% highlight bash %}
    #ls -lrt 时间从从旧到新排列
    #awk -F: '{print'}| tail-n1 得到最后一行
    #awk '{print $9}' 得到最新的一行的第9个字段（即为文件名），其中字段以空格为分割符
    DEBName=`ls -lrt |awk -F: '{print '}|tail -n1 | awk '{print $9}'`
{% endhighlight %}

###得到ip地址
{% highlight bash %}
    #grep -v '***' 去掉包含***的项
    #cut -d: -f2 指定以“：”为分割符（-d:） 
    #-f2（选取：：1，2两个冒号之间的内容） -f3（选取：：2，3两个冒号之间的内容）以此类推
    #awk '{ print $1}' 得到第一个字段
    ifconfig | grep 'inet 地址:'| grep -v '127.0.0.1' | cut -d: -f2 | awk '{ print $1}'
{% endhighlight %}

###读取文件的某一行
{% highlight bash %}
    #-n 取消默认输出
    #1p,输出第一行
    sed -n `1p` ~/file
{% endhighlight %}

###大小写替换
{% highlight bash %}
    echo "ABcd" | tr A-Z a-z
{% endhighlight %}

##bash实例-数组,for循环
###for循环
{% highlight bash %}
    names=( Jennifer Tonya Anna Sadie )

    for name in ${names[@]} do
    echo $name
    # other stuff on $name
    done

    for (( i = 0 ; i < ${#names[@]} ; i++ )) do
    echo ${names[$i]}
    # yadda yadda
    done
{% endhighlight %}

###for循环(positional parameters)
{% highlight bash %}
    $ cat for1.sh
    i=1
    for day
    do
     echo "Weekday $((i++)) : $day"
    done

    $ ./for1.sh Mon Tue Wed Thu Fri
    Weekday 1 : Mon
    Weekday 2 : Tue
    Weekday 3 : Wed
    Weekday 4 : Thu
    Weekday 5 : Fri
{% endhighlight %}

###bash中将字符串split成数组
{% highlight bash %}
    str="hello,world,i,like,you,babalala" 
    arr=(${str//,/ }) 

    for i in ${arr[@]} 
    do 
    echo $i 
    done 
    "将str按照','切分成一个数组，并遍历之。
    "当然，这里分隔符可以是一个子串。
{% endhighlight %}

##bash Positional Parameters
###Set/Unset Bash Positional Parameters
{% highlight bash %}
    # From command line
    echo -e "Basename=$0"
    echo -e  "\$1=$1"
    echo -e "\$2=$2"
    echo -e "\$3=$3"

   # From Set builtin
    set First Second Third
    echo -e  "\$1=$1"
    echo -e "\$2=$2"
    echo -e "\$3=$3"

    # Store positional parameters with -(hyphen)
    set - -f -s -t
    echo -e  "\$1=$1"
    echo -e "\$2=$2"
    echo -e "\$3=$3"

    # Unset positional parameter
    set --
    echo -e  "\$1=$1"
    echo -e "\$2=$2"
    echo -e "\$3=$3"
{% endhighlight %}

##bash变量
###bash bulid-in 变量
{% highlight bash %}
    $0           当前shell程序的名字
    $1 ~ $9      命令行上的第一到第九个参数
    $#           命令行上的参数个数
    $*           命令行上的所有参数
    $@           分别用双引号引用命令行上的所有参数
    $$           当前进程的进程标识号(PID)
    $?           上一条命令的退出状态
    $!           最后一个后台进程的进程标识号

    ./test.sh -f config.conf -v --prefix=/home
    # $0 ： ./test.sh,即命令本身，相当于C/C++中的argv[0]
    # $1 ： -f,第一个参数.
    # $2 ： config.conf
    # $3, $4 ... ：类推。
    # $# :参数的个数，不包括命令本身，上例中$#为4.
    # $@ ：参数本身的列表，也不包括命令本身，如上例为 -f config.conf -v --prefix=/home
    # $* ：和$@相同，但"$*" 和 "$@"(加引号)并不同，"$*"将所有的参数解释成一个字符串，而"$@"是一个参数数组。
{% endhighlight %}

###bash 输入变量
{% highlight bash %}
    read -p "Enter your name:" name
    echo "Hello $name, Welcome to my blog!"
{% endhighlight %}

