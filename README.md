# Room
Room is an ORM, Object Relational Mapping library. In other words, Room will map our database objects to Java objects. Room provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.

## SQLite vs Room
* In case of SQLite, There is no compile time verification of raw SQLite queries. But in Room there is SQL validation at compile time.
* As your schema changes, you need to update the affected SQL queries manually. Room solves this problem.
* You need to use lots of boilerplate code to convert between SQL queries and Java data objects. But, Room maps our database objects to Java Object without boilerplate code.
* Room is built to work with LiveData and RxJava for data observation, while SQLite does not.

## Main Annotations
* `@Entity` — Define our database tables
* `@DAO` — Provide an API for reading and writing data
* `@Database` — Represent a database holder

## Plugin Needed
```
// Annotation Processor
apply plugin: 'kotlin-kapt'
```

## Packaging Option Needed
```
// Exclude the atomic functions module from the package and prevent warnings
android {
  ...
  ...
  packagingOptions {
    exclude 'META-INF/atomicfu.kotlin_module'
  }
}
```

## Dependencies Needed
```
// Room components
implementation "androidx.room:room-runtime:$rootProject.roomVersion"
kapt "androidx.room:room-compiler:$rootProject.roomVersion"
implementation "androidx.room:room-ktx:$rootProject.roomVersion"
androidTestImplementation "androidx.room:room-testing:$rootProject.roomVersion"

// Lifecycle components
implementation "androidx.lifecycle:lifecycle-extensions:$rootProject.archLifecycleVersion"
kapt "androidx.lifecycle:lifecycle-compiler:$rootProject.archLifecycleVersion"
implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$rootProject.archLifecycleVersion"


// Kotlin components
implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
api "org.jetbrains.kotlinx:kotlinx-coroutines-core:$rootProject.coroutines"
api "org.jetbrains.kotlinx:kotlinx-coroutines-android:$rootProject.coroutines"

// Material design
implementation "com.google.android.material:material:$rootProject.materialVersion"

// Testing
testImplementation 'junit:junit:4.12'
androidTestImplementation "androidx.arch.core:core-testing:$rootProject.coreTestingVersion"
```


## App Demo
<img src="https://i.gyazo.com/5c5e93477b8d6beaec956cbe70ea69d9.gif" width="350px" height="650px" />
