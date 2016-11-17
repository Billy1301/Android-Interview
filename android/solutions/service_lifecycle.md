## What do you know about service Lifecycle?

There are two types of `Services`.
- `Started Services`
- `Bound Services`

![](https://developer.android.com/images/service_lifecycle.png)


The entire lifetime of a service happens between the time `onCreate()` is called and the time `onDestroy()` returns. Like an activity, a service does its initial setup in `onCreate()` and releases all remaining resources in `onDestroy()`. For example, a music playback service could create the thread where the music will be played in `onCreate()`, then stop the thread in `onDestroy()`.

#### Started Service Lifecycle

When a call to `startService()` is made, the service will go through the following methods in its **life time** ( from creation to destruction ):
- `onCreate()`
- `onStartCommand()`
- `onDestroy()`

#### Bound Service Lifecycle

When a call to `bindService()` is made, the service will go through the following methods in its **life time** ( from creation to destruction ):
- `onCreate()`
- `onBind()`
- `onUnbind()`
- `onDestroy()`


#### Things to remember:

The `onCreate()` and `onDestroy()` methods are called for all services, whether they're created by `startService()` or `bindService()`.
- `onCreate()` is called only once, the first time `startService()` or `bindService()` is called.
- `startService()` is called a second time on a running service, then `onStartCommand()` will be called and `onCreate()` is skipped!.
- `bindService()` is called a second time on a running service, then `onBindCommand()` will be called and `onCreate()` is skipped!.
- Bounded services must be unbound by **all** components before `onDestroy()` will be called. For example, suppose 3 components ( denoted by c1, c2, and c3 ) are bound to a service ( denoted by s1 ). If the first component `c1` calls `unbindService()`, then `s1` will invoke `onUnbind()`. If the third component `c3` calls `unbindService()`, then `s1` will invoke `onUnbind()`. **Only after `c2`** calls `unbindService()`, will `s1` call `onUnbind()` **and** `onDestroy()`.



If the service is started, the active lifetime ends the same time that the entire lifetime ends (the service is still active even after `onStartCommand()` returns). If the service is bound, the active lifetime ends when `onUnbind()` returns.

Read more:
- [Services](https://developer.android.com/guide/components/services.html)
- [Bound Services](https://developer.android.com/guide/components/bound-services.html)
