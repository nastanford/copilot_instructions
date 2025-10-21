---
applyTo: "**/*.sql"
---

# SQL Server Specific Guidelines

## SQL Server Requirements
- Use only **Microsoft SQL Server**
- Every table must have an `id` column as the primary key
- The `id` column must be set to autoincrement using `IDENTITY(1,1)` syntax

## SQL Server Best Practices
- Use `NVARCHAR` for Unicode text fields
- Use proper data types for optimal performance (`INT`, `BIGINT`, `DECIMAL`, etc.)
- Include proper indexes for frequently queried columns
- Use stored procedures for complex business logic when appropriate
- Always use parameterized queries to prevent SQL injection

## SQL Server Authorization
- When needing to create or update a database table, I have to send to the database team so always provide a MS SQL code for me to send to them.
