# Messenger

Activity

```java
public class MainActivity extends Activity implements ServiceConnection{

    Messenger mServiceMessenger;
    Messenger mClientMessenger = new Messenger(new ClientHandler());

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Intent intent = new Intent(this,TestService.class);
        bindService(intent,this, Context.BIND_AUTO_CREATE);
    }


    @Override
    public void onServiceConnected(ComponentName name, IBinder service) {
        mServiceMessenger = new Messenger(service);
        Message m = Message.obtain();
        m.replyTo = mClientMessenger;
        try {
            mServiceMessenger.send(m);
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }

    @Override
    public void onServiceDisconnected(ComponentName name) {}

    public class ClientHandler extends Handler {
        @Override
        public void handleMessage(Message msg) {
            Log.d("Spam","Message Received");
        }
    }
}
```

Service

```java
public class TestService extends Service {

    private Messenger mServiceMessenger = new Messenger(new ServiceHandler());
    private Messenger mClientMessenger;
    private Random r = new Random();

    public TestService() {
        super();
    }

    @Override
    public void onCreate() {
        super.onCreate();
    }


    @Override
    public IBinder onBind(Intent intent) {
        return mServiceMessenger.getBinder();
    }

    public void initSpam(){
        for(int i=0;i<10;i++) {
            TimerTask task = new TimerTask() {
                @Override
                public void run() {
                    Bundle b = new Bundle();
                    b.putInt("INT",r.nextInt());
                    b.putLong("LONG",r.nextLong());
                    b.putBoolean("BOOL",r.nextBoolean());
                    b.putFloat("FLOAT",r.nextFloat());
                    b.putDouble("DOUBLE",r.nextDouble());
                    b.putString("STRING",String.valueOf(r.nextInt()));
                    Message msg = Message.obtain();
                    msg.setData(b);

                    try {
                        mClientMessenger.send(msg);
                    } catch (RemoteException e) {
                        e.printStackTrace();
                    }
                }
            };
            Timer timer = new Timer();
            timer.scheduleAtFixedRate(task,1,1);
        }
    }

    public class ServiceHandler extends Handler {
        @Override
        public void handleMessage(Message msg) {
            mClientMessenger = msg.replyTo;
            initBarrage();

        }
    }
}
```

# 



