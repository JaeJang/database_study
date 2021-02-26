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

<br>

### Second Normal Form, 2NF
When 2NF has completed, all columns in the table satisfy a fully functional dependency.

- Functional Dependency - When The value of X determines value Y, it is expressed as X -> Y, which is called Functional Dependency. For example, if we know a student ID, we can also know the name of the student, and in this case, the student ID is X and the name is Y. X is called the determiner and Y is the dependent. In other words, if X is changed, Y must be changed.
  
- when the value of X is multiple elements, {X1, X2} -> Y, it is called Fully Functional Dependency when both X1 and X2 determine the value of, and if only one of X1 and X2 determines the value of Y, it is called Partial Functional Dependency.

<br>

![2NF](/images/2nf_1.png)  
*2NF Not Satisfied*

{Model, Manufacturer} -> Model Full Name - Fully Functional Dependency

{Model, Manufacturer} -> Manufacturer Country - Model and Manufacturer Country have no relation, Manufacturer Country is dependent on Manufacturer only - Partial Functional Dependency
<br>

![2NF](/images/2nf_2.png)  
*2NF Satisfied*