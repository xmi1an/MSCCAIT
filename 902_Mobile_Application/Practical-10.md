# Practical-10.md

## Mobile Application

### Practical List

Create an android application to read a file from the sdcard and display that file content on the screen.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/button"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Read File"`
   - `android:layout_gravity="center"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `readFile` to handle the button click event and read the file content:
   ```java
   private void readFile() {
       File file = new File(Environment.getExternalStorageDirectory(), "file.txt");
       StringBuilder content = new StringBuilder();
       try {
           BufferedReader reader = new BufferedReader(new FileReader(file));
           String line;
           while ((line = reader.readLine()) != null) {
               content.append(line).append("\n");
           }
           reader.close();
       } catch (IOException e) {
           e.printStackTrace();
       }
       TextView textView = findViewById(R.id.textView);
       textView.setText(content.toString());
   }
   ```
7. Run the application on an Android device or emulator.
8. Click the "Read File" button to read the file content and display it on the screen.

