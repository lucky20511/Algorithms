# AIDL \(Two way Communication\)

AIDL for Activity calls Service Intent  \(**Implemented** in **Service** and **Used** in **Activity**\)

```java
import IServiceAidlCallback;

interface IRemoteService {

    void registerCallback(IServiceAidlCallback cb);   
}
```

AIDL for  Service Calls back to Activity  \(**Implemented** in **Activity** and **Used** in **Service**\)

```java
interface IServiceAidlCallback {

    void basicTypes(int aI, long aL, boolean aB, float aF, double aD, String aS)
}
```

Activity

```java
public class MainActivity extends Activity implements ServiceConnection{

    IRemoteService mService;
    TextView countTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Intent intent = new Intent(this,TestService.class);
        bindService(intent,this, Context.BIND_AUTO_CREATE);
    }

    @Override
    public void onServiceConnected(ComponentName name, IBinder service) {

        mService = IRemoteService.Stub.asInterface(service);
        try {
            mService.registerCallback(mClientBinder);
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }

    @Override
    public void onServiceDisconnected(ComponentName name) {}


    public final IServiceAidlCallback.Stub mClientBinder = new IServiceAidlCallback.Stub(){
        public void basicTypes(int anInt, long aLong, boolean aBoolean,
                               float aFloat, double aDouble, String aString){
            Log.d("Spam","Callback Received");
        }
    };
}
```

Service

```java
public class TestService extends Service {

    private Random r = new Random();

    private IServiceAidlCallback mClientCallback;

    public TestService() {
        super();
    }

    @Override
    public void onRebind(Intent intent) {
        super.onRebind(intent);
    }

    @Override
    public void onCreate() {
        super.onCreate();
    }

    @Override
    public int onStartCommand(Intent intent, int flags, int startId) {
        return super.onStartCommand(intent, flags, startId);
    }

    @Override
    public IBinder onBind(Intent intent) {
        return mBinder;
    }

    public final IRemoteService.Stub mBinder = new IRemoteService.Stub(){
        public void registerCallback(IBinder callback){

            mClientCallback = IServiceAidlCallback.Stub.asInterface(callback);
            initSpam();

        }
    };

    public void initSpam(){
        for(int i=0;i<10;i++) {
            TimerTask task = new TimerTask() {
                @Override
                public void run() {
                    try {
                        mClientCallback.basicTypes(
                                r.nextInt(),
                                r.nextLong(),
                                r.nextBoolean(),
                                r.nextFloat(),
                                r.nextDouble(),
                                String.valueOf(r.nextInt()));
                    } catch (RemoteException e) {
                        e.printStackTrace();
                    }
                }
            };
            Timer timer = new Timer();
            timer.scheduleAtFixedRate(task,1,1);
        }
    }
}
```



