# Index

## 1. What is Index?
Some kind of address system that has location information of data. It's is useful tool to optimize performance when it comes to search (SELECT)  


## 2. Why Index is needed

  ![index](/images/index_example.gif)
*https://help.sap.com/SAPHelp_46C/helpdata/ES/cf/21eb20446011d189700000e8322d00/frameset.htm*

Let's say that we are looking for **LCY** in the **AIRPORT** column from the **SCOUNTER** table. Since Database doesn' know what is the last row that has value **LCY**, it needs to do the full-scan and returns a result. It is logically find. But if there are multi-million rows in a table and if the search function is executed frequently, it affects the performance.

Using **Index**, we can improve the performance dramatically when there is a SELECT query by creating Index Table for columns searched frequently and returning results based on the index table.

## 3. How it works
- SELECT query
- Find a value included in where clause from Index Table
- Get table_id[PK] of the value
- Retrieve data from the original table with table_id[PK] from the last step

## 4. About Index

- Index Table  
Index stores a value and use it with a table. Indiscreet index generation can cause performance issue in that the one new table is created that depends on another table.

- Sorting
Index table is sorted by default because it uses binary tree search. With that being said, if insertion, deletion or update occurs frequently in the table referenced by the index table, the index table can cause overall performance degradation as it is inserted, deleted and updated while sorting the data.

In a nut shell, the index is a search-optimized feature, we need to carefully consider whether to use the index depending on the business logic or table usage, where insertion, deletion, and update happen frequently.


## 5. Etc  

  ### Index Hint
  In some cases, query performance is slow using other indices rather than the desired one. In that case, using Index Hints forces to execute queries with the index assigned.  
  ```
  SELECT * FROM table1 USE INDEX (col1_index,col2_index)
  WHERE col1=1 AND col2=2 AND col3=3;

  SELECT * FROM table1 IGNORE INDEX (col3_index)
  WHERE col1=1 AND col2=2 AND col3=3;
  ```

  

