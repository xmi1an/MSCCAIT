# Practical-03

## Problem Statement

Create an application to draw a line on the screen as the user drags their finger.

## Solution

To solve this problem, follow the steps below:

1. Create a new Android project in Android Studio.
2. Open the `MainActivity.java` file.
3. Implement the necessary logic to handle touch events on the screen.
4. Override the `onTouchEvent` method and handle the `ACTION_DOWN`, `ACTION_MOVE`, and `ACTION_UP` events.
5. In the `ACTION_DOWN` event, get the starting coordinates of the touch.
6. In the `ACTION_MOVE` event, get the current coordinates of the touch and draw a line from the starting coordinates to the current coordinates.
7. In the `ACTION_UP` event, stop drawing the line.
8. Open the `activity_main.xml` layout file.
9. Add a `CustomView` element to the layout with the following attributes:
   - `android:id="@+id/customView"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="match_parent"`
10. Create a new Java class called `CustomView` that extends `View`.
11. Override the `onDraw` method in the `CustomView` class and implement the logic to draw the line on the screen.
12. In the `MainActivity` class, find the `CustomView` element by its ID and set it as the content view using `setContentView(R.layout.activity_main)`.
13. Build and run the application on an Android device or emulator.

## Explanation

In this solution, we create an Android application that allows the user to draw a line on the screen by dragging their finger. We achieve this by implementing the necessary logic to handle touch events on the screen. When the user touches the screen, we get the starting coordinates of the touch. As the user moves their finger, we get the current coordinates and draw a line from the starting coordinates to the current coordinates. When the user releases their finger, we stop drawing the line.

By following the above steps, you will be able to create an Android program that meets the requirements of the problem statement.

