To automate the use of a keystore in your Android project, you can specify the keystore details in your `build.gradle` file. This way, every time you build your project, Gradle will automatically sign your APK with the specified keystore.

Here's how you can do it:

1. First, make sure your keystore file is in a secure and accessible location.

2. In your `build.gradle` file, you can add the signing configurations inside the `android` block.

Here's an example of how you can do it:

```groovy
android {
    signingConfigs {
        release {
            storeFile file("path_to_your_keystore_file")
            storePassword "your_keystore_password"
            keyAlias "your_key_alias"
            keyPassword "your_key_password"
        }
    }

    buildTypes {
        release {
            signingConfig signingConfigs.release
            // other configurations for the release build type
        }
    }
    // ...
}
```

Replace `"path_to_your_keystore_file"`, `"your_keystore_password"`, `"your_key_alias"`, and `"your_key_password"` with your actual keystore details.

3. Change the build variant to Release (Build -> Select Build Variant)
4. Build the new release APK (Build -> Build Bundle(s) / APK(s) -> Build APK / Build Bundle)

> You can use `./gradlew assembleRelease` gradle task to automate the process of changing the build variant to Release and building a new release.

Please note that storing sensitive information like passwords in your `build.gradle` file is not recommended for security reasons. You should consider storing them in a secure and encrypted way or using environment variables.

Also, remember not to commit sensitive information to your version control system.

## Using Environment Variable (Windows 11)
1. Set the environment variable for `your_keystore_password`, `your_key_alias`, and `your_key_password`
   Open Command Prompt and write this command line `setx your_keystore_password_key "keystore_password"` and so on. Then restart the Android Studio.
2. Access the envionrment variable from build.gradle
   ```
       signingConfigs {
        release {
            storeFile rootProject.file("keysotre_file")
            storePassword System.getenv("keystore_password")
            keyPassword System.getenv("keystore_password")
            keyAlias System.getenv("keystore_alias")
        }
    }
   ```
   
   
