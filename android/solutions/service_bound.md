## How does a Bound Service work?

- A `Bound Service` has its own [lifecycle](solutions/service_lifecycle.md) that is different from `Started Service`.
- Components must bind to the service using `bindService()`. 
- In order to stop the `Bound Service`, **all** bound components must call `unbindService()`.

### Binding to a Service 

In oder to bind to a service, the following steps must be taken:
- Service should extend `Binder` class and return this `IBinder` instance during `onBind()`
- Component must create a `ServiceConnection` and grab an instance of the service from the `IBinder` during `onServiceConnected()` callback.
- Component must bind to the service using `ServiceConnection` instance and `bindService()`.
- Component can interact with the service.

#### 1) IBinder

Your service should return an `IBinder` object during `onBind()` so that the binding component can communicate with your service.

For this you will need to extend the `Binder` class which will return an instance of your `Service` via `getService()`.

```java

public class LocalService extends Service {
    // Binder given to clients
    private final IBinder mBinder = new LocalBinder();
    // Random number generator
    private final Random mGenerator = new Random();

    /**
     * Class used for the client Binder.  Because we know this service always
     * runs in the same process as its clients, we don't need to deal with IPC.
     */
    public class LocalBinder extends Binder {
        LocalService getService() {
            // Return this instance of LocalService so clients can call public methods
            return LocalService.this;
        }
    }

    @Override
    public IBinder onBind(Intent intent) {
        return mBinder;
    }

    /** 
     * Public method for bounded clients to interact with your service.
     * This method simply returns a random number to the bound component.
     */
    public int getRandomNumber() {
      return mGenerator.nextInt(100);
    }
}

```

#### 2) Service Connection

Inside your component, you need to create a new `ServiceConnection()` object. This object has two callbacks:
- `onServiceConnected()` called when a connection to the `Service` has been established, with the `IBinder` of the communication channel to the `Service`. You can then cast the `IBinder` to your `LocalBinder` type and then pull out a reference to your `LocalService` instance.
- `onServiceDisconnected()` called when a connection to the `Service` has been lost. This typically happens when the process hosting the service has crashed or been killed. This does not remove the `ServiceConnection` itself -- this binding to the service will remain active, and you will receive a call to `onServiceConnected(ComponentName, IBinder)` when the `Service` is next running.

```java

    /** 
      * Defines callbacks for service binding, passed to bindService() 
      */
    private ServiceConnection mConnection = new ServiceConnection() {

        @Override
        public void onServiceConnected(ComponentName className, IBinder iBinder) {
            // We've bound to LocalService, cast the IBinder and get LocalService instance
            LocalBinder localBinder = (LocalBinder) iBinder;
            mService = localBinder.getService();
            mBound = true;
        }

        @Override
        public void onServiceDisconnected(ComponentName arg0) {
            mBound = false;
        }
    };

```

#### 3) Binding to the Service

Now that we have an instance of `LocalService`, our component can bind to it!

Remember that `mConnection` is an instance of `ServiceConnection` defined above.

```java

  @Override
  protected void onStart() {
      super.onStart();
      // Bind to LocalService
      Intent intent = new Intent(this, LocalService.class);
      bindService(intent, mConnection, Context.BIND_AUTO_CREATE);
  }

  @Override
  protected void onStop() {
      super.onStop();
      // Unbind from the service
      if (mBound) {
          unbindService(mConnection);
          mBound = false;
      }
  }

```

#### 4) Interacting with the Bound Service

We are now bound to the `LocalService` using out `ServiceConnection`. We can now iteract with `LocalService`.

Remember that `mService` instance was assigned when `ServiceConnection` connected to the service via `onServiceConnected()`.

```java

  /** 
    * Called when a button is clicked (the button in the layout file attaches to
    * this method with the android:onClick attribute) 
    */
  public void onButtonClick(View v) {
      if (mBound) {
          // Call a method from the LocalService.
          // However, if this call were something that might hang, then this request should
          // occur in a **separate thread** to avoid slowing down the activity performance.
          int num = mService.getRandomNumber();
          Toast.makeText(this, "number: " + num, Toast.LENGTH_SHORT).show();
      }
  }

```


Read more:
- [Bound Services](https://developer.android.com/guide/components/bound-services.html)
- [Binder](https://developer.android.com/reference/android/os/Binder.html) note it implements `IBinder`
- [Service Connection](https://developer.android.com/reference/android/content/ServiceConnection.html)
- [Bound Service lifecycle](solutions/service_lifecycle.md)
