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

##PL/SQL Reserved Words and Keywords
###IS / AS / DECLARE / BEGIN / EXCEPTION / END
The procedure body begins with the keyword IS (or AS) and ends with the keyword END followed by an optional procedure name.  
The procedure body has three parts: a declarative part, an executable part, and an optional exception-handling part.  
The declarative part contains local declarations, which are placed between the keywords IS and BEGIN. The keyword DECLARE, which introduces declarations in an anonymous PL/SQL block, is not used.  
The executable part contains statements, which are placed between the keywords BEGIN and EXCEPTION (or END).  
At least one statement must appear in the executable part of a procedure. The NULL statement meets this requirement. The exception-handling part contains exception handlers, which are placed between the keywords EXCEPTION and END.  

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

##SQL DISTINCT
In a table, a column may contain many duplicate values; and sometimes you only want to list the different (distinct) values.  
The DISTINCT keyword can be used to return only distinct (different) values.  
{% highlight sql %}
    SELECT DISTINCT column_name,column_name FROM table_name;
{% endhighlight %}

##SQL Alias
##SQL Distinct
##SQL Rank()

