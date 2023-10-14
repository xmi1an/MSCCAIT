# Practical-09.md

## Problem Statement
Write a MVC program to perform CRUD operations on the category table using the Database First Approach of entity framework.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the Models folder and add a new ADO.NET Entity Data Model.
3. Choose "EF Designer from database" and click Next.
4. Configure the connection to your database and select the category table.
5. Click Finish to generate the entity model classes.
6. Open the HomeController.cs file located in the Controllers folder.
7. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    using (var context = new YourDbContext())
    {
        var categories = context.Categories.ToList();
        return View(categories);
    }
}
```

8. Open the Index.cshtml file located in the Views/Home folder.
9. Add the following code to display the categories:

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

10. Run the application and navigate to the home page. You should see the categories displayed on the page.

11. To perform CRUD operations on the category table, you can add the following action methods to the HomeController.cs file:

```csharp
public ActionResult Create()
{
    return View();
}

[HttpPost]
public ActionResult Create(Category category)
{
    if (ModelState.IsValid)
    {
        using (var context = new YourDbContext())
        {
            context.Categories.Add(category);
            context.SaveChanges();
        }
        return RedirectToAction("Index");
    }
    return View(category);
}

public ActionResult Edit(int id)
{
    using (var context = new YourDbContext())
    {
        var category = context.Categories.Find(id);
        if (category != null)
        {
            return View(category);
        }
    }
    return RedirectToAction("Index");
}

[HttpPost]
public ActionResult Edit(Category category)
{
    if (ModelState.IsValid)
    {
        using (var context = new YourDbContext())
        {
            context.Entry(category).State = EntityState.Modified;
            context.SaveChanges();
        }
        return RedirectToAction("Index");
    }
    return View(category);
}

public ActionResult Delete(int id)
{
    using (var context = new YourDbContext())
    {
        var category = context.Categories.Find(id);
        if (category != null)
        {
            return View(category);
        }
    }
    return RedirectToAction("Index");
}

[HttpPost]
public ActionResult Delete(int id, FormCollection form)
{
    using (var context = new YourDbContext())
    {
        var category = context.Categories.Find(id);
        if (category != null)
        {
            context.Categories.Remove(category);
            context.SaveChanges();
        }
    }
    return RedirectToAction("Index");
}
```

12. Create the Create.cshtml, Edit.cshtml, and Delete.cshtml files in the Views/Home folder to display the create, edit, and delete forms respectively.

13. Run the application and navigate to the home page. You should be able to perform CRUD operations on the category table.

## Explanation
In this program, we use the Database First Approach of entity framework to generate the entity model classes for the category table. We then use these classes to perform CRUD operations on the category table. The Index action method retrieves all categories from the database and passes them to the view. The view displays the categories in a table. The Create, Edit, and Delete action methods handle the corresponding CRUD operations and redirect to the Index action method after the operation is completed.

By using the Database First Approach of entity framework, we can easily perform CRUD operations on the category table without having to write SQL queries manually. The entity framework takes care of generating the necessary SQL statements and executing them against the database.


