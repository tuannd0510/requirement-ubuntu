## ARCore API key
- Enable Service: [link][arcoreService]
```
<application
  ...
  <meta-data
    android:name="com.google.android.ar.API_KEY"
    android:value="keyyyyy"/>
  ...
>
```

## 
```
# grandle.properties
dependencies {
...
    implementation 'com.google.android.gms:play-services-location:19.0.1'
    implementation 'com.google.android.gms:play-services-auth:20.3.0'
...
```

[arcoreService]: https://console.cloud.google.com/apis/library/arcorecloudanchor.googleapis.com?project=arcore1-363303
