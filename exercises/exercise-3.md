# Use Subqueries to reduce round-trips

### Goal
- Implement a scenario using subqueries that needs to feed a query result into another result.

### Problem Statement
- Find the list of books from the *BOOK* table whose number of pages is less than the 50% of pages in a book with maximum paged.
- Field Names: 
-- *book_id* - a primary key,
-- *title* - a mandatory long text value, 
-- *no_of_pages* - a mandatory integer

#### Some pre-work

> **Create the above described Table**

> **Create an index on the book_id field**

***Note*** - The primary key field is an INDEX in its own

> **Populate Data in BOOK Table**

***Hint***
- Use the following script to populate sample data
```
INSERT INTO BOOK
    (title, no_of_pages)
VALUES
    ('B10', 10),
    ('B11', 20),
    ('B21', 25),
    ('B32', 20),
    ('B43', 10),
    ('B54', 50);
```
#### The Two-step solution

> **Create a query to find the highest value of no_of_pages**

***Hint:*** 
- Use *MAX* function.
- In this case, it is 50. Please confirm you get that above
- Need to use the above value in the query below

> **Create another query with the following condition**
- *no_of_pages* is less than 50% (or half) of above found highest value.

***Hint:***
- It should print all (actually, four) rows where no_of_pages is less than 50% of 50 i.e., 25

#### The Subquery based solution
> Merge above created queries into one by using the first query as a subquery in the condition of the second query.

***Hint:***
- The final query should look something like below.
```
SELECT ... FROM book 
	WHERE no_of_pages < 0.5* (...the first query...);
```

> **It should also print the same rows as above.

