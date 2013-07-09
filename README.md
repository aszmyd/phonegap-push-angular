AngularJS PhoneGap Push Notifications Service
=============================================

Allows using the [PushPlugin](https://github.com/bobeast/PushPlugin) in [PhoneGap](http://phonegap.com/) apps built with AngularJS.

Provides a service for registering the device with the push notification server and listening for notifications.

Example
-------

Register device:

```javascript
new pgPushNotificationsFactory(
  '0123456789', // GCM Sender ID
  function registeredCallback (deviceToken, platform) {
    // Send `deviceToken` to your push server here
    // `platform` is either 'APNS' (iOS) or 'GCM' (Android)
  },
  function pushNotificationCallback (data, platform) {
     // Push message received
  }
);
```

Listen for push notifications:

```javascript
$scope.$on('phonegapPush.notification', function (notification) {
  // Notification received:
  // `notification.data` raw notification data/payload
  // `notification.provider` either 'APNS' or 'GCM'
});
```