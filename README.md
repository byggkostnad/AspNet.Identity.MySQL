# AspNet.Identity.MySQL
Sample usage of MySQL together with EF identity

## Setup
 
Install MySql.Data.Entity in your project:

```PM> Install-Package MySql.Data.Entity```

Add migration configuration:

```PM> Enable-Migrations```

In the file ```Migrations/Configuration.cs```

Add the following lines in the constructor:

```
            AutomaticMigrationsEnabled = true;
            SetSqlGenerator("MySql.Data.MySqlClient", new MySql.Data.Entity.MySqlMigrationSqlGenerator());
```

Change the DefaultConnection to something like:

```
    <add name="DefaultConnection" 
         connectionString="Server=127.0.0.1;Uid=root;Pwd=test;Database=test;"
         providerName="MySql.Data.MySqlClient" />
```

```PM> Update-Database```

Your database should now contain aspnetroles, aspnetusers, et.c.