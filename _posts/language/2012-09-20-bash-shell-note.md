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

##bash 实例
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

###数组
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

##字符串操作
##数组操作


