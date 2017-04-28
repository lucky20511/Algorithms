# Intent  \(One Way Communication\)

Activity

```java
public void sendLogin (View loginview){
    Intent i = new Intent(this, NetworkService.class);
    i.putExtra("username", usernameText.getText().toString());
    i.putExtra("password", passwordText.getText().toString());
    startService(i);
}
```

Service

```java
public class NetworkService extends IntentService {

    public NetworkService() {
        super("NetworkService");
    }

    protected void onHandleIntent(Intent i) {

        @Override
        protected void onHandleIntent(Intent intent) {
            String username = intent.getStringExtra("username");
            String password = intent.getStringExtra("password");
            .....
        }
    }
}
```



