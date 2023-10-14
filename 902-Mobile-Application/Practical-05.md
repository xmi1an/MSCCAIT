# Practical-05

## Problem Statement

Create an android program that will display a toast (message) on a specific interval of time.

## Solution

To solve this problem, follow the steps below:

1. Create a new Android project in Android Studio.
2. Open the `MainActivity.java` file.
3. Implement the necessary logic to display a toast message on a specific interval of time.
4. In the `onCreate` method, create a `Handler` object and use the `postDelayed` method to schedule a task that displays the toast message after a specific interval of time.
5. In the scheduled task, use the `Toast` class to display the desired message.
6. Build and run the application on an Android device or emulator.

## Explanation

In this solution, we create an Android application that displays a toast message on a specific interval of time. We achieve this by using a `Handler` object to schedule a task that displays the toast message after a specific interval of time. The `postDelayed` method allows us to delay the execution of a task by a specified amount of time. In the scheduled task, we use the `Toast` class to display the desired message.

By following the above steps, you will be able to create an Android program that meets the requirements of the problem statement.

