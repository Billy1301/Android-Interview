## In what lifecycle method would I clean up any significant resources (Thread, Bitmaps, etc.) in my Activity?

Cleanup of significant resources should happen in the `onStop()` method.

Once your activity is stopped, the system might destroy the instance if it needs to recover system memory. In extreme cases, the system might simply kill your app process without calling the activity's final `onDestroy()` callback, so it's important you use `onStop()` to **release resources that might leak memory**.

Read more:
- [Releasing resources](https://developer.android.com/training/basics/activity-lifecycle/stopping.html)
- [When is onStop() called](solutions/activity_on_stop.md)
