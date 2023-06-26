# data-enrichment-week-13-core-assignment-2---Books

Books (Core)
 
## Assignment:
Consider the following "flat" file that a start-up has just started using for its first customers: Client's Original File. They quickly realized that saving this information in .csv format will not meet their needs as they grow. First, consider how you would design a relational database to meet their needs. Be sure to consider conventions of normalization and what information should be separated.

### Part 1: Design an ERD
Create an ERD (figure out how many tables to include and the relationships between them) to represent a database that tracks users and their favorite books. Here are some considerations as you design the database:

- For the purposes of this assignment, you may assume that each book only has one author (or that we are only tracking the primary author), but that the same author may have written multiple books.
- Each user should have a first name, last name, and email.
- We will be saving a list of each user's favorite books.
- Each book should have a title and an author. (The author's whole name can be one attribute)
- Note that each user will have multiple favorite books, and a book could certainly be the favorite of many users.
- Use the MySQL Workbench for designing the ERD.
- Hint: When you link two tables with a many to many relationship, MySQL Workbench will automatically create a joiner table for you! It will also automatically make the keys primary keys, which you will want to uncheck.


Insert the image of your ERD into the first markdown cell of your Jupyter Notebook. 

### Part 2: Create the database in Python

Continue working in Jupyter Notebook with the ERD image.

Rather than creating the database in MySQL workbench with forward engineering, we are going to develop our Python skills by creating the database in Python using PyMySQL that you practiced in the "MySQL with Python" lesson.

Note that working with MySQL via Python will be a required component of the belt exam, so getting comfortable with it now will help prepare you!

You will need to create a connection. This time, you may wish to call it "books"

>  //Create connection string using credentials following this format
>
>  //connection = "dialect+driver://username:password@host:port/database"
>
> connection = "mysql+pymysql://root:root@localhost/books"


Normally, you would have to take the time to transform the original .csv file from your client into the appropriate normalized tables. However, for this task, the transformation steps have been completed for you and you are provided a .csv for each table you will need. (Note that you will be learning and practicing efficient ways to make these transformations next week!)

The four files you will need to add as tables to your database are:

- users
- books
- authors
- favorites

Note that these files may not perfectly match the schema you designed. Notice how they are different, but move forward with these tables even if they are not exactly the same as your original plan. (Notably, we will not have created_at and updated_at attributes)

Once you have added these tables to your database, the database is now available to query from MySQL workbench OR in your Jupyter Notebook using SQLAlchemy!

### Testing the Database

After creating your 4 tables, you should run the "SHOW TABLES;" query in your notebook.

As a final step to this task, write a query at the end of your Jupyter Notebook to list the titles of all of John Doe's favorite books. 

### Part 3: Exporting the database and committing to GitHub

Now that you've created your database and verified it works, open MySQL Workbench and use the Export Database tool to save the .SQL file for your database in your assignment repository.
