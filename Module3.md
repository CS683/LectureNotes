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
