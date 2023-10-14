# Practical-10.md

## Problem Statement
Write a MVC program to perform CRUD operations on the category table using Model First Approach of entity framework.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the Solution Explorer and right-click on the project name.
3. Select "Add" and then "New Item".
4. In the "Add New Item" dialog, select "Data" from the left menu.
5. Select "ADO.NET Entity Data Model" and click "Add".
6. In the "Entity Data Model Wizard", select "EF Designer from database" and click "Next".
7. Configure the connection to the database and click "Next".
8. Select the "Category" table from the database and click "Finish".
9. Open the HomeController.cs file located in the Controllers folder.
10. Add the following code to the Index action method:

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

14. To perform CRUD operations on the category table, you can add the following action methods to the HomeController.cs file:

```csharp
public ActionResult Create()
{
    return View();
}

[HttpPost]
public ActionResult Create(Category category)
{
    using (var context = new YourDbContext())
    {
        context.Categories.Add(category);
        context.SaveChanges();
    }
    return RedirectToAction("Index");
}

public ActionResult Edit(int id)
{
    using (var context = new YourDbContext())
    {
        var category = context.Categories.Find(id);
        return View(category);
    }
}

[HttpPost]
public ActionResult Edit(Category category)
{
    using (var context = new YourDbContext())
    {
        context.Entry(category).State = EntityState.Modified;
        context.SaveChanges();
    }
    return RedirectToAction("Index");
}

public ActionResult Delete(int id)
{
    using (var context = new YourDbContext())
    {
        var category = context.Categories.Find(id);
        return View(category);
    }
}

[HttpPost]
public ActionResult Delete(Category category)
{
    using (var context = new YourDbContext())
    {
        context.Entry(category).State = EntityState.Deleted;
        context.SaveChanges();
    }
    return RedirectToAction("Index");
}
```

15. Create the Create.cshtml, Edit.cshtml, and Delete.cshtml files in the Views/Home folder with the following code:

Create.cshtml:
```csharp
@model Category

<h2>Create Category</h2>
@using (Html.BeginForm("Create", "Home", FormMethod.Post))
{
    <div>
        @Html.LabelFor(m => m.Name)
        @Html.TextBoxFor(m => m.Name)
    </div>
    <div>
        <input type="submit" value="Create" />
    </div>
}
```

Edit.cshtml:
```csharp
@model Category

<h2>Edit Category</h2>
@using (Html.BeginForm("Edit", "Home", FormMethod.Post))
{
    <div>
        @Html.HiddenFor(m => m.Id)
        @Html.LabelFor(m => m.Name)
        @Html.TextBoxFor(m => m.Name)
    </div>
    <div>
        <input type="submit" value="Save" />
    </div>
}
```

Delete.cshtml:
```csharp
@model Category

<h2>Delete Category</h2>
@using (Html.BeginForm("Delete", "Home", FormMethod.Post))
{
    <div>
        @Html.HiddenFor(m => m.Id)
        <p>Are you sure you want to delete this category?</p>
        <p>@Model.Name</p>
    </div>
    <div>
        <input type="submit" value="Delete" />
    </div>
}
```

16. Run the application and navigate to the home page. You should see the categories displayed on the page. You can click on the "Create" button to create a new category, click on the "Edit" button to edit an existing category, and click on the "Delete" button to delete a category.

17. The CRUD operations will be performed on the category table using the Model First Approach of entity framework.

## Explanation
In this program, we use the Model First Approach of entity framework to perform CRUD operations on the category table. We create an ADO.NET Entity Data Model to connect to the database and generate the entity classes for the category table. We then use these entity classes in the controller to query and manipulate the data. The categories are displayed in the view using a foreach loop, and the create, edit, and delete operations are performed using form submissions.

This approach allows us to easily perform CRUD operations on the category table without writing complex SQL queries. The entity framework handles the database operations for us, making it easier to work with and maintain the code.

