# Practical-07.md

## Problem Statement
Write a MVC program to create a registration form for a student and validate the page using data annotation concept.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the HomeController.cs file located in the Controllers folder.
3. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    return View();
}
```

4. Create a new class called Student.cs in the Models folder with the following code:

```csharp
public class Student
{
    [Required(ErrorMessage = "Please enter your name")]
    public string Name { get; set; }

    [Required(ErrorMessage = "Please enter your email")]
    [EmailAddress(ErrorMessage = "Please enter a valid email address")]
    public string Email { get; set; }

    [Required(ErrorMessage = "Please enter your age")]
    [Range(18, 100, ErrorMessage = "Please enter a valid age between 18 and 100")]
    public int Age { get; set; }
}
```

5. Open the Index.cshtml file located in the Views/Home folder.
6. Add the following code at the top of the file to declare the model type:

```csharp
@model Student
```

7. Add the following code to create the registration form using Html Helper methods:

```csharp
@using (Html.BeginForm("Register", "Home", FormMethod.Post))
{
    <div>
        @Html.LabelFor(m => m.Name)
        @Html.TextBoxFor(m => m.Name)
        @Html.ValidationMessageFor(m => m.Name)
    </div>
    <div>
        @Html.LabelFor(m => m.Email)
        @Html.TextBoxFor(m => m.Email)
        @Html.ValidationMessageFor(m => m.Email)
    </div>
    <div>
        @Html.LabelFor(m => m.Age)
        @Html.TextBoxFor(m => m.Age)
        @Html.ValidationMessageFor(m => m.Age)
    </div>
    <div>
        <input type="submit" value="Register" />
    </div>
}
```

8. Add the following code to the HomeController.cs file to handle the form submission:

```csharp
[HttpPost]
public ActionResult Register(Student model)
{
    if (ModelState.IsValid)
    {
        // Perform registration logic here
        // Redirect to the appropriate page
    }

    return View("Index", model);
}
```

9. Run the application and navigate to the home page. You should see the registration form. Try submitting the form with and without entering valid data to see the validation in action.

## Explanation
In this program, we create a Student class in the Models folder with properties for name, email, and age. We use data annotations to add validation rules to these properties, such as requiring a value, requiring a valid email format, and requiring an age between 18 and 100.

In the view, we declare the model type as Student and use Html Helper methods to create the registration form. We also use Html Helper methods to display validation error messages if the user enters invalid data.

In the controller, we have an action method called Register that takes a Student object as a parameter. We use the ModelState.IsValid property to check if the submitted data is valid. If it is, we can perform the registration logic and redirect to the appropriate page. If it is not valid, we return the view with the model so that the user can see the validation error messages.

This approach allows us to create a registration form with validation using the data annotation concept, making it easier to ensure that the user enters valid data.


