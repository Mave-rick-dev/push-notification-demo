# push-notification-demo
Push notification with Spring boot and Firebase


#Firebase push notifications: Spring-boot config
The project demonstrates how to configure a spring-boot application as a middleware to 
  deliver client(Android, IOS, web) FCM token to Firebase for triggering push notification.

#Steps
1. Create firebase account and project

2. Configure firebase project for Spring-boot 
	- Project Settings --> Service a/c 
		- Set Admin SDK configuration snippet to Java
		- Generate new Primary key (.json)
			- move into Project resources folder

3. Create spring-boot project with dependency
	- firebase-admin

4. Add application property to identify the firebase config file (new Primary key)
	- app.firebase-configuration-file=primary-key-name.json


5. Create model for Request and Response data

6. Create three services:
	- one for initializing FCM (Firebase Cloud Messaging) service
	- second for exception handling for push notification
	- third for sending data to firebase to trigger push notification

7. Create FCM controller for sending push-notification-request


#Note: 
Token below is client(android, iso, web) specific FCM token 

Request:

{
    "title":"Test Notification",
    "message":"The notification has been sent",
    "topic":"Update notification",
    "token":"f33ecgFFQvGnqqzTT67MFE:APA91bGZbyBlcpXnfc5aNUTtMgqBPgEbIhiCs3NKrYB9e0vADNlrpqLODTHYXK3pxaZtEhfYSU7-hIYjgPLIRaASOw4xKLAhlPBZNbyQfEDBXrDCj2LPBf7ITkJkEDXxa74xCkGzYBNJ"
}


Response:

{
    "status": 200,
    "message": "Notification has been sent."
}




