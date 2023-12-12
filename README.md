# Car-Hub-Shop
CAR-HUB Application

Welcome to CarHub. It can be daunting when trying to sell a vehicle, especially if one does not want to trade it in or sell it to a used car lot for less than its real value.
Searching for a vehicle, driving from used car lot to used car lot, and dealing with all sorts of salespeople can be equally taxing.
CarHub attempts to solve this problem with an easy-to-use application in which sellers can list their vehicles and buyers can browse those listings.
The listings include relevant information about the vehicle and the seller's contact information, so they can then get in contact with each other directly,
and the sale of the vehicle can be conducted on their own terms.
Sellers can get their vehicles in front of potential buyers, and buyers can avoid the used car lot grind.


Code Structure
The code is structured in a modular manner, ensuring a separation of concerns:

1. Controller classes
    - AddListingController.java: implement the function for AddListing.fxml
    - HomePageController.java:  implement the function for HelloApplication.fxml
    - LoginController.java: implement the function for Login.fxml
    - RemoveListingController.java: implement the function for RemoveListing.fxml
    - UserPageController.java: implement the function for UserPage.fxml
    - VehicleController.java: implement the function for Vehicle.fxml
    - VehicleProfileController.java: implement the function for VehicleProfile.fxml
2. Main classes
    - Dialog_Box.java:
    - HelloApplication.java: Running the main application
    - Listing.java: populate the listings from users and cars
    - ListingData.java: created a array listing to populate the data
    - ListingDatabase.java: listing functions that connect with carhub database
    - Navigation.java: a navigation class to open scene
    - SelectedListing.java: a class that get selected listings
    - User.java: a singleton instance for user class
    - UserDate.java: provides a simple and straightforward way to manage user data and login status, single-user applications
    - UserSession.java: implement the status of the new/current user
3. Interface class
    - Dialog_Interface.java: implement the notification message box after Clicked Action.
4. Abstract class
    - Car.java: a abstract class that implement for VehicleProfileController.java
5. FXML files
    - AddListing.fxml: receive the implementation from AddListingController.java
    - HomePage.fxml: receive the implementation from HomePageController.java
    - Login.fxml: receive the implementation from LoginController.java
    - RemoveListing.fxml: receive the implementation from RemoveListingController.java
    - UserPage.fxml: receive the implementation from UserPageController.java
    - Vehicle.fxml: receive the implementation from VehicleController.java
    - VehicleProfile.fxml: receive the implementation from VehicleProfileController.java


Functional requirements. Each functional requirement item should describe both the functional requirement and how your application will meet that requirement.

- Users can sign up on Car-Hub.
- Users can log in/logout on Car-Hub.
- Users can edit their user information
- Users can create listings with information about their cars.
- Users can modify/delete their own listings
- Users can view listing/contact information.

Non-functional requirements. Each requirement item will describe both the requirement and how your application will meet that requirement.

1. Data Persistence.
This is achieved by storing all the data in CarHub in a database the application interacts with.

2. Simplicity.
This is achieved by designing the user interface in a simple manner. There is not too much going on on each screen, and the purpose of each button is clear to the user.

3. Maintainability
The modular design of the application makes maintenance easier. One can make changes in the classes instead of having to deal with the UI interacting directly with the database.

4. Availability.
The application, if it were released in the real world, would be accessible to users 24/7.



Code Implementation Requirements
The code meets the "Code Implementation" requirements in the following manner:

UI Layout and Design: The layout and design are defined in
AddListing.fxml, HomePage.fxml, Login.fxml, RemoveListing.fxml, UserPage.fxml, Vehicle.fxml, VehicleProfile.fxml, and styled using style.css.
This allows for a clear separation between UI structure and appearance.

User Registration and Login: The UserPageController.java and LoginController.java class handles user registration and login functionalities. It connects to a MySQL database for user data storage which hosted online.

Database Connection: we hosted the database online. For the feature to view the database changes, we have:

- Host: carhubservice-carhub.a.aivencloud.com
- Port: 23563
- User: carhubuser
- Password: AVNS_LrzqoWReIY1UfSOroMi
- Database: carhub

The set up database is not required, only applied when you want to review the changes in carhub database.


Running the Application
To run the CAR-HUB application, follow these steps:

1. Ensure you have Java and JavaFX installed on your system. (Using SDK 19 or 21)

2. Database has been stored online, so there will no set up the database.

3. Build the project

4. Run the HelloApplication.java to start the Application.
    - Step 1: Sign Up
        Fill in the appropriate Name, Email, Phone number, Password
    - Step 2: Login
        Fill in the appropriate Email and Password
    - Step 3: Update user Information if needed
        Update User Information via Name, Email, Phone number, Password
    - Step 4: Add your listing
        Add Listing follows Make, Model, Year, Price, Drive Terrain, Exterior Color, Interior Color
    - Step 5: You can view your listings
        View your Listing in ViewListing.fxml
    - Step 6: You can check your listing in marketplace
        View your created listing in HomePage.fxml
    - Step 7: You can review your vehicle that has been posted in marketplace
        View your created listing in HomePage.fxml
    - Step 8: You can delete a listing when its profile
        Delete your listing in VehicleProfile.fxml
    - Step 9: You can filter listing by price, mileage, and year production
        Fill in text for price, milage, and year for searching listing
    - Step 10: After you are done, you can logout
        Logout button has been functioned every page in the UI
