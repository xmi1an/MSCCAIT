# Practical-12.md

## Mobile Application

### Practical List

Create an android program to send a message between two emulators and read messages from any one emulator (mobile).

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add two `EditText` elements to the layout with the following attributes:
   - `android:id="@+id/editTextSender"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="wrap_content"`
   - `android:hint="Enter message to send"`
   - `android:inputType="text"`
   - `android:layout_marginTop="16dp"`
   - `android:layout_marginBottom="16dp"`
   - `android:layout_marginStart="16dp"`
   - `android:layout_marginEnd="16dp"`
   - `android:imeOptions="actionSend"`
   - `android:maxLines="1"`
   - `android:singleLine="true"`
   - `android:textSize="16sp"`
   - `android:textColor="@android:color/black"`

   - `android:id="@+id/editTextReceiver"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="wrap_content"`
   - `android:hint="Received message will be displayed here"`
   - `android:inputType="text"`
   - `android:layout_marginTop="16dp"`
   - `android:layout_marginBottom="16dp"`
   - `android:layout_marginStart="16dp"`
   - `android:layout_marginEnd="16dp"`
   - `android:imeOptions="actionDone"`
   - `android:maxLines="1"`
   - `android:singleLine="true"`
   - `android:textSize="16sp"`
   - `android:textColor="@android:color/black"`
   - `android:enabled="false"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `sendMessage` to send a message between two emulators:
   ```java
   private void sendMessage() {
       EditText editTextSender = findViewById(R.id.editTextSender);
       EditText editTextReceiver = findViewById(R.id.editTextReceiver);
       String message = editTextSender.getText().toString();
       editTextReceiver.setText(message);
   }
   ```
7. Inside the `onCreate` method, add the following code to set the `OnClickListener` for the send button:
   ```java
   Button sendButton = findViewById(R.id.sendButton);
   sendButton.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           sendMessage();
       }
   });
   ```
8. Run the application on two emulators or devices.
9. Enter a message in the sender emulator/device and click the send button.
10. The message should be displayed in the receiver emulator/device.

