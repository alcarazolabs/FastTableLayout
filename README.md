# FastTableLayout <img src="https://jitpack.io/v/alcarazolabs/FastTableLayout.svg">
A library to build in a faster way a table layout in Android.
### Gradle Setup

```gradle
repositories {
    maven { url 'https://jitpack.io' }
}

dependencies {
    implementation 'com.github.alcarazolabs:FastTableLayout:1.0.0'
}
```
### Example

Add a table layout in your xml layout

```xml
<TableLayout
        android:id="@+id/myTableLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
```

MainActivity class - Example 1:

```kotlin
 val headers = arrayOf("ID","Names","Age")
 val data =  arrayOf(arrayOf("123","Freddy Alcarazo","27"),
             arrayOf("124","William Madrid","45"),
             arrayOf("125","Antonio Ibanez", "38"))
 
  val fastTable = FastTableLayout(this,
                                        binding.myTableLayout,
                                        headers,
                                        data)
  fastTable.build()
```

MainActivity class - Example 2:

```kotlin
 val headers = arrayOf("ID","Names","Age")
 var data = Array<Array<String>>(2) { arrayOf()}
     data[0] = arrayOf("123","Freddy Alcarazo","27")
     data[1] = arrayOf("124","William Madrid","45")
 
  val fastTable = FastTableLayout(this,
                                        binding.myTableLayout,
                                        headers,
                                        data)
  fastTable.build()
```

# Attributes

There three attributes you can set:

| attr | description |
|:---|:---|
| SET_DEAFULT_HEADER_BORDER | If set to true, a border will be added to each header, default false (color black and default shape is rectangle) |
| SET_DEFAULT_HEADER_BACKGROUND | If set to true, a background color will be added to the header row, default false (color gray) |
| TABLE_TEXT_SIZE | default value is 14f, increase or decrease this value will affect the text size of all table |

# Methods

There are two methods you can set:

| method | description |
|:---|:---|
| setCustomBackgroundToHeaders(color: Int) | You can pass a custom background color for the headers |
| setCustomBorderToHeaders(drawable: Int) | You can pass a custom shape drawable for the border of the headers |
