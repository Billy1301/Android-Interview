## When is onPause() called?

`onPause()` is called when the activity is still **partially visible** but currently not the activity in focus.

For example:
- A semi-transparent activity opens (such as one in the style of a dialog)
- User receives a system notification in the form of a popup that overlays your activity
- User pulls down on the notification bar at the top of the phone and is viewing the notifications

Read more about [paused activities](https://developer.android.com/training/basics/activity-lifecycle/pausing.html).

![](https://developer.android.com/images/training/basics/basic-lifecycle-paused.png)
