# Practical-05.md

## Problem Statement
Write a MVC program to create a partial view for the login page.

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
@Html.Partial("_LoginPartial")
```

6. Create a new file called _LoginPartial.cshtml in the Views/Shared folder.
7. Add the following code to create the login form in the partial view:

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

8. Add the following code to the HomeController.cs file to handle the form submission:

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

9. Create a new class called LoginViewModel.cs in the Models folder with the following code:

```csharp
public class LoginViewModel
{
    [Required]
    public string Username { get; set; }

    [Required]
    public string Password { get; set; }
}
```

10. Run the application and navigate to the home page. You should see the login form displayed on the page.

## Explanation
In this program, we create a partial view called _LoginPartial.cshtml that contains the login form. We then include this partial view in the Index.cshtml file using the `@Html.Partial()` method. The login form is created using Html Helper methods, and the form submission is handled in the HomeController.cs file using the `[HttpPost]` attribute.

Using partial views allows us to reuse code and create modular components in our MVC application. In this case, we create a separate partial view for the login form, which can be included in multiple views throughout the application.

