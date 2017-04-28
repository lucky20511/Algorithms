# Implicit Intents v.s Broadcast Receivers

The following is a list here of all the differences between **Implicit Intents**\(sent via`startActivity()`\) and**Broadcasts**\(sent via`sendBroadcast()`\)

1. Broadcasts, by default, can affect multiple applications at once \(Ordered Broadcasts have the potential to be disrupted\). In contrast, Implicit Intents will only affect one application.
   _Please note that there may be multiple possibilities of applications that could be affected, but eventually only one will be._
2. Implicit Intents are handled via
   **Intent-Filters**
   , and Broadcasts are handled via
   **Broadcast Receivers**
   \(albeit the intent-filters play a role here too\).
   _I have seen in many instances over the web that Broadcasts are compared to Intent-filters and that does not make sense to me._
3. An Implicit Intent launches an Activity, or a Service. By contrast, a Broadcast launches a Broadcast Receiver. \(This, if you think about it, is the core difference between Intents and Broadcasts. It is because of this reason that Broadcasts aren't meant to do too much heavy work, and especially not UI work!\)
4. From
   [the Developers Website](http://developer.android.com/reference/android/content/BroadcastReceiver.html):

> There is no way for a BroadcastReceiver to see or capture Intents used with startActivity\(\); likewise, when you broadcast an Intent, you will never find or start an Activity. These two operations are semantically very different: starting an Activity with an Intent is a foreground operation that modifies what the user is currently interacting with; broadcasting an Intent is a background operation that the user is not normally aware of.

The description is shown below:

Broadcasts are just that -- messages broadcast to anyone listening. They are inherently insecure, and delivery to the intended recipient isn't guaranteed, because there really isn't an intended recipient. For example, the`CONNECTIVITY_CHANGE`broadcast makes this quite clear: When connectivity changes in an Android device, many apps might be interested. Rather than the`ConnectivityManager`having to notify each app via specific`Intent`, it sends a broadcast. Any app that has registered interest in this event will be notified. Any app that isn't running or doesn't care... won't.

An`Intent`is "sent" when one app or`Activity`wants to launch another to do something very specific. For example, a file-manager might want to launch an image viewer or video player. Your app might want to launch a very specific`Activity`within another one of your apps, etc. The communication by specific intents \(i.e. including package name and component name\) can not easily be intercepted, so it's somewhat more secure. Most importantly, there's only and exactly one "receiver" -- if none can be found, the`Intent`will fail.

Further, a`BroacastReceiver`will be active within an`Activity`or`Service`and received broadcasts will generally only change state and/or do minor UI updates... for example, you might disable a few actions if your internet connectivity is dropped. By comparison, a specific Intent will usually launch a new`Activity`or bring an existing one to the foreground.

