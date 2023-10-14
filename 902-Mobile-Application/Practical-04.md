# Practical-04

## Problem Statement

Create an android program that will display the use of a spinner, where the spinner takes items and animations from the "string.xml" file. When selecting an item from spinner-1, the image should be changed in the image control. When selecting an animation from spinner-2, the image should be animated.

## Solution

To solve this problem, follow the steps below:

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `Spinner` element to the layout with the following attributes:
   - `android:id="@+id/itemSpinner"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
4. Add another `Spinner` element to the layout with the following attributes:
   - `android:id="@+id/animationSpinner"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
5. Open the `MainActivity.java` file.
6. Implement the necessary logic to handle the spinner selection events.
7. In the `onCreate` method, initialize the spinners and set their adapters.
8. Create an array adapter for the item spinner using the items from the "string.xml" file.
9. Create an array adapter for the animation spinner using the animations from the "string.xml" file.
10. Set the item spinner adapter and set an `OnItemSelectedListener` to handle the item selection event.
11. Set the animation spinner adapter and set an `OnItemSelectedListener` to handle the animation selection event.
12. In the item selection event, change the image in the image control based on the selected item.
13. In the animation selection event, animate the image based on the selected animation.
14. Open the `strings.xml` file.
15. Add the items and animations as string resources.
16. Build and run the application on an Android device or emulator.

## Explanation

In this solution, we create an Android application that demonstrates the use of a spinner. The spinner takes items and animations from the "string.xml" file. When an item is selected from spinner-1, the image in the image control is changed accordingly. When an animation is selected from spinner-2, the image is animated based on the selected animation.

By following the above steps, you will be able to create an Android program that meets the requirements of the problem statement.

