# Practical-08.md

## Problem Statement
Write a MVC program to perform CRUD operations on the category table using the Code First Approach of the Entity Framework.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the Package Manager Console by going to Tools -> NuGet Package Manager -> Package Manager Console.
3. Run the following command in the Package Manager Console to install the Entity Framework:

```
Install-Package EntityFramework
```

4. Open the Web.config file located in the root folder of the project.
5. Add the following connection string to the `<connectionStrings>` section:

```xml
<add name="DefaultConnection" connectionString="Data Source=(LocalDb)\MSSQLLocalDB;Initial Catalog=YourDatabaseName;Integrated Security=True" providerName="System.Data.SqlClient" />
```

6. Create a new class called `Category.cs` in the Models folder with the following code:

```csharp
public class Category
{
    public int Id { get; set; }
    public string Name { get; set; }
}
```

7. Open the ApplicationDbContext.cs file located in the Models folder.
8. Add the following code to the ApplicationDbContext class:

```csharp
public DbSet<Category> Categories { get; set; }
```

9. Open the HomeController.cs file located in the Controllers folder.
10. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    using (var db = new ApplicationDbContext())
    {
        var categories = db.Categories.ToList();
        return View(categories);
    }
}
```

11. Open the Index.cshtml file located in the Views/Home folder.
12. Add the following code to display the categories:

```csharp
@model List<Category>

<h2>Categories</h2>
<table>
    <tr>
        <th>Id</th>
        <th>Name</th>
    </tr>
    @foreach (var category in Model)
    {
        <tr>
            <td>@category.Id</td>
            <td>@category.Name</td>
        </tr>
    }
</table>
```

13. Run the application and navigate to the home page. You should see the categories displayed on the page.

## Explanation
In this program, we use the Code First Approach of the Entity Framework to perform CRUD operations on the category table. We start by installing the Entity Framework and adding a connection string to the Web.config file. We then create a Category class in the Models folder to represent the category table. We add a DbSet property to the ApplicationDbContext class to represent the categories table in the database. In the HomeController, we retrieve the categories from the database using the ApplicationDbContext and pass them to the view. In the view, we use a foreach loop to display the categories in a table.

This approach allows us to easily perform CRUD operations on the category table using the Entity Framework and display the data in the view.

