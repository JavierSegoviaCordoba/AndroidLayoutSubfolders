# AndroidLayoutSubfolders
## Folders structure:

Rename the layout folder to layouts with Android Studio. Add your layouts
files to the subfolders. Now, take care about you have to use the folder
layout as container of any layout files. For example:

```bash
res
│
└──── layouts
      │
      └──── activities
            │
            ├──── main
            │     │
            │     │
            │     └──── layout
            │               activity_main.xml
            │
            └──── second
                  │
                  │
                  └──── layout
                            activity_second.xml

```

The xml files are inside of a layout folder.
Now you have to add this code inside "android" to the app build.gradle:

```gradle
android {

    ...

    sourceSets {
        main.res.srcDirs = [
                file('src/main/res'),
                file('src/main/res/layouts').listFiles(),
                file('src/main/res/layouts/activities').listFiles()
            ]

    }
}
```

We can use less code if we use `.listFiles()` because we don't need to
add the main and second folders.

You never have not to add the "layout" folders