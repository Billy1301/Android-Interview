## How do you stop both types services?

#### Started Services

- Component calls `stopService()`
- The service itself calls `stopSelf()`

#### Bound Services

- All bound components call `unbindService()`. 
- Suppose you have three components denoted by `c1`, `c2`, and `c3` which are bound to service `s1`. If component `c3` calls `unbindService()`, then `s1` will call `onUnbind()`. If component `c2` calls `unbindService()`, then `s1` will call `onUnbind()`. Finally, when the last component `c1` calls `unbindService()`, `s1` will call `onUnbind()` and `onDestroy()`.

#### Started AND Bound Services

- All components must call `unbindService()` and `stopService()` or `stopSelf()` must be called.

![](https://developer.android.com/images/fundamentals/service_binding_tree_lifecycle.png)

Read more:
- Stopping [started and bound services](http://stackoverflow.com/questions/17146822/when-is-a-started-and-bound-service-destroyed).
- Stopping [services](https://developer.android.com/guide/components/services.html)
- Stopping [bound services](https://developer.android.com/guide/components/bound-services.html)
- [Service lifecycles](solutions/service_lifeycle.md)
