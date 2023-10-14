# Practical-02

## Problem Statement

Create an android program that will display login functionality where username (EmailID) and password should be validated. If username/password will be wrong login button remain disabled otherwise move to next screen (intent) with welcome (username) message.

## Solution

To solve this problem, follow the steps below:

1. Create a new Android project in Android Studio.
2. Open the `activity_login.xml` layout file.
3. Add two `EditText` elements to the layout with the following attributes:
   - `android:id="@+id/usernameEditText"`
   - `android:id="@+id/passwordEditText"`
4. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/loginButton"`
   - `android:enabled="false"`
5. Open the `LoginActivity.java` file.
6. Implement the necessary logic to validate the username and password entered by the user.
7. If the username/password is incorrect, disable the login button.
8. If the username/password is correct, enable the login button and set an `OnClickListener` to handle the button click event.
9. In the button click event, create an intent to navigate to the next screen (e.g., `WelcomeActivity`) and pass the username as an extra.
10. Build and run the application on an Android device or emulator.

## Explanation

In this solution, we create an Android application that implements login functionality. The user is required to enter their username (EmailID) and password. The login button is initially disabled until the username and password are validated. If the username/password is incorrect, the login button remains disabled. If the username/password is correct, the login button is enabled and clicking on it navigates to the next screen (e.g., `WelcomeActivity`) with a welcome message that includes the username.

By following the above steps, you will be able to create an Android program that meets the requirements of the problem statement.
