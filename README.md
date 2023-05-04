Download Link: https://assignmentchef.com/product/solved-csci317-project-database-performance-tuning
<br>
This project includes the tasks in improving performance of database applications.

<h1>Prologue</h1>

In this subject we use Oracle 19c database server running under Oracle Linux 7.4 operating system on a virtual machine hosted by VirtualBox. To start Oracle database server you have to start VirtualBox first. To start VirtualBox navigate through the following menus:  Start-&gt;All Programs-&gt;Oracle VM VirtualBox-&gt;Oracle VM VirtualBox.

It is explained in Cookbook for CSIT115 Recipe 1.1, Step 1 “How to start VirtualBox ?”

(https://www.uow.edu.au/~jrg/115/COOKBOOK/e1-1-frame.html) how to start VirtualBox.




When VirtualBox is started, import an appliance included in a file OracleLinux7.464bits-Oracle19c-22-JAN-2020.ova and located on a drive VMs(E:) in a folder Virtual MachinesCSCI317-Janusz.




When ready, power on a virtual machine OracleLinux7.4-64bits-Oracle19c22-JAN-2020.




A password to a Linux user ORACLE is oracle and a password to Oracle users SYSTEM and SYS (database administrators) is also oracle. Generally, whenever you are asked about a password then it is always oracle, unless you change it.




When logged as a Linux user, you can access Oracle database server either through a

command line interface (CLI) SQLcl or through Graphical User Interface (GUI) SQL Developer.




You can find in Cookbook, Recipe 1, How to access Oracle 19c database server, how to use SQL Developer, how to use basic SQL and SQLcl, and how to create a sample database ? more information on how to use SQLcl and SQL Developer.




It is strongly recommended to drop the relational tables of TPC-HR benchmark database and to drop all tablespaces created in the previous Assignment. Then, recreate TPC-HR benchmark database in a way explained in Assignment 1, task 1. The other option is to import a new copy of virtual machine with Oracle 19c and again repeat Assignment 1, task 1.

<u>                                                                                                                                                 </u>

<strong>             </strong>

<h1>Preface</h1>

A database administrator identified for the workload optimizations the following templates of five frequent data processing tasks:




task1.sql sample SELECT statement used for power testing in TPC-HR benchmark task2.sql sample SELECT statement used for power testing in TPC-HR benchmark

task3.sql  SELECT statement using a stored function that never ends

task4.sql JDBC application task5.sql JDBC application




Note, that a symbol … included in the implementation of the tasks listed above represents a text or numeric constant that should be used when processing the tasks. Assume, the frequencies of processing are more or less the same for each task.




<h1>Objective</h1>

<strong>An objective of this project is to improve performance of all five data processing task listed above. </strong>

<strong> </strong>

<h1>Constraints</h1>

<ul>

 <li>These days financial situation is pretty hopeless and we have no money to purchase a better hardware and/or to invest into a software license of more powerful database system.</li>

</ul>




<ul>

 <li>It is possible to invest no more than 100Mbytes of transient memory into the expansion of SGA and data buffer caches. All extension of SGA and data buffer caches must be documented in the final submission.</li>

</ul>




<ul>

 <li>It is also possible to invest no more than 300Mbytes of persistent storage, i.e. to double the size of TPC-HR benchmark database. All investments into persistent storage like for example additional indexes or materialized views must documented in the final submission.</li>

</ul>




<ul>

 <li>You are allowed to use the following of optimization of data processing techniques that have been discussed and practiced in the subject:

  <ul>

   <li>data modeling techniques,</li>

   <li>persistent storage techniques,</li>

   <li>SQL programming techniques,</li>

   <li>Advanced/specialized SQL programming techniques,       – SQL+host language programming techniques,             – database server tuning techniques.</li>

  </ul></li>

</ul>




You can find an overview of the techniques listed above in a presentation 05 Principles of Database Performance Tuning.

<strong> </strong>

<h1>Deliverables</h1>

Every implemented improvement of one or more given data processing tasks must be described in a separate document that contains:




<ul>

 <li>a short description of an improvement,</li>

 <li>information about the benefits from an improvement,</li>

 <li>information about the costs of an improvement, i.e. documented investments into transient and persistent storage and</li>

 <li>a report from implementation of an improvement.</li>

</ul>




For example, if you propose to denormalize a relational table then the benefits from denormalization can be reported as SQL processing plans with the cost estimations performed before and after an improvement, the costs can be measured as the total amount of additional persistent storage required to implement denormalization, and a report from implementation is a report from processing of SQL script that denormalizes a relational table.




The improvements in performance can be demonstrated with SQL processing plans obtained from EXPLAIN PLAN statement, application of time command for JDBC tasks and application of SQL scripts utlbstat and utlestat.




It is <strong>not recommended</strong> to use <strong>AWR reports</strong> and <strong>tracing</strong> due to the complexity of the reports. The reports from processing of SQL scripts utlbstat and utlestat must be limited to information that is only relevant to the improvements achieved. Complete reports will be ignored.




It is expected that each one of the data processing tasks listed above will be improved in at least one way. However, more improvements are mostly welcomed. The complete reports from the implemented improvements must be saved in the pdf files report1.pdf, report2.pdf, report3.pdf, report4.pdf, and report5.pdf.