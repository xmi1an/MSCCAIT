# Practical-01

## Problem Statement

Create an android program that will display "Hello World" in the middle of the screen with red color and also implement several callback events of the activity class.

## Solution

To solve this problem, follow the steps below:

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `TextView` element to the layout with the following attributes:
   - `android:id="@+id/helloWorldTextView"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:layout_gravity="center"`
   - `android:text="Hello World"`
   - `android:textColor="#FF0000"` (red color)
4. Open the `MainActivity.java` file.
5. Implement the necessary callback events of the `Activity` class, such as `onCreate`, `onStart`, `onResume`, etc.
6. In the `onCreate` method, set the content view to the `activity_main.xml` layout file using `setContentView(R.layout.activity_main)`.
7. Build and run the application on an Android device or emulator.

## Explanation

In this solution, we create a simple Android application that displays the text "Hello World" in the middle of the screen with red color. We achieve this by adding a `TextView` element to the layout file and setting its attributes accordingly. Additionally, we implement the necessary callback events of the `Activity` class to handle the lifecycle of the application.

By following the above steps, you will be able to create an Android program that meets the requirements of the problem statement.

