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

#PL/SQL Concepts
##PL/SQL in CLient/Server Architecture
PL/SQL is not a stand-alone programming language.PL/SQL is a part of the Oracle RDBMS,and ot can reside in two environments,the client and the server.  
The SQL ststement processor is always located on the Oracle server.  
**When the PL/SQL engine is located on the server**  

**When the PL/SQL engine is located on the client** 
As it is in Oracle Developer Tools, the PL/SQL processing is done on the client side.  
(1) All SQL statements that are embedded within the PL/SQL block are sent to the Oracle server for further processing.  
(2) When the PL/SQL block contains no SQL statements, the entire block is executed on the client side.  

**PL/SQL in client/server architecture**
Compares two applications. The first application uses four independent SQL state-ments that generate eight trips on the network. The second application combines SQL state-ments into a single PL/SQL block. This PL/SQL block is then sent to the PL/SQL engine. The engine sends SQL statements to the SQL statement processor and checks the syntax of PL/SQL statements. As you can see, only two trips are generated on the network.  
