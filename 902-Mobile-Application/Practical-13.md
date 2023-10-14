# Practical-13.md

## Mobile Application

### Practical List

Create an android application to pick any image from the native application gallery and display it on the screen.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add an `ImageView` element to the layout with the following attributes:
   - `android:id="@+id/imageView"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="match_parent"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `pickImage` to open the image picker:
   ```java
   private void pickImage() {
       Intent intent = new Intent(Intent.ACTION_PICK, MediaStore.Images.Media.EXTERNAL_CONTENT_URI);
       startActivityForResult(intent, PICK_IMAGE_REQUEST);
   }
   ```
7. Override the `onActivityResult` method to handle the result of the image picker:
   ```java
   @Override
   protected void onActivityResult(int requestCode, int resultCode, Intent data) {
       super.onActivityResult(requestCode, resultCode, data);
       if (requestCode == PICK_IMAGE_REQUEST && resultCode == RESULT_OK && data != null) {
           Uri imageUri = data.getData();
           ImageView imageView = findViewById(R.id.imageView);
           imageView.setImageURI(imageUri);
       }
   }
   ```
8. Add the necessary permissions to the `AndroidManifest.xml` file:
   ```xml
   <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
   ```
9. Run the application on an emulator or a physical device.
10. Click the "Pick Image" button to open the image picker.
11. Select an image from the gallery.
12. The selected image will be displayed on the screen.

