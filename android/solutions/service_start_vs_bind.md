## Whats the difference between starting a service and binding to a service?

![](https://developer.android.com/images/service_lifecycle.png)

Key differences:
- `Started Services` will run indefinitely until `stopSelf()` or `stopService()` are called.
- `Started Services` vs `Bound Services` have different [lifecycles](solutions/service_lifecycle.md).
- `Bound Services` will run until the last bound component calls `unbindService()`.
- `Bound Services` can be **interacted** with (i.e. component can pause/play music player inside a `bound service` ). They cannot do so with a started service since there is **no link/connection** between the component and a `Started Service`.
- [A service that is both started and bound](http://stackoverflow.com/questions/17146822/when-is-a-started-and-bound-service-destroyed), via `startService()` and `bindService()` must receive calls to both `stopService()` and `unbindService()` before it can call `onDestroy()` and finish its lifecycle.

![](https://developer.android.com/images/fundamentals/service_binding_tree_lifecycle.png)

Read more:
- [Services lifecycles](solutions/service_lifecycle.md)
- [Services](https://developer.android.com/guide/components/services.html)
- [Bound Services](https://developer.android.com/guide/components/bound-services.html)
- [Components](https://developer.android.com/guide/components/fundamentals.html)
