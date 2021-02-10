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
<br>

## Normalization Process