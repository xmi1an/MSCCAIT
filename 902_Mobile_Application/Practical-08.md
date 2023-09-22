# Practical-08.md

## Mobile Application

### Practical List

Create an android program that will read phonebook contacts using content providers and display them in a list.

#### Steps

1. Create a new Android project in Android Studio.
2. Open the `activity_main.xml` layout file.
3. Add a `ListView` element to the layout with the following attributes:
   - `android:id="@+id/listView"`
   - `android:layout_width="match_parent"`
   - `android:layout_height="match_parent"`
4. Open the `MainActivity.java` file.
5. Inside the `onCreate` method, add the following code to set the content view to the `activity_main.xml` layout:
   ```java
   setContentView(R.layout.activity_main);
   ```
6. Create a new method called `displayContacts` to fetch and display the phonebook contacts:
   ```java
   private void displayContacts() {
       List<Contact> contactList = getContacts();
       ContactListAdapter adapter = new ContactListAdapter(this, contactList);
       ListView listView = findViewById(R.id.listView);
       listView.setAdapter(adapter);
   }
   ```
7. Create a new class called `Contact` to represent a contact object with the following attributes:
   - `String name`
   - `String phoneNumber`
8. Create a new class called `ContactListAdapter` that extends `ArrayAdapter<Contact>` and implements the necessary methods to display the contact items in the list view.
9. Implement the `getContacts` method to fetch the phonebook contacts using content providers and return a list of contact objects.
10. Run the application on an Android device or emulator.
11. The list view should display the phonebook contacts with their names and phone numbers.
