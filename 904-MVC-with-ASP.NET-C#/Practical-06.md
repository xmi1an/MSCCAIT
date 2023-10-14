# Practical-06.md

## Problem Statement
Write a MVC program to introduce the concept of Cookies and Session.

## Solution

1. Create a new ASP.NET MVC project in Visual Studio.
2. Open the HomeController.cs file located in the Controllers folder.
3. Add the following code to the Index action method:

```csharp
public ActionResult Index()
{
    // Set a cookie
    HttpCookie cookie = new HttpCookie("username", "JohnDoe");
    Response.Cookies.Add(cookie);

    // Set a session variable
    Session["isLoggedIn"] = true;

    return View();
}
```

4. Open the Index.cshtml file located in the Views/Home folder.
5. Add the following code to display the cookie and session variable:

```csharp
<h2>Cookies and Session</h2>
<p>Username: @Request.Cookies["username"].Value</p>
<p>Is Logged In: @Session["isLoggedIn"]</p>
```

6. Run the application and navigate to the home page. You should see the cookie and session variable displayed on the page.

## Explanation
In this program, we introduce the concept of cookies and session in MVC.

In the controller, we set a cookie named "username" with the value "JohnDoe" using the `Response.Cookies.Add()` method. We also set a session variable named "isLoggedIn" with the value true using the `Session["isLoggedIn"]` syntax.

In the view, we use the `Request.Cookies["username"].Value` syntax to access the value of the cookie and display it on the page. We also use the `Session["isLoggedIn"]` syntax to access the value of the session variable and display it on the page.

Cookies are used to store small amounts of data on the client-side, while session variables are used to store data on the server-side for a specific user session. Both cookies and session variables can be used to persist data between requests and provide a way to maintain state in an MVC application.

