# Practical-11.md

## Mobile Application

### Practical List

Create an android program to perform all database operations like insert, update, delete, and display.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/insertButton"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Insert"`
   - `android:layout_gravity="center"`
4. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/updateButton"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Update"`
   - `android:layout_gravity="center"`
5. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/deleteButton"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Delete"`
   - `android:layout_gravity="center"`
6. Add a `Button` element to the layout with the following attributes:
   - `android:id="@+id/displayButton"`
   - `android:layout_width="wrap_content"`
   - `android:layout_height="wrap_content"`
   - `android:text="Display"`
   - `android:layout_gravity="center"`
7. Open the `MainActivity.java` file.
8. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
9. Create a new method called `insertData` to insert data into the database:
   ```java
   private void insertData() {
       // Code to insert data into the database
   }
   ```
10. Create a new method called `updateData` to update data in the database:
   ```java
   private void updateData() {
       // Code to update data in the database
   }
   ```
11. Create a new method called `deleteData` to delete data from the database:
   ```java
   private void deleteData() {
       // Code to delete data from the database
   }
   ```
12. Create a new method called `displayData` to display data from the database:
   ```java
   private void displayData() {
       // Code to display data from the database
   }
   ```
13. Add click listeners to the buttons in the `onCreate` method to call the respective methods:
   ```java
   Button insertButton = findViewById(R.id.insertButton);
   insertButton.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           insertData();
       }
   });

   Button updateButton = findViewById(R.id.updateButton);
   updateButton.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           updateData();
       }
   });

   Button deleteButton = findViewById(R.id.deleteButton);
   deleteButton.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           deleteData();
       }
   });

   Button displayButton = findViewById(R.id.displayButton);
   displayButton.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View v) {
           displayData();
       }
   });
   ```
14. Implement the database operations in the respective methods using SQLiteOpenHelper or any other database library of your choice.

