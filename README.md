# CarHub Application
Welcome to CarHub. It can be daunting when trying to sell a vehicle, especially if one does not want to trade it in or sell it to a used car lot for less than its real value.
Searching for a vehicle, driving from used car lot to used car lot, and dealing with all sorts of salespeople can be equally taxing.

CarHub attempts to solve this problem with an easy-to-use application in which sellers can list their vehicles and buyers can browse those listings.
The listings include relevant information about the vehicle and the seller's contact information, so they can then get in contact with each other directly,
and the sale of the vehicle can be conducted on their own terms.
Sellers can get their vehicles in front of potential buyers, and buyers can avoid the used car lot grind.

Created using Java, JavaFX/FXML/CSS, and MySQL.

## Requirements
- Gradle
- MySQL Server/Workbench

## Code Structure
The application is structured in a modular manner, ensuring a separation of concerns:

### Main classes
- [HelloApplication.java](src/main/java/carshop/carshop/HelloApplication.java): Application launcher class.
- [Navigation.java](src/main/java/carshop/carshop/Navigation.java): Navigation class to open new pages.
- [Car.java](src/main/java/carshop/carshop/Car.java): Abstract class representing cars.
- [Listing.java](src/main/java/carshop/carshop/Listing.java): Class representing a listing's contents.
- [ListingData.java](src/main/java/carshop/carshop/ListingData.java): List of listings used to populate pages.
- [ListingDatabase.java](src/main/java/carshop/carshop/ListingDatabase.java): Class that retrieves listing information from the database.
- [SelectedListing.java](src/main/java/carshop/carshop/SelectedListing.java): Class that retrieves information from a selected listing.
- [User.java](src/main/java/carshop/carshop/User.java): Class that represents a user's information.
- [UserData.java](src/main/java/carshop/carshop/UserData.java): Class representing a list of users.
- [UserSession.java](src/main/java/carshop/carshop/UserSession.java): Singleton class to track the currently logged in user.
- [UserDatabase.java](src/main/java/carshop/carshop/UserDatabase.java): Class that retrieves user information from the database.
- [Dialog_Box.java](src/main/java/carshop/carshop/Dialog_Box.java): Class for raising alerts and notifications.
- [Dialog_Interface.java](src/main/java/carshop/carshop/Dialog_Interface.java): Interface to implement Dialog_Box.java
- [DatabaseCredentials.java](src/main/java/carshop/carshop/DatabaseCredentials.java): Interface containing database access information.
 
### FXML Pages/Controller Classes
- [Login.fxml](src/main/resources/carshop/carshop/Login.fxml): Login page that opens on startup. Allows users to register an account, or log into the application if they already have an account. Controlled by [LoginController.java](src/main/java/carshop/carshop/LoginController.java).
- [HomePage.fxml](src/main/resources/carshop/carshop/HomePage.fxml): Primary page of the application where users can view/filter listings. Controlled by [HomePageController.java](src/main/java/carshop/carshop/HomePageController.java).
- [UserPage.fxml](src/main/resources/carshop/carshop/UserPage.fxml): Page that allows users to upload a profile picture and/or update profile information. Controlled by [UserPageController.java](src/main/java/carshop/carshop/UserPageController.java).
- [AddListing.fxml](src/main/resources/carshop/carshop/AddListing.fxml): Page for users to create a new listing by selecting card parameters and uploading an image. Controlled by [AddListingController.java](src/main/java/carshop/carshop/AddListingController.java).
- [RemoveListing.fxml](src/main/resources/carshop/carshop/RemoveListing.fxml): Page for users to view/remove their own active listings. Controlled by [RemoveListingController.java](src/main/java/carshop/carshop/RemoveListingController.java).
- [Vehicle.fxml](src/main/resources/carshop/carshop/Vehicle.fxml): "Thumbnail" for listings that displays the car make, model, drive train, and image. Controlled by [VehicleController.java](src/main/java/carshop/carshop/VehicleController.java).
- [VehicleProfile.fxml](src/main/resources/carshop/carshop/VehicleProfile.fxml): Full page that displays listing information, including the car make, model, year, mileage, interior/exterior color, drive train, contact information, and image. Controlled by [VehicleProfileController.java](src/main/java/carshop/carshop/VehicleProfileController.java).

## Database Setup
1. Using MySQL Workbench, connect to the host where you would like to host the database for the application. Make note of the host name, login username, and password, as that information will be used to run the application .
2. Open [CarHub_DB_Schema.sql](CarHub_DB_Schema.sql) in MySQL Workbench, and run the script.
3. Open [DatabaseCredentials.java](src/main/java/carshop/carshop/DatabaseCredentials.java) in your text editor of choice.
4. Set the `JDBC_URL`, `USER`, and `PASSWORD` variables to the host name, username, and password recorded in the previous step.

## Running the Application
1. In the [main project directory](/), compile the application. The command format is:
    ```
    ./gradlew build
    ```
2. Run the application. The command format is:
    ```
    ./gradlew run
    ```

## Navigating CarHub
### Sign In
- If you have a registered account, enter your login information on the left and click `Sign In`.
- Otherwise, if you do not have a registered account, enter your personal details on the right and click `Sign Up`.
- In either case, you will be logged in and taken to the [Main Page](###main-menu).
### Main Page
- On this page, you can view and filter car listings by `Price`, `Year` and `Mileage`.
- Clicking a listing thumbnail opens a new [Page](###Listing-Page) for that listing.
- If you are logged in, you can also click your name in the top right corner to navigate to your [User Profile](###User-Profile).
### User Profile
- On this page, you can update your name, email address, phone number, password, and profile photo.
- Clicking `Add Listing` on the left will take you to the [Add Listing](###Add-Listing) page.
- Clicking `View/Remove Listing` on the left will take you to [Your Listings](###Your-Listings).
- You can also click `Sign Out` in the bottom left to log out.
### Add Listing
- On this page, you can select your vehicle's `Make`, `Model`, `Year`, `Price`, `Drive Train`, and `Interior`/`Exterior Color`.
- You can also upload a photo of your vehicle for the listing.
### Your Listings
- On this page, you can view the thumbnails for all of your active listings.
- Clicking a listing thumbnail opens a new [Page](###Listing-Page) for that listing.
### Listing Page
- On this page, you can see a picture of the vehicle in the listing, as well as the vehicle's `Make`, `Model`, `Year`, `Price`, `Drive Train`, and `Interior`/`Exterior color`.
- On the right, you can see the `Contact Information` of the seller.
- If you are the owner of the car in the listing, you will see a button titled `Delete Listing` that will remove your listing from the database.
