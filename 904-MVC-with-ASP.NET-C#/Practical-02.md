# Practical-02.md

## Problem Statement
Write a MVC program to create a Login Form using Html Helper Methods.

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

4. Open the Index.cshtml file located in the Views/Home folder.
5. Add the following code to create the login form using Html Helper methods:

```csharp
@using (Html.BeginForm("Login", "Home", FormMethod.Post))
{
    <div>
        @Html.LabelFor(m => m.Username)
        @Html.TextBoxFor(m => m.Username)
    </div>
    <div>
        @Html.LabelFor(m => m.Password)
        @Html.PasswordFor(m => m.Password)
    </div>
    <div>
        <input type="submit" value="Login" />
    </div>
}
```

6. Add the following code to the HomeController.cs file to handle the form submission:

```csharp
[HttpPost]
public ActionResult Login(LoginViewModel model)
{
    if (ModelState.IsValid)
    {
        // Perform login logic here
        // Redirect to the appropriate page
    }

    return View(model);
}
```

7. Create a new class called LoginViewModel.cs in the Models folder with the following code:

```csharp
public class LoginViewModel
{
    [Required]
    public string Username { get; set; }

    [Required]
    public string Password { get; set; }
}
```

8. Run the application and navigate to the home page. You should see the login form displayed.
9. Enter a username and password and click the Login button. The form will be submitted to the Login action method in the HomeController.cs file.
10. Handle the login logic in the Login action method and redirect the user to the appropriate page.

## Explanation
In this program, we create a login form using Html Helper methods in the view. The form is submitted to the Login action method in the controller, where we can handle the login logic. We use a LoginViewModel class to represent the data entered in the form and perform validation using data annotations.

Using Html Helper methods makes it easier to create form elements and bind them to model properties. It also helps with generating the necessary HTML and handling form submissions.

