# Practical-03.md

## Problem Statement
Write a MVC program to create a Strongly Typed view for an employee model object or a list of employee model objects.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the HomeController.cs file located in the Controllers folder.
3. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    // Create a list of employee model objects
    List<Employee> employees = new List<Employee>();

    // Add employee objects to the list
    employees.Add(new Employee { Id = 1, Name = "John Doe", Age = 25 });
    employees.Add(new Employee { Id = 2, Name = "Jane Smith", Age = 30 });
    employees.Add(new Employee { Id = 3, Name = "Bob Johnson", Age = 35 });

    // Pass the list of employee model objects to the view
    return View(employees);
}
```

4. Create a new class called Employee.cs in the Models folder with the following code:

```csharp
public class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}
```

5. Open the Index.cshtml file located in the Views/Home folder.
6. Add the following code at the top of the file to declare the model type:

```csharp
@model List<Employee>
```

7. Use the model to access the list of employee model objects in the view:

```csharp
<h2>Employee List</h2>
<table>
    <tr>
        <th>Id</th>
        <th>Name</th>
        <th>Age</th>
    </tr>
    @foreach (var employee in Model)
    {
        <tr>
            <td>@employee.Id</td>
            <td>@employee.Name</td>
            <td>@employee.Age</td>
        </tr>
    }
</table>
```

8. Run the application and navigate to the home page. You should see the list of employees displayed in a table format.

## Explanation
In this program, we create a list of employee model objects in the controller and add some employee objects to it. We then pass this list of employee model objects to the view using the `View()` method. In the view, we declare the model type as `List<Employee>` and use the model to access the list of employee model objects and display them in a table format.

Using a strongly typed view allows us to work with model objects directly in the view, making it easier to access and display the data.

