# Practical-01.md

## Problem Statement
Write a MVC program to pass data from controller to view by using data dictionary object.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the HomeController.cs file located in the Controllers folder.
3. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    // Create a data dictionary object
    Dictionary<string, string> data = new Dictionary<string, string>();

    // Add data to the dictionary
    data.Add("Name", "John Doe");
    data.Add("Age", "25");
    data.Add("Email", "johndoe@example.com");

    // Pass the data dictionary to the view
    return View(data);
}
```

4. Open the Index.cshtml file located in the Views/Home folder.
5. Add the following code at the top of the file to declare the model type:

```csharp
@model Dictionary<string, string>
```

6. Use the model to access the data dictionary in the view:

```csharp
<h2>Details</h2>
<p>Name: @Model["Name"]</p>
<p>Age: @Model["Age"]</p>
<p>Email: @Model["Email"]</p>
```

7. Run the application and navigate to the home page. You should see the data displayed on the page.

## Explanation
In this program, we create a data dictionary object in the controller and add some data to it. We then pass this data dictionary object to the view using the `View()` method. In the view, we declare the model type as `Dictionary<string, string>` and use the model to access the data dictionary and display the values on the page.

This approach allows us to pass data from the controller to the view in a structured manner, making it easier to work with and display the data in the view.
