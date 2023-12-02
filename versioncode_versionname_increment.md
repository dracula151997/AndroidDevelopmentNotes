You can automate the incrementation of `versionCode` and `versionName` in your Android project by using Gradle. Here's a simple way to do it:

1. Create a `version.properties` file in the root directory of your project. This file will store your `versionCode` and `versionName`.

2. In your `version.properties` file, add the following lines:

```properties
VERSION_CODE=1
VERSION_NAME=1.0.0
```

3. In your `build.gradle` file, add a function to read the `version.properties` file and increment the `versionCode` and `versionName`.

Here's the code you can add to your `build.gradle` file:

```groovy
def versionCodeInc() {
    def versionPropsFile = file('version.properties')
    if (versionPropsFile.canRead()) {
        Properties versionProps = new Properties()

        versionProps.load(new FileInputStream(versionPropsFile))

        def versionCode = versionProps['VERSION_CODE'].toInteger()
        if (getGradle().getStartParameter().getTaskRequests().toString().contains("Release")) {
            versionCode += 1
            versionProps['VERSION_CODE'] = versionCode.toString()
            versionProps.store(versionPropsFile.newWriter(), null)
        }

        return versionCode
    } else {
        throw new GradleException("Could not read version.properties!")
    }
}

def versionNameInc() {
    def versionPropsFile = file('version.properties')
    if (versionPropsFile.canRead()) {
        Properties versionProps = new Properties()

        versionProps.load(new FileInputStream(versionPropsFile))

        def versionName = versionProps['VERSION_NAME']
        if (getGradle().getStartParameter().getTaskRequests().toString().contains("Release")) {
            def (major, minor, patch) = versionName.tokenize('.')
            patch = patch.toInteger() + 1
            versionName = major + "." + minor + "." + patch
            versionProps['VERSION_NAME'] = versionName
            versionProps.store(versionPropsFile.newWriter(), null)
        }

        return versionName
    } else {
        throw new GradleException("Could not read version.properties!")
    }
}

android {
    defaultConfig {
        versionCode getVersionCode()
        versionName getVersionName()
        // ...
    }
    // ...
}
```

This code will increment the `versionCode` by 1 and the `patch` part of the `versionName` by 1 every time you build your project. If you want to increment the `major` or `minor` part of the `versionName`, you will need to do it manually in the `version.properties` file.
