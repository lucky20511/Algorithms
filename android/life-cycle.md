# Activity

![](https://developer.android.com/guide/components/images/activity_lifecycle.png)

# Service

![](https://developer.android.com/images/service_lifecycle.png)

## Managing the lifecycle of a bound service {#Lifecycle}

---

When a service is unbound from all clients, the Android system destroys it \(unless it was also started with[`onStartCommand()`](https://developer.android.com/reference/android/app/Service.html#onStartCommand%28android.content.Intent, int, int%29)\). As such, you don't have to manage the lifecycle of your service if it's purely a bound service—the Android system manages it for you based on whether it is bound to any clients.

However, if you choose to implement the[`onStartCommand()`](https://developer.android.com/reference/android/app/Service.html#onStartCommand%28android.content.Intent, int, int%29)callback method, then you must explicitly stop the service, because the service is now considered to be_started_. In this case, the service runs until the service stops itself with[`stopSelf()`](https://developer.android.com/reference/android/app/Service.html#stopSelf%28%29)or another component calls[`stopService()`](https://developer.android.com/reference/android/content/Context.html#stopService%28android.content.Intent%29), regardless of whether it is bound to any clients.

Additionally, if your service is started and accepts binding, then when the system calls your[`onUnbind()`](https://developer.android.com/reference/android/app/Service.html#onUnbind%28android.content.Intent%29)method, you can optionally return`true`if you would like to receive a call to[`onRebind()`](https://developer.android.com/reference/android/app/Service.html#onRebind%28android.content.Intent%29)the next time a client binds to the service.[`onRebind()`](https://developer.android.com/reference/android/app/Service.html#onRebind%28android.content.Intent%29)returns void, but the client still receives the[`IBinder`](https://developer.android.com/reference/android/os/IBinder.html)in its[`onServiceConnected()`](https://developer.android.com/reference/android/content/ServiceConnection.html#onServiceConnected%28android.content.ComponentName, android.os.IBinder%29)callback. The following figure illustrates the logic for this kind of lifecycle.

![](https://developer.android.com/images/fundamentals/service_binding_tree_lifecycle.png)

