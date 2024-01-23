# SQLQuery

## Data Defination Language 
Used for defining the few examples are `CREATE`, `DROP`, `ALTER`, `TRUNCATE`, `RENAME`

`CREATE` - Used for creating tables.
```SQL
CREATE TABLE table_name (
    column1 data_type(size),
    column2 data_type(size),
    ...
);
```

`DROP` - Used to delete an entier table
```SQL
DROP TABLE table_name
```

`ALTER` - Used for adding new columns, updating data types and deleting colummns.  
```SQL
ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name datatype(size);
```

`TRUNCATE` - Delete all data inside the table
```SQL
TRUNCATE TABLE table_name;
```

`RENAME` - Used for changing name of the existing column with other name.
```SQL
RENAME TABLE old_table_name TO new_table_name;
```

## Data Manipulation Language (DML)
DML Statements are used for performing queries on the data present in the database.
Examples are `INSERT`, `UPDATE`, `DELETE`

`INSERT` Adding data to any table
```SQL
INSERT INTO table_name 
    ( column1, column2, column3, ... )  
VALUES 
    ( value1, value2, value3, ... ) 
```

`UPDATE` - Update existing data based on `WHERE` condition, If `WHERE` is not passed then all the data might get effected.
```SQL
UPDATE 
    table_name
SET 
    column1 = value1, column2 = value2, ...
WHERE 
    condition;
```

`DELETE` - Removes data permenatly from the databases based on the condition present in the `WHERE` clause, If that is not present then entire data present in the table will be deleted.
```SQL
DELETE FROM table_name WHERE condition;
```

## Data Query Langauge (DQL)
DQL is used to perform operations on the data to fetch data, Mainly `SELECT` is used for fetching Based on the conditions passed on `WHERE` clause and ordering data from `order by` clause and using various other parameters.
```SQL
SELECT 
    column1, column2, ... 
FROM 
    table_name
WHERE 
    condition...
```

* `DISTINCT` - To get only unique data
    ```SQL
        SELECT 
            DISTINCT column1, column2, ...
        FROM 
            table_name 
    ```
* `ORDER BY` - To order perticular data
    ```SQL
        SELECT 
            column1, column2, ...
        FROM 
            table_name
        ORDER BY 
            column ASC|DESC;
    ```
* `GROUP BY and HAVING` - To Group based on condition
    ```SQL
        SELECT 
            column1, column2
        FROM 
            table_name
        GROUP BY 
            column1, column2;
    ```
    ```SQL
        SELECT 
            column1, column2
        FROM 
            table_name
        GROUP BY 
            column1, column2
        HAVING 
            condition value;
    ```
* `JOIN` - To join multiple tables we are using join operator
     ```SQL
        SELECT 
            table1.column1, table2.column2...
        FROM table1
        (INNER | LEFT | RIGHT | FULL) JOIN table2
            ON table1.matching_column = table2.matching_column;
    ``` 
    By `USING`
    ```SQL
        SELECT 
            table1.column1, table2.column2...
        FROM table1
        (INNER | LEFT | RIGHT | FULL) JOIN table2
            USING matching_column;
    ```
    * `INNER JOIN` - Gives record matching condititions from both conditions
    * `LEFT JOIN` or `LEFT OUTER JOIN` - Gives all record from table1 and matching conditions from table2
    * `RIGHT JOIN` or `RIGHT OUTER JOIN`- Gives all record from table2 and matching conditions from table1
    * `FULL JOIN`or `FULL OUTER JOIN` - Returns all the record from the table1 and table2
    * `SELF JOIN` - To Get record of one table using values of same table
    ```SQL
        SELECT 
            a.column_name, b.column_name...
        FROM 
            table_name AS a, 
            table_name AS b
        WHERE 
            condition;
    ```
    * `CARTESIAN JOIN` - Same as above without where condition
    ```SQL
        SELECT 
            a.column_name, b.column_name...
        FROM 
            table_name AS a, 
            table_name AS b
    ```