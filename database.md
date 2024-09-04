### What is self join. Write an example?
A self join is a type of join in SQL that allows you to combine and compare rows within the same table. It is useful when you need to relate records in a table to other records in the same table. This is typically done using table aliases to differentiate between the two instances of the table.

```database
SELECT   
    e1.name AS Employee,  
    e2.name AS Manager  
FROM   
    employees e1  
LEFT JOIN   
    employees e2 ON e1.manager_id = e2.employee_id; 
```
