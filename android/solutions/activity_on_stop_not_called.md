## Is there a situation where onStop() could not be called? 

Yes.

## What is the situation?

`onStop()` will not be called when:
- You call `finish()` inside of `onCreate()`.
- Memory pressures cause the os to kill your activity **and** your app runs on a platform **older** than [Honeycomb](https://developer.android.com/reference/android/os/Build.VERSION_CODES.html#HONEYCOMB). 

[Documentation](https://developer.android.com/reference/android/app/Activity.html) states that:
- Starting with Honeycomb, an [application is not in the killable state until its `onStop()` has returned](https://developer.android.com/reference/android/app/Activity.html).
- However, the table in the above link shows `onStop()` as having `Yes` for the `Killable` column, which implies that **post** Honeycomb, `onStop()` might still not be called. This directly contradicts what we just read above. **One of these cases is in the documentation wrong**, its up to your to dig through the source code and figure it out or be able to back up your answer!
