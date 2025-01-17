To **handle expired or invalid Firebase tokens on the server-side**, you need to check the response from Firebase when sending push notifications. Firebase will return specific error codes when a token is no longer valid.

### **Common Firebase Error Codes for Invalid Tokens**

- **`NotRegistered`**: The token is invalid (user uninstalled the app, token expired).
- **`InvalidRegistration`**: The token format is invalid.
- **`MismatchSenderId`**: The token was generated with a different sender ID.

### **Implementation Example**

If you're using **HTTP v1 API** or **Firebase Admin SDK**, here's how to handle token errors:

---

#### **1. Using Firebase Admin SDK (Kotlin/Java Backend)**

```kotlin
val message = Message.builder()
    .setToken(deviceToken)
    .putData("title", "Hello!")
    .putData("body", "This is a notification.")
    .build()

try {
    FirebaseMessaging.getInstance().send(message)
} catch (e: FirebaseMessagingException) {
    when (e.errorCode) {
        "NOT_FOUND", "UNREGISTERED", "INVALID_ARGUMENT" -> {
            // Token is invalid or expired
            removeTokenFromDatabase(deviceToken)
        }
        else -> {
            // Handle other errors (e.g., network issues)
            println("Error sending message: ${e.message}")
        }
    }
}
```

---

#### **2. Using HTTP v1 API**

When using REST APIs to send notifications, check the response for `"error": "NotRegistered"`.

##### **Example Response (Invalid Token):**

```json
{
  "error": {
    "code": 404,
    "message": "Requested entity was not found.",
    "status": "NOT_FOUND",
    "details": [
      {
        "@type": "type.googleapis.com/google.firebase.fcm.v1.FcmError",
        "errorCode": "UNREGISTERED"
      }
    ]
  }
}
```

##### **Backend Handling Example (Node.js):**

```javascript
const admin = require("firebase-admin");

const message = {
  token: deviceToken,
  notification: {
    title: "Hello!",
    body: "This is a test notification"
  }
};

admin.messaging().send(message)
  .then(response => {
    console.log("Successfully sent message:", response);
  })
  .catch(error => {
    if (error.errorInfo.code === 'messaging/registration-token-not-registered') {
      // Remove invalid token from the database
      removeTokenFromDatabase(deviceToken);
    } else {
      console.error("Error sending message:", error);
    }
  });
```

---

### **Action Plan for Invalid Tokens**
1. **Detect Error:** Check for `"NotRegistered"`, `"InvalidRegistration"`, or `"Unregistered"` errors.  
2. **Remove Token:** Delete the invalid token from your database to avoid retrying.  
3. **Retry for Other Errors:** For temporary errors, implement a retry mechanism.

This ensures your server keeps a clean and valid list of tokens, reducing unnecessary push notification failures.
