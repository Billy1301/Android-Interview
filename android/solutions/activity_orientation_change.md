## What happens on orientation change (screen rotation)?

The current Activity will be `destroyed` and then `re-created`.

Assuming the Activity is currently running and in `onResume()` state, it will go through the following in the listed order:
- `onPause()`
- `onStop()`
- `onDestroy()`
- `onCreate()`
- `onStart()`
- `onResume()`

Android restarts the running Activity (`onDestroy()` is called, followed by `onCreate()`). The restart behavior is designed to help your application [adapt to new configurations](https://developer.android.com/guide/topics/resources/runtime-changes.html) by automatically reloading your application with alternative resources that match the new device configuration.

![](https://developer.android.com/images/activity_lifecycle.png)
