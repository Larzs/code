# SQL

# Spēja ievietot vērtības identity (primary) laukos

```
SET IDENTITY_INSERT [serveris1].[db].[shēma].[tabula] ON 

INSERT INTO [serveris1].[db].[shēma].[tabula]
SELECT * FROM [serveris2].[db].[shēma].[tabula]

SET IDENTITY_INSERT [serveris1].[db].[shēma].[tabula] OFF
```

## Mariadb

Kāda versija?
```
select @@version as version;
```

Importēt no komandrindas
```
"C:\xampp\mysql\bin\mysql.exe" -hlocalhost -uroot database_name < db_02022022.sql
```
