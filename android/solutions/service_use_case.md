## I needed to do something outside of the activity lifecycle. It needs to run across multiple activities. How would I do that?

Use a [Service](https://developer.android.com/guide/components/services.html).

A `Service` is an application component that can perform long-running operations in the **background** and does not provide a user interface. Another [application component](https://developer.android.com/guide/components/fundamentals.html) can start a `service` and it will continue to run in the background even if the user switches to another application. Additionally, a component can bind to a `service` to interact with it and even perform interprocess communication (IPC). For example, a service might handle network transactions, play music, perform file I/O, or interact with a content provider, all from the background.

**Note:** Application components are defined as:
- `Activities`
- `Services`
- `Content Providers`
- `Broadcast Receivers`

Read more about [application components](https://developer.android.com/guide/components/fundamentals.html).
