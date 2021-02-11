# Normalization

Database Normalization is the process or structuring a database, in accordance with a series of so-called normal forms in order to reduce redundancy and improve data integrity.
<br>

## Objectives of Normalization
- Remove unnecessary data and reude redundancy
- Minimize re-structuring when scaling up
- To support query in many different perspective
- To simplify the enforcement of integrity constraints
- To prevent many kinds of Anomaly
<br>

## Target of Normalization
It is better to be normalized for OLTP(Online Transaction Processing) Database, such as ecommerce, as there are lots of CRUD, but OLAP(Online Analytical Processing) Database, such as Analysis or Reoprt, is beter te be *denormalized* for calculation speed.  


  > Denormalization is to literally reverse normalization to acheive performance improvement and simplification of development and management. Generally, when there are many join statements and when it is deemed to be important to handle inquiries, such as frequently processing large numbers of scope, denormalization is partial proceeded

<br>

## Normalization Process

There are 1NF ~ 6NF, but in practice, it usually goes through 1NF ~ 3NF normalization process
<br>

### First Normal Form, 1NF
3 conditions to statisfy 1NF

1. All domains that belong to a Relation have only atomic values
2.  Repeating group is not present in all attribute
3. The primary key should be able to uniquely identify each set of relevant data

  ![1NF Violation](/images/1nf_violation_1.png)  
  *Violate the first condition - one column has two numbers*
<br>
<br>

  ![1NF Violation](/images/1nf_violation_2.png)  
  *Violate the second condition - repeating Telephone Number group*
<br>
<br>

  ![1NF](/images/1nf_1.png)  
  *Desing that comply with 1NF*
  *We can see on the above relation that the ID is no longer a uniquely identifiable key. Therefore, it is better to divide the tale as below to meet the third conditions*
<br>
<br>

  ![1NF](/images/1nf_1.png)  
  *One-to-many relationship between Customer Name and Customer Telephone Number*