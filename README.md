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

**Note**: While these numeric data types are common in many SQL databases, the exact ranges and behaviors might vary slightly between different database management systems. Always consult the documentation for your specific DBMS for the most accurate information.
