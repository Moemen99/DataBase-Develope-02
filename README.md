# SQL Basics: An Introduction

## SQL Data Types

When creating tables in SQL, you need to specify the data type for each column. This defines what kind of data can be stored in that column. Let's look at some common data types, starting with numeric data types.

### Numeric Data Types

1. **BIT**
   - Stores either 0 or 1
   - Equivalent to a boolean value
   - Example use: flags, true/false conditions

2. **TINYINT**
   - 1 byte (8 bits)
   - Range: 
     - Signed: -128 to 127
     - Unsigned: 0 to 255
   - Example use: small integer values, age

3. **SMALLINT**
   - 2 bytes (16 bits)
   - Range:
     - Signed: -32,768 to 32,767
     - Unsigned: 0 to 65,535
   - Example use: larger integer values, year

4. **INT**
   - 4 bytes
   - Most commonly used integer type
   - Range: -2,147,483,648 to 2,147,483,647
   - Example use: IDs, counts, standard integer values

5. **BIGINT**
   - 8 bytes
   - Used for very large integer numbers
   - Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
   - Example use: large IDs, big counts, statistical data

### Usage Notes

- Choose the appropriate data type based on the expected range of values to optimize storage and performance.
- Using the smallest data type that can accommodate your data can save storage space and improve query performance.
- UNSIGNED can be used with these types in some database systems to allow only non-negative values and effectively double the positive range.

### Example

```sql
CREATE TABLE Products (
    ProductID INT,
    InStock BIT,
    Quantity SMALLINT,
    Price BIGINT
);
```

In this example:
- `ProductID` uses INT, suitable for a standard ID field.
- `InStock` uses BIT, perfect for a yes/no (1/0) flag.
- `Quantity` uses SMALLINT, assuming we don't need to store very large quantities.
- `Price` uses BIGINT, allowing for very high precision in pricing (e.g., if storing price in cents).

## Next Steps

- Learn about other data types (string, date/time, binary, etc.)
- Understand how to choose the right data type for your needs
- Practice creating tables with various data types
- Explore more advanced SQL features and best practices for database design

---


### Fraction Data Types

1. **SMALLMONEY**
   - 4 bytes before the decimal point, 4 digits after
   - Used for monetary or currency values (smaller range)

2. **MONEY**
   - 8 bytes before the decimal point, 4 digits after
   - Used for monetary or currency values (larger range)

3. **REAL**
   - 4 bytes
   - Approximate numeric data from -3.40E+38 to 3.40E+38
   - 7 digits precision

4. **FLOAT**
   - 8 bytes
   - Approximate numeric data from -1.79E+308 to 1.79E+308
   - 15 digits precision

5. **DECIMAL (or NUMERIC)**
   - Example: DECIMAL(5,2)
   - Exact numeric data
   - First parameter is total number of digits, second is number of digits after the decimal point
   - Most commonly used for precise fractional numbers
   - Example: DECIMAL(5,2) allows 124.22, but not 18.1, 12.2212, or 2.1234

### String Data Types

1. **CHAR(n)**
   - Fixed-length character string
   - Allocates all n characters in memory
   - Example: CHAR(10)

2. **VARCHAR(n)**
   - Variable-length character string
   - Allocates only the used characters (up to n) in memory
   - Example: VARCHAR(10)

3. **NCHAR(n) and NVARCHAR(n)**
   - Unicode character strings
   - Used for non-English language data
   - NVARCHAR(MAX) for large Unicode strings up to 2GB

### Date and Time Data Types

1. **DATE**
   - Format: MM/dd/yyyy (may vary based on server settings)

2. **TIME**
   - Format: hh:mm:ss.nnnnnnn
   - Default precision: TIME(3) - milliseconds
   - Can specify precision, e.g., TIME(5) for microsecond precision

3. **SMALLDATETIME**
   - Format: MM/dd/yyyy hh:mm:00
   - No seconds precision

4. **DATETIME**
   - Format: MM/dd/yyyy hh:mm:ss.123
   - 3-digit millisecond precision

5. **DATETIME2(n)**
   - Format: MM/dd/yyyy hh:mm:ss.nnnnnnn
   - Can specify precision (n)
   - Example: DATETIME2(4) gives MM/dd/yyyy hh:mm:ss.1234

6. **DATETIMEOFFSET**
   - Includes time zone awareness
   - Example: 11/23/2020 10:30 +02:00

### Binary Data Types

1. **BINARY**
   - Fixed-length binary data

2. **VARBINARY**
   - Variable-length binary data

3. **IMAGE**
   - Variable-length binary data (deprecated, use VARBINARY(MAX) instead)

Note: Storing large files (like videos) directly in the database is generally not recommended due to performance issues. Alternative approaches for file storage should be considered.

### Other Specialized Data Types

1. **XML**
   - Stores XML formatted data

2. **SQL_VARIANT**
   - Stores values of various SQL Server-supported data types

## Usage Notes

- Choose the appropriate data type based on the expected data and usage patterns.
- Using the correct data type can improve query performance and reduce storage requirements.
- For storing large files or BLOBs (Binary Large Objects), consider using file system storage and storing the file path in the database instead of the file itself.
- Always consult your specific database system's documentation, as data type implementations can vary between different database management systems.

## Next Steps

- Practice creating tables with various data types
- Learn about data type conversion and casting
- Explore best practices for database schema design
- Understand indexing and its relation to data types

---

**Note**: While these data types are common in many SQL databases, the exact behavior and availability might vary between different database management systems. Always consult the documentation for your specific DBMS for the most accurate information.




