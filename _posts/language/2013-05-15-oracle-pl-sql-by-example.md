---
layout: post
title: "Oracle PL/SQL By Example"
category: language
tags: [language]
description: |
  Oracle PL/SQL By Example 
---
{% include JB/setup %}

[Oracle PL/SQL By Example](http://liufei.name/language/oracle-pl-sql-by-example.html)

#1. PL/SQL Concepts
##1.1 PL/SQL in CLient/Server Architecture
**PL/SQL is not a stand-alone programming language.PL/SQL is a part of the Oracle RDBMS,and ot can reside in two environments,the client and the server.**   
The SQL ststement processor is always located on the Oracle server.  

**When the PL/SQL engine is located on the server**  
![1-1](/res/images/language/oracle-pl-sql-by-example-1-1)  

**When the PL/SQL engine is located on the client**   
As it is in Oracle Developer Tools, the PL/SQL processing is done on the client side.  
<li>All SQL statements that are embedded within the PL/SQL block are sent to the Oracle server for further processing.</li>
<li>When the PL/SQL block contains no SQL statements, the entire block is executed on the client side.</li>
  
**PL/SQL in client/server architecture**
![1-2](/res/images/language/oracle-pl-sql-by-example-1-2)  
Compares two applications. The first application uses four independent SQL state-ments that generate eight trips on the network. The second application combines SQL state-ments into a single PL/SQL block. This PL/SQL block is then sent to the PL/SQL engine. The engine sends SQL statements to the SQL statement processor and checks the syntax of PL/SQL statements. As you can see, only two trips are generated on the network.  

##1.2 PL/SQL Block Structure
All PL/SQL programs are combined into blocks.   

**PL/SQL blocks can be divided into two groups: named and anonymous.**  
Named PL/SQL blocks are used when creating subroutines. These subroutines are procedures, functions, and packages. The subroutines then can be stored in the database and referenced by their names later. In addition, subroutines such as procedures and functions can be defined within the anonymous PL/SQL block. These subroutines exist as long as this block executes and cannot be referencedoutside the block.  

**PL/SQL blocks contain three sections: the declaration section, the executable section, and the exception-handling section.**
The executable section is the only mandatory section of the block.The declaration and exception-handling sections are optional.   
As a result,a PL/SQL block has the following structure:  
{% highlight sql %}
DECLARE
    Declaration statements
BEGIN
    Executable statements
EXXEPTION
    Exception-handling statements
END;
{% endhighlight %}
The executable section of any PL/SQL block always begins with the keyword BEGIN and ends with
the keyword END. Example:  
{% highlight sql %}
DECLARE   v_first_name VARCHAR2(35);   v_last_name VARCHAR2(35);BEGIN   SELECT first_name, last_name     INTO v_first_name, v_last_name     FROM student    WHERE student_id = 123;      DBMS_OUTPUT.PUT_LINE ('Student name: '||v_first_name||' '||v_last_name);EXCEPTION   WHEN NO_DATA_FOUND THEN      DBMS_OUTPUT.PUT_LINE ('There is no student with '||'student id 123');END;
{% endhighlight %}



