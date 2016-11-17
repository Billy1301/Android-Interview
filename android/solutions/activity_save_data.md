## When should we save data from our Activity?

`onPause()` is used to save any information in case the user continues to leave your app.

For example:
- When `onPause()` is called, you don't know if your user is just looking at the nofications and your activity is still **partially visible** or if user has left the activity and is looking at a **different app** ( `onStop()` was called ).

Generally, you should not use `onPause()` to store user changes (such as personal information entered into a form) to permanent storage. The only time you should persist user changes to permanent storage within `onPause()` is when you're certain users expect the changes to be auto-saved (such as when drafting an email).

You should keep the amount of operations done in the `onPause()` method relatively simple in order to allow for a speedy transition to the user's next destination if your activity is actually being stopped.

Although the `onPause()` method is called before `onStop()`, you should use `onStop()` to **perform larger, more CPU intensive shut-down operations**, such as writing information to a database.

Read more:
- [Pausing an Activity](https://developer.android.com/training/basics/activity-lifecycle/pausing.html)
- [Stopping an Activity](https://developer.android.com/training/basics/activity-lifecycle/stopping.html)
