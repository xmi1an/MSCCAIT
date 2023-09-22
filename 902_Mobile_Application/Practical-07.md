# Practical-07.md

## Mobile Application

### Practical List

Create an android program that will have a UI where the main screen has a list of cars. On selecting any car, the next screen will display the number of cars in the gallery with car information.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `ListView` element to the layout with the following attributes:
   - `android:id="@+id/listView"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="match_parent"`
4. Create a new XML file called `car_item.xml` in the `res/layout` directory.
5. Open the `car_item.xml` file and add the following code to define the layout for each car item in the list:
   ```xml
   <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
       android:layout_width="match_parent"
       android:layout_height="wrap_content"
       android:orientation="horizontal"
       android:padding="16dp">

       <ImageView
           android:id="@+id/carImageView"
           android:layout_width="48dp"
           android:layout_height="48dp"
           android:src="@drawable/car_icon" />

       <TextView
           android:id="@+id/carNameTextView"
           android:layout_width="wrap_content"
           android:layout_height="wrap_content"
           android:textSize="16sp"
           android:textStyle="bold"
           android:layout_marginStart="16dp" />

   </LinearLayout>
   ```
6. Open the `MainActivity.java` file.
7. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
8. Create a new method called `setupCarList` to populate the list view with car items:
   ```java
   private void setupCarList() {
       ListView listView = findViewById(R.id.listView);
       List<Car> carList = getCarList();
       CarListAdapter adapter = new CarListAdapter(this, carList);
       listView.setAdapter(adapter);
       listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
           @Override
           public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
               Car car = (Car) parent.getItemAtPosition(position);
               showCarDetails(car);
           }
       });
   }
   ```
9. Create a new class called `Car` to represent a car object with the following attributes:
   - `String name`
   - `int imageResId`
   - `int galleryCount`
   - `String information`
10. Create a new class called `CarListAdapter` that extends `ArrayAdapter<Car>` and implements the necessary methods to display the car items in the list view using the `car_item.xml` layout.
11. Implement the `getCarList` method to return a list of car objects with dummy data.
12. Create a new method called `showCarDetails` to display the car details in the next screen:
    ```java
    private void showCarDetails(Car car) {
        Intent intent = new Intent(this, CarDetailsActivity.class);
        intent.putExtra("car", car);
        startActivity(intent);
    }
    ```
13. Create a new activity called `CarDetailsActivity` with a layout file `activity_car_details.xml`.
14. Open the `CarDetailsActivity.java` file.
15. Inside the `onCreate` method, add the following code to get the car object from the intent and display the car details:
    ```java
    Car car = getIntent().getParcelableExtra("car");
    TextView carNameTextView = findViewById(R.id.carNameTextView);
    TextView galleryCountTextView = findViewById(R.id.galleryCountTextView);
    TextView informationTextView = findViewById(R.id.informationTextView);
    carNameTextView.setText(car.getName());
    galleryCountTextView.setText(String.valueOf(car.getGalleryCount()));
    informationTextView.setText(car.getInformation());
    ```
16. Run the application on an Android device or emulator.
17. The main screen will display a list of cars.
18. Select any car from the list to navigate to the next screen and display the car details.

Congratulations! You have successfully created an Android program that has a UI where the main screen has a list of cars. On selecting any car, the next screen displays the number of cars in the gallery with car information.
