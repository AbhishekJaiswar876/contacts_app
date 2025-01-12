1. Project setup instructions:
   Flutter SDK installed on your system (Download Flutter).
A Firebase account with a Firebase project set up (Firebase Console).
Code editor: Recommended VS Code or Android Studio.
Device or Emulator: Physical Android/iOS device or a simulator/emulator.(i'm using Physical android device Redmi 10 s)

-----------------------------------First Firebase setup-----------------------------
Open Firebase Console --Create a new Project --Project name set as Contacts-app -- accepts Firebase terms & Continue-- disable google analytics & create .
in cmd after selecting your located folder -flutter create contacts_app.
--install Firebase CLI for npm version--
run : npm install -g firebase-tools -- then firebase login --choose email account 
run this 2 commands in cmd--
dart pub global activate flutterfire_cli
flutterfire configure --project=contacts-app-f5702 // add packages and plugins 
--select platform // mine android only,
// Initialise Firebase app //
await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
);
------- in terminal for Project commands to run 
a.flutter pub add firebase_core  // test your app (when you are doing in real android device require a cable and setup developer option in device )
b. flutter pub add google_fonts 


---------------------------------------------------------------------------------
b. UI design for Login and setup 
1. Create a Folder name "views"
   1. login page , sign up(Register),home ,main, updateContact // files
      ( wihout registration user will not be able to do any things or proceed)
---------------------------------------------------------------------------------
------- in terminal for Project commands to run
 c.flutter pub add firebase_auth  // Email password Authentication 
 d.flutter pub add google_sign_in

 -------------------------------------------------------------------------------
 b. UI design for Login and Register setup and Create account With Firebase 
 Controller Folder contain 2 files 1.auth services and crud services 
 then validations for our Login email and password
 from firebase Authentication  setup for Google Sign in 
 ------------------------------------------------------------------------------
design contacts page making use of Drawer 
with personal mail and a logout option
setup for firebase database for storing users data and use same things for validations
-------------------------------------------------------------------------------
Google Authentication 
in firebase -- projects settings -- Add fingerprint ---// (Folder inside .android you will find adbkey )// -----open in cmd .android Folder -- // Run command-  
keytool -list -v -keystore debug.keystore -alis androiddebugkey // 

password as android ----- you will get SHA1 KEY ---- use this key for firebase .
design sign and signout function with Google account in (Authservices)
--------in terminal 

------------------------------------------------------------------------------
Create new Contacts in the firestore
 flutter pub add cloud_firetsore // in terminal

 design Crud Services for performing (CRUD Operation)adding contact, delete , insert , update etc.

 Create database 
 design addContact page (An Elevated button ) where you can add Contacts ---- change rules in cloud firestore----//if request.auth!=null// -- add contact data will be submitted in our database ----
 Read all Contacts from database (// getContacts in CRUD services ) -- setup HomePage 
 Updating an Existing Contact // Design an UpdateContact page 
 Delete an Existing Contact 
 Search Functionality in Contacts (Accourding to the names )

 Url Launcher (When you click on call a real dialpadnote appear with the same name and phone number )

 URL Launcher for device > then API 30 need to make changes in AndroidManifes.xmlt
 
 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------   
   
3. Features implemented:
   Core Features:
   Frontend: Flutter 
1.	User Authentication Screens: 
o	Login Screen:  
▪	Email and password fields with validation. 
o	Registration Screen:  
▪	Email, password, and confirm password fields with validation. 
▪	Display error messages for invalid inputs. 
o	Logout Option:  
▪	Allow users to log out from their account (e.g., via a menu or button). 
2.	Home Screen: 
o	Display a list of contacts specific to the logged-in user. o 	Floating Action Button (FAB) to add new contacts. 
o	Search bar to filter contacts by name.(Optional) 
3.	Contact Management: 
o	Add Contacts:  
▪	Form with fields: name, phone number, email, and optional profile picture. 
o	Edit Contacts:  
▪	Update existing contact details. o 	Delete Contacts:  
▪	Remove a contact permanently. 
4.	Contact Details Page: 
o	View detailed information for a selected contact. 
o	Edit or delete the contact from this page. 
-----------------------------------------------------------------------------------------------------------------
Backend: Firebase 
1.	Firebase Authentication: 
o	Enable email/password authentication. 
o	Store user credentials securely. 
2.	Firebase Firestore: 
o	Create a contacts collection with fields:  
▪	userId (to associate contacts with a specific user). 
▪	name, phoneNumber, email, and timestamp. 
o	Fetch only the logged-in user’s contacts. 
o	Perform CRUD (Create, Read, Update, Delete) operations on contacts.
sorting options (by name) 
---------------------------------------------------------------------------------------------------------------



User Authentication:
Sign-up and login functionality using Firebase Authentication.
Search Functionality in Contacts
 Url Launcher 

Email/password-based authentication.

Contacts Management:
Add new contacts: User can input and save contact details.

Edit existing contacts.
Delete contacts.

Real-time Data Sync:
Integration with Firestore to store and retrieve contact data.
Ensures real-time updates across multiple sessions/devices.

Search Functionality:
Allows searching through stored contacts by name or other details.

Responsive UI:
Designed for  mobile  




   


   
5. assumtions or challenges:
   Firebase services are configured correctly for the app to run without issues.
   designing API version 30+ require changes in file AndroidManifest.xml
   
   
