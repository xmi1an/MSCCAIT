# Practical-06.md

## Mobile Application

### Practical List

Create an android program that will display the use of a menu that will change the color of the background screen after selecting a menu option.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `TextView` element to the layout with the following attributes:
   - `android:id="@+id/textView"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="match_parent"`
   - `android:gravity="center"`
   - `android:text="Background Color Changer"`
   - `android:textSize="24sp"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `showColorMenu` to display the color menu options:
   ```java
   private void showColorMenu() {
       PopupMenu popupMenu = new PopupMenu(this, findViewById(R.id.textView));
       popupMenu.getMenuInflater().inflate(R.menu.color_menu, popupMenu.getMenu());
       popupMenu.setOnMenuItemClickListener(new PopupMenu.OnMenuItemClickListener() {
           @Override
           public boolean onMenuItemClick(MenuItem item) {
               int color = 0;
               switch (item.getItemId()) {
                   case R.id.menu_red:
                       color = Color.RED;
                       break;
                   case R.id.menu_green:
                       color = Color.GREEN;
                       break;
                   case R.id.menu_blue:
                       color = Color.BLUE;
                       break;
               }
               findViewById(R.id.textView).setBackgroundColor(color);
               return true;
           }
       });
       popupMenu.show();
   }
   ```
7. Create a new XML file called `color_menu.xml` in the `res/menu` directory.
8. Open the `color_menu.xml` file and add the following code to define the color menu options:
   ```xml
   <menu xmlns:android="http://schemas.android.com/apk/res/android">
       <item
           android:id="@+id/menu_red"
           android:title="Red" />
       <item
           android:id="@+id/menu_green"
           android:title="Green" />
       <item
           android:id="@+id/menu_blue"
           android:title="Blue" />
   </menu>
   ```
9. Open the `activity_main.xml` layout file.
10. Add a button element below the `TextView` with the following attributes:
    - `android:id="@+id/button"`
    - `android:layout_width="wrap_content"`
    - `android:layout_height="wrap_content"`
    - `android:text="Change Color"`
11. Open the `MainActivity.java` file.
12. Inside the `onCreate` method, add the following code to set a click listener for the button:
    ```java
    Button button = findViewById(R.id.button);
    button.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            showColorMenu();
        }
    });
    ```
13. Run the application on an Android device or emulator.
14. Click the "Change Color" button to display the color menu.
15. Select a color option from the menu to change the background color of the text view.

Congratulations! You have successfully created an Android program that displays the use of a menu to change the color of the background screen.

