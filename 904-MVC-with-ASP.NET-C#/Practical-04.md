# Practical-04.md

## Problem Statement
Write a MVC program to create a web application with a user-defined layout.

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
5. Add the following code to create the user-defined layout:

```csharp
@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}

<h2>Welcome to My Web Application</h2>
<p>This is the home page of my web application.</p>
```

6. Create a new folder called Shared in the Views folder.
7. Create a new file called _Layout.cshtml in the Views/Shared folder.
8. Add the following code to define the user-defined layout:

```csharp
<!DOCTYPE html>
<html>
<head>
    <title>My Web Application</title>
</head>
<body>
    <header>
        <h1>My Web Application</h1>
    </header>

    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>

    <main>
        @RenderBody()
    </main>

    <footer>
        <p>&copy; 2021 My Web Application. All rights reserved.</p>
    </footer>
</body>
</html>
```

9. Run the application and navigate to the home page. You should see the user-defined layout with the home page content displayed.

## Explanation
In this program, we create a web application with a user-defined layout. The layout is defined in the _Layout.cshtml file, which contains the HTML structure for the header, navigation, main content, and footer sections of the web application. The Index.cshtml file uses the user-defined layout by setting the Layout property to the path of the _Layout.cshtml file.

Using a user-defined layout allows us to define a consistent structure and design for all pages in the web application. It also makes it easier to manage and update the layout across multiple pages.

