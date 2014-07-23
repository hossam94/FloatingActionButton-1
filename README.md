FloatingActionButton
====================

### Description

Android [Google+] like floating action button which reacts on the list view scrolling events. Becomes visible when the list view is scrolled up and invisible when scrolled down.

![Demo](art/demo.gif)

### Integration

1) Clone this repo, copy it to your Gradle project and add as a dependency to your ``build.gradle``:

```groovy
dependencies {
    ...
    compile project(':FloatingActionButton:library')
}
```

2) Add the ``com.melnykov.fab.FloatingActionButton`` to your layout XML file. The button should be placed in the bottom right corner of the screen. The width and height of the floating action button are hardcoded to ``56dp`` as specified in the [guidlines].

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
             xmlns:fab="http://schemas.android.com/apk/res-auto"
             android:layout_width="match_parent"
             android:layout_height="match_parent">

    <ListView
            android:id="@android:id/list"
            android:layout_width="match_parent"
            android:layout_height="match_parent"/>

    <com.melnykov.fab.FloatingActionButton
            android:id="@+id/button_floating_action"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="bottom|right"
            android:layout_margin="32dp"
            android:src="@drawable/ic_action_content_new"
            fab:colorNormal="@android:color/holo_red_dark"
            fab:colorPressed="@android:color/holo_red_light"/>
</FrameLayout>
```


3) Attach the list view to the button in the Java code:

```java
ListView listView = (ListView) findViewById(android.R.id.list);
FloatingActionButton floatingActionButton = (FloatingActionButton) findViewById(R.id.button_floating_action);
floatingActionButton.attachToListView(listView);
```

4) Add the namespace ``xmlns:fab="http://schemas.android.com/apk/res-auto"`` to your layout file and set the normal and pressed colors via xml attributes:

```xml
fab:colorNormal="@android:color/holo_red_dark"
fab:colorPressed="@android:color/holo_red_light"
```

5) Set an icon for the ``FloatingActionButton`` using ``android:src`` xml attribute. Use drawables of size ``24dp`` as specified by the [guidlines]. Icons of desired size can be generated with [Android Asset Studio].


[Google+]:https://play.google.com/store/apps/details?id=com.google.android.apps.plus
[guidlines]:http://www.google.com/design/spec/patterns/promoted-actions.html#promoted-actions-floating-action-button
[Android Asset Studio]:http://romannurik.github.io/AndroidAssetStudio/icons-generic.html
