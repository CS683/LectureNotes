# Advanced UI
## ListViews and AdapterViews
1. It is an adapter view. It is also a ViewGroup. 
2. Displays a vertically-scrollable collection of views, where each view is positioned immediatelybelow the previous view in the list.
3. An adapter view needs to bind with an adapter, ususally through the setAdapter() method.
4. The adapter bridges the adapter view with the data it assoicates with.
5. A ListView can only work with a ListAdapter. An ArrayAdapter is also a ListAdapter.
6. To display a constant string, we can use android:entries property of the adapter view, 
for example, when working with spinners and listviews.
7. If the data will change, you need to create an adapter in the Java code to bind the data. 
8. An adapter specifies the data collection it assoicates with and the view for each individual data item. 
The adapter view will specifies how to display these views (the relative positions of these views).
9. AdatperViews use the Observer pattern. They are observers and the associated data (or through adapter) are observable. When the associated data changes, you can call the notifyDataSetchanged() method of the adatper to update the adapterview.
## RecyclerViews
1. It is very similar to ListViews. However, it is NOT inherited from AdapterView. It is provided in the support library and 
now it is in the Androidx namespace (androidx.recyclerview.widget.RecyclerView).
2. To use a recyclerview, we need first to subclass RecyclerView.Adapter to create an adapter for the Recylcerview. 
The subclass needs to implement three abstract methods. It also needs to specify the associated data. 
3. Use the setAdapter() method of the RecyclerView to set its adapter.
##Communication between Activites
1. Activities are independent Android components. They communicate through intents. To start another activity, simply call startActivit().
2. An intent is a message object, that encapsulates both data and actions. You can also specify the receiving objects in the intent.
## Communciation between Fragments
1. Fragments are not independent Android components. They depend on activities that contain them. They cannot communicate with each other directly, but always through activity. 
2. In the activity class, it is easier to get the references to the fragment objects the activity contains, and thus it is easy to call any public methods defined in the Fragment and pass any parameters.
2. However, the fragment may not know what kind of activites that will contain it when it is first designed. While you can get the reference to the containing activity, you shall not call any public methods defined in that activity directly. Instead, you can define an interface first and let that activity class implement that interface. 
## Adaptive to different screen sizes
1. Use view dimensions that allow the layout to resize (constraint layout, weight in Linear layout, avoid hard code size, match_parent, wrap_ content for view size)
2. Create alternative UI layouts according to the screen configuration (create resource directory folders with different qualifier name: res/layout, res/layout-sw600dp, res/layout-land/, res/layout-w600dp, res/layout-large/ ...)
3. Provide bitmaps that can stretch with the views (nine patch)

https://developer.android.com/training/multiscreen/screensizes

## Pixel density
1. density-independent pixels (dp): 1 dp is about 1 px in a 160 dpi screen(~1/160 inch)
2. Pixel (px): # of pixel on the screen depends on the screen size and resolution
3. scalable pixels (sp): use for the text size 

px = dp * (dpi / 160)

https://developer.android.com/training/multiscreen/screendensities

