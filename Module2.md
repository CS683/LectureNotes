# Module 2 Basic UIs
## Activities
1. an android UI component
2. need to be declared in the AndroidManifest.xml file
3. Define a Java class (define interaction, control) & a xml layout (defines look , view)
4. Callback functions in the activity class, lifecycle
5. foreground vs background, visible vs invisible, open the app, close the app, switch between apps, press home button, back button, overview button
6. activity with the intent filter to receive action.MAIN intent will start first. This is defined in the manfiest file.

## Views and Viewgroups
1. View is the base class for all UI widgets. A simple widget like textview is a view. 
2. A viewgroup is also a view. 
3. Composite pattern is used here

## Event Handling
1. defined in the java class
2. bind eventlistener to a view object using the set method,e.g. setOnclickListener
3. Each listener defines a single call back method
4. OnClick can be also specified in the layout xml file through android:onclick
5. Also have other event handler call back

## Fragments
1. Similar to activities, a fragment is usually defined by a java class and a layout xml file
2. Different from activites, a fragment is NOT a standalone component, and is NOT declared in the manifest file, and has to be contained in some activity.
3. A activity can contain multiple fragments. A fragment class (different instances of the same fragment class) can be reused in different activities. 
4. Fragments can be added in the activity statically in the layout file, or dynamically added/removed/replaced in the java code using fragment manager and fragment transaction
5. In the activity, it is easy to get the fragment object reference and call its public methods , in order to communicate with the fragments it contains. 

## androidx namespace
It replaces all support libraries. You can migrate the project using the support library to androix by clicking the menu item Refactor/Migrate to Androidx... Also make sure that the gradle.properties file has the following setting 
```
android.useAndroidX=true
# Automatically convert third-party libraries to use AndroidX
android.enableJetifier=true
```

## Project
1. Model classes
2. Simple UI(s)
