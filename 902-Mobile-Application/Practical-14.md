# Practical-14.md

## Mobile Application

### Practical List

Create an android program to display the use of a custom component with extend TextView to Date View component.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `com.example.dateview.DateView` element to the layout with the following attributes:
   - `android:id="@+id/dateView"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:textSize="24sp"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new class called `DateView` that extends `TextView` and override the necessary methods to display the current date:
   ```java
   public class DateView extends TextView {
       public DateView(Context context) {
           super(context);
           init();
       }

       public DateView(Context context, AttributeSet attrs) {
           super(context, attrs);
           init();
       }

       public DateView(Context context, AttributeSet attrs, int defStyleAttr) {
           super(context, attrs, defStyleAttr);
           init();
       }

       private void init() {
           SimpleDateFormat dateFormat = new SimpleDateFormat("dd/MM/yyyy", Locale.getDefault());
           String currentDate = dateFormat.format(new Date());
           setText(currentDate);
       }
   }
   ```
7. Open the `res/values/attrs.xml` file and add the following code to define the custom attributes for the `DateView` component:
   ```xml
   <resources>
       <declare-styleable name="DateView">
           <attr name="dateFormat" format="string" />
       </declare-styleable>
   </resources>
   ```
8. Open the `res/layout/activity_main.xml` file and add the following code to define the custom `DateView` component:
   ```xml
   <com.example.dateview.DateView
       android:id="@+id/dateView"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:textSize="24sp" />
   ```
9. Run the application on an emulator or device to see the custom `DateView` component displaying the current date.

