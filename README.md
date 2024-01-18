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

`ALTER` - Used for adding new columns, updating data types and deleting colummns.  
```SQL
ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name datatype(size);
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