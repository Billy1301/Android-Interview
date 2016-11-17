## When is onStop() called?

`onStop()` is called when the activity is **no longer visible**. 

For example:
- The user opens the Recent Apps window and switches from your app to another app. The activity in your app that's currently in the foreground is stopped. If the user returns to your app from the Home screen launcher icon or the Recent Apps window, the activity restarts.
- The user performs an action in your app that starts a new activity. The current activity is stopped when the second activity is created. If the user then presses the Back button, the first activity is restarted.
- The user receives a phone call while using your app on his or her phone.

Read more about [stopped activites](https://developer.android.com/training/basics/activity-lifecycle/stopping.html).

**Note:** `onStop()` should release almost all resources that aren't needed. Once your activity is stopped, the system might destroy the instance if it needs to recover system memory. In extreme cases, the system might simply kill your app process without calling the activity's final `onDestroy()` callback, so it's important you use `onStop()` to **release resources that might leak memory**.


![](https://developer.android.com/images/training/basics/basic-lifecycle-stopped.png)
