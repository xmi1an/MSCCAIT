# Practical-11.md

## Problem Statement
Write a MVC program to introduce the concept of Exception Filter.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the HomeController.cs file located in the Controllers folder.
3. Add the following code to the Index action method:

```csharp
[HandleError(ExceptionType = typeof(Exception), View = "Error")]
public ActionResult Index()
{
    throw new Exception("An error occurred.");
}
```

4. Create a new view called Error.cshtml in the Views/Shared folder with the following code:

```csharp
@{
    ViewBag.Title = "Error";
    Layout = "~/Views/Shared/_Layout.cshtml";
}

<h2>Error</h2>
<p>An error occurred while processing your request.</p>
```

5. Open the web.config file located in the root folder of the project.
6. Add the following code inside the <system.web> section to enable custom errors:

```xml
<customErrors mode="On" defaultRedirect="~/Error">
    <error statusCode="404" redirect="~/Error/NotFound" />
</customErrors>
```

7. Run the application and navigate to the home page. You should see the error message displayed on the page.

## Explanation
In this program, we introduce the concept of an exception filter. We decorate the Index action method with the [HandleError] attribute, specifying the type of exception to handle and the view to display in case of an exception. When an exception occurs in the Index action method, the exception filter will catch it and redirect to the specified error view.

We also create a custom error view called Error.cshtml to display a generic error message. We configure the web.config file to enable custom errors and redirect to the error view in case of a 404 error.

This approach allows us to handle exceptions in a centralized manner and provide a consistent error handling experience for our users.

