## React Native Geo Location Module
This projects serves the purpose of tracking geo location for android platform.

## Installing it as a library in your main project

1. Do `npm install --save git+https://github.com/sundermagar/ReactNativeGeoLocation.git` in your main project.
2. Link the library:
    * Add the following to `android/settings.gradle`:
        ```
        include ':react-native-geolocation'
        project(':react-native-geolocation').projectDir = new File(settingsDir, '../node_modules/react-native-geolocation/android')
        ```

    * Add the following to `android/app/build.gradle`:
        ```xml
        ...

        dependencies {
            ...
            compile project(':react-native-geolocation')
        }
        ```
    * Add the following to `android/app/src/main/java/**/MainApplication.java`:
        ```java
        package com.justget;

        import com.justget.geolocation.GeoLocationService;  // add this for react-native-geolocation

        public class MainApplication extends Application implements ReactApplication {

            @Override
            protected List<ReactPackage> getPackages() {
                return Arrays.<ReactPackage>asList(
                    new MainReactPackage(),
                    new GeoLocationService()     // add this for react-native-geolocation
                );
            }
        }
        ```
3. Simply `import/require` it by the name defined in your library's `package.json`:

    ```javascript
    import geolocation from 'react-native-geolocation'
    JustGetGeoLocation.show('JustGetGeoLocation runs fine', JustGetGeoLocation.LONG)
    ```
