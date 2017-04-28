# Communication Methods

The following are the list of method for the communication between activities and services:

### Intra-Process \(Early Binding\)

1. .jar Library
2. Binder to Service

### Inter-Process \(Running Time Binding\)

1. Intent  +bindService\(\)  or  +startService\(\)        **Bounded  &  unBounded**
2. Broadcast      **Bounded  &  unBounded ** 
3. Messenger     **Bounded  &  UnBounded **
4. AIDL            **Bounded**
5. HTTP Server    **Bounded  &  UnBounded **

| Method | Service Type | Flexibility | Direction | Speed |
| :--- | :--- | :--- | :--- | :--- |
| Intent + bind or start | Bounded & Unbounded | High | 1 way | Slow |
| Broadcast | Bounded & Unbounded | High | 2 way | Slow |
| AIDL | Bounded | Medium | 2 way | Faster |
| Messenger | Bounded & Unbounded | Medium High | 2 way | Fast |
| HTTP Server | Bounded & Unbounded | High | 2 way | Slow |

An`Intent`is "sent" when one app or`Activity`wants to launch another to do something very specific. For example, a file-manager might want to launch an image viewer or video player. Your app might want to launch a very specific`Activity`within another one of your apps, etc. The communication by specific intents \(i.e. including package name and component name\) can not easily be intercepted, so it's somewhat more secure. Most importantly, there's only and exactly one "receiver" -- if none can be found, the`Intent`will fail.

Further, a`BroacastReceiver`will be active within an`Activity`or`Service`and received broadcasts will generally only change state and/or do minor UI updates... for example, you might disable a few actions if your internet connectivity is dropped. By comparison, a specific Intent will usually launch a new`Activity`or bring an existing one to the foreground.

3\)Using a Binder to talk to a service is only possible if the two are in the same process. Its a method to totally avoid using IPC.

4\)AIDL is a wrapper around an IPC method. AIDL uses IPC, it just tries to make it look like normal function calls to the client.

5\)An Intent object is an abstraction for all the data needed to start a service or activity in Android. It will include parameters, which may or may not be in Parcels. It may or may not use IPC to send those parameters \(if the target Activitiy or Service is in another APK it will. If it isn't it may not\).

I think the problem here is you don't really understand what a process is, what an Android component is, and how processes actually communicate. I suggest doing some studying up on that.

@AIDL is just one way to communicate with a bound service. There is no such thing as a 'AIDL based servcie', it's just a bound service that returns a Binder generated based on an AIDL interface.

@In the ADIL guide on Android developer says

**"Note: Using AIDL is necessary only if you allow clients from different applications to access your service for IPC and want to handle multithreading in your service. If you do not need to perform concurrent IPC across different applications, you should create your interface by implementing a Binder"**

so what does this mean ?

@It means what is says: if you use AIDL you allow multiple clients to connect concurrently and you should be able to handle this. If you use a messenger, it will serialize requests for you. If you use the service in the same process, you can access it directly \(no IPC\) via your own class that extends Binder.

Bound Service

[Extending the Binder class](https://developer.android.com/guide/components/bound-services.html#Binder)

If your service is private to your own application and runs in the same process as the client \(which is common\), you should create your interface by extending the[`Binder`](https://developer.android.com/reference/android/os/Binder.html)class and returning an instance of it from[`onBind()`](https://developer.android.com/reference/android/app/Service.html#onBind%28android.content.Intent%29). The client receives the[`Binder`](https://developer.android.com/reference/android/os/Binder.html)and can use it to directly access public methods available in either the[`Binder`](https://developer.android.com/reference/android/os/Binder.html)implementation or the[`Service`](https://developer.android.com/reference/android/app/Service.html).

This is the preferred technique when your service is merely a background worker for your own application. The only reason you would not create your interface this way is because your service is used by other applications or across separate processes.

[Using a Messenger](https://developer.android.com/guide/components/bound-services.html#Messenger)

If you need your interface to work across different processes, you can create an interface for the service with a[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html). In this manner, the service defines a[`Handler`](https://developer.android.com/reference/android/os/Handler.html)that responds to different types of[`Message`](https://developer.android.com/reference/android/os/Message.html)objects. This[`Handler`](https://developer.android.com/reference/android/os/Handler.html)is the basis for a[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html)that can then share an[`IBinder`](https://developer.android.com/reference/android/os/IBinder.html)with the client, allowing the client to send commands to the service using[`Message`](https://developer.android.com/reference/android/os/Message.html)objects. Additionally, the client can define a[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html)of its own, so the service can send messages back.

This is the simplest way to perform interprocess communication \(IPC\), because the[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html)queues all requests into a single thread so that you don't have to design your service to be thread-safe.

[Using AIDL](https://developer.android.com/guide/components/aidl.html)

Android Interface Definition Language \(AIDL\) decomposes objects into primitives that the operating system can understand and marshals them across processes to perform IPC. The previous technique, using a[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html), is actually based on AIDL as its underlying structure. As mentioned above, the[`Messenger`](https://developer.android.com/reference/android/os/Messenger.html)creates a queue of all the client requests in a single thread, so the service receives requests one at a time. If, however, you want your service to handle multiple requests simultaneously, then you can use AIDL directly. In this case, your service must be thread-safe and capable of multi-threading.

To use AIDL directly, you must create an`.aidl`file that defines the programming interface. The Android SDK tools use this file to generate an abstract class that implements the interface and handles IPC, which you can then extend within your service.

### 

# 



