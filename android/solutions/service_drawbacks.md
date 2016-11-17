## What are some of the drawbacks or limitations of using a Service? 

While Services run in the background, they still run on the **main UI thread**.

## How would I get around them?

You can use:
- `Thread` and `Runnable` inside of the service.
- `AsyncTask` inside of the service.
- `Intent Service`, which offloads the work onto a separate thread.
- Start your service in a separate `process` ( i.e. one that is different from your application process ).

Read more:
- [Using Threads/AsyncTask](https://developer.android.com/guide/components/processes-and-threads.html)
- [Thread class](https://developer.android.com/reference/java/lang/Thread.html)
- [AsyncTask](https://developer.android.com/reference/android/os/AsyncTask.html)
- [IntentService](https://developer.android.com/training/run-background-service/create-service.html)
