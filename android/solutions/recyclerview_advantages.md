## What is a RecyclerView? What are some advantages of RecyclerView over alternatives like ListView?

[Android developer](https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html) reference

A RecyclerView is a more advanced, flexible, and capable version of ListView. It is a container for displaying large data sets that can be scrolled very efficiently by maintaining a limited number of views.

Here are some of it's differences/advantages:

* ViewHolder Pattern: RecyclerView requires a ViewHolder pattern, while it is just a recommendation for ListView. 

* LayoutManager: Unlike only having ListView available, RecyclerView can also utilize other options (such as GridLayoutManager, and LinearLayoutManager). 

* More control/power with OnItemClickListener.

* Better item animations

* Better item decorations with ItemDecorator class.

A disadvantage could be that it is more complex than a ListView.


Additional Resource:

[SO post](http://stackoverflow.com/questions/26570325/what-are-recyclerview-advantages-compared-to-listview) on the subject.
