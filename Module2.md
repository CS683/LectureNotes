# Module 2 Basic UIs
## Activities
1. An activity is an android UI component
2. It need to be declared in the AndroidManifest.xml file
3. To create an activity, we need to define a Java/kotlin class (define interaction, control) and a xml layout (defines its look, view)
4. There are several callback functions defined in the Activity class. These callback functions define the lifecycle of the activity. 
5. Understand the differences between foreground and background, visible and invisible. Understand how the callback functions are called when open an app, close an  app, switch between apps, press the home button, the back button, or the overview button.
6. An Activity with the intent filter to receive action MAIN intent will start first. This is defined in the manfiest file.

## Views and Viewgroups
1. View is the base class for all UI widgets. A simple widget like textview is a view. 
2. A viewgroup is also a view. 
3. Composite pattern is used here.
4. Clearly understand several class diagrams in the Module 2 lecture notes on blackboard. 

## Layout
1. The Layout classes inherit from Viewgroup, so a layout is a viewgroup. It is also a view.
2. There are several different layouts provided by android. Commonly used are linear layout, frame layout, constraint layout and coordinator layout.
3. ConstraintLayout is different in android support library. For all view components defined in the constraint layout, we need to specify at least two constraints, one is horizontal constraint, the other is vertical constraint. Without specify any constraint, the view widget will be placed on the top left corner. 
4. The views in the LinearLayout can be positioned either horitonzally in a column or vertically in a row. 
5. FrameLayout is usually used to hold a single child view. If there are multiple children views, they are drawn in a stack, with the most recently added child on top.


## Event Handling
1. defined in the java class
2. bind eventlistener to a view object using the set method,e.g. setOnclickListener
3. Each listener defines a single call back method
4. OnClick can be also specified in the layout xml file through android:onclick
5. Also have other event handler call back

## Fragments
1. Framgements are similar to activities, in the way that a fragment is usually defined by a java/kotlin class and a layout xml file.
2. Fragments are different from activites. A fragment is NOT a standalone component, and is NOT declared in the manifest file, and has to be contained in some activity.
3. A activity can contain multiple fragments. A fragment can be reused in different activities (The same fragment class can be used in different activities). 
4. Fragments can be added in the activity statically in the layout file, or dynamically added/removed/replaced in the java/kotlin code using fragment manager and fragment transaction. 
5. In the activity, it is easy to get the fragment object reference and call its public methods, in order to communicate with the fragments it contains. If the fragment is defined statically in the layout file, we need to use first get the fragment manager by calling getSupportFragmentManager(), then call findFragmentById() to get the object reference based on its Id defined in the layout xml file.

## androidx namespace
It replaces all support libraries. You can migrate the project using the support library to androix by clicking the menu item Refactor/Migrate to Androidx... Also make sure that the gradle.properties file has the following setting 
```
android.useAndroidX=true
# Automatically convert third-party libraries to use AndroidX
android.enableJetifier=true
```

