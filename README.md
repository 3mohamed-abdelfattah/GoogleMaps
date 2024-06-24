
# Google Maps Integration in Android

This guide provides step-by-step instructions to integrate Google Maps into your Android application using Kotlin.

<img src="https://github.com/3mohamed-abdelfattah/GoogleMaps/assets/142848460/e8f7573d-585b-458f-9ffa-a4f3797cc37c" alt="image" width="300"/>

## Prerequisites

- Android Studio installed
- A Google Cloud Platform (GCP) project with the Maps SDK for Android enabled
- An API key for Google Maps

## Getting Started

### 1. Create a Google Cloud Project

1. Go to the [Google Cloud Console](https://cloud.google.com/).
2. Click on the project drop-down and select or create the project you want to use for Google Maps.
3. Enable the Maps SDK for Android from the API Library.

### 2. Get an API Key

1. In the Cloud Console, go to the [Credentials](https://console.cloud.google.com/apis/credentials) page.
2. Click `Create credentials` and then `API key`.
3. Restrict the API key to Android apps by specifying your application's package name and SHA-1 certificate fingerprint.

### 3. Add the API Key to Your Project

1. Open your project's `AndroidManifest.xml` file.
2. Add the following inside the `<application>` tag:

```xml
<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_API_KEY"/>
```

### 4. Update Gradle Files
In your project-level build.gradle file, include the Google services classpath:

```xml
buildscript {
    repositories {
        google()
    }
    dependencies {
        classpath 'com.google.gms:google-services:4.3.10' // Check for latest version
    }
}
```

In your app-level build.gradle file, apply the Google services plugin and add the Maps SDK dependency:

```xml
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services'

dependencies {
    implementation 'com.google.android.gms:play-services-maps:18.0.0' // Check for latest version
}
```

## Additional Resources
- [Google Maps SDK for Android Documentation](https://developers.google.com/maps/documentation/android-sdk/config?hl=en#kotlin)
- [Google Cloud Platform](https://cloud.google.com)

