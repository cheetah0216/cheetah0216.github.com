---
layout: post
title: "实例学PL/SQL"
category: language
tags: [sql]
description: |
  PL/SQL (Procedural Language/Structured Query Language) is Oracle Corporation's procedural extension language for SQL and the Oracle relational database. 
---
{% include JB/setup %}

[实例学PL/SQL](http://liufei.name/language/pl_sql_note.html)


##Get a table description
###Method 1
{% highlight sql %}
   select t1.column_name, 
   substr(data_type||'('||data_length||')', 0, 20) as data_type, 
   decode(nullable,'N','NOT NULL', '') as null_status, comments
   from all_tab_columns t1, all_col_comments t2
   where t1.table_name = t2.table_name
   and t1.column_name = t2.column_name
   and t1.table_name = 'TABLENAME'
   ORDER BY COLUMN_ID;
{% endhighlight %}

###Method 2
{% highlight sql %}
    SELECT *
    FROM user_col_comments
    WHERE table_name = 'TABLENAME';
{% endhighlight %}


##SQL Alias
##SQL Distinct
##SQL Rank()

