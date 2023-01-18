# SQL

# DDL - Data Definition Language

## CREATE TABLE

```sql
CREATE TABLE "customer" (
  "id" character(50) NOT NULL,
  "name" character(50) NOT NULL,
  "surname" character(50) NOT NULL,
  "birthdate" date NOT NULL,
  "created_on" timestamp NOT NULL
);
COMMENT ON COLUMN "customer"."id" IS 'primary key';
```

## ALTER TABLE

## DROP TABLE

## CREATE INDEX

## DROP INDEX


# DML - Data Manipulaiton Language

## SELECT
```sql
SELECT *
FROM
WHERE
GROUP BY
HAVING
ORDER BY
```

## INSERT INTO

``` sql
INSERT INTO customer (id, name, surname, birthdate, created_on)
VALUES
(1, 'Pahlke', 'Lucas', '1998-05-01', NOW())
```

## UPDATE
```sql

```

## DELETE FROM/TRUNCATE TABLE
```sql

```

# DCL - Data Control Language
