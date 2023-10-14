# Practical-09.md

## Mobile Application

### Practical List

Create an android program that will play a media file from the memory card.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/button"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Play Media File"`
   - `android:layout_gravity="center"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `playMediaFile` to handle the button click event and play the media file:
   ```java
   private void playMediaFile() {
       String filePath = "/path/to/media/file.mp3"; // Replace with the actual file path
       MediaPlayer mediaPlayer = new MediaPlayer();
       try {
           mediaPlayer.setDataSource(filePath);
           mediaPlayer.prepare();
           mediaPlayer.start();
       } catch (IOException e) {
           e.printStackTrace();
       }
   }
   ```
7. Inside the `onCreate` method, add the following code to set the click listener for the button:
   ```java
   Button button = findViewById(R.id.button);
   button.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           playMediaFile();
       }
   });
   ```
8. Run the application on an Android device or emulator.
9. Click the "Play Media File" button to play the media file from the memory card.
10.  Verify that the media file is played successfully.
