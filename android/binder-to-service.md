# Binder to Service

Activity

```java
//Activity implements the Callbacks interface which defined in the Service  
    public class MainActivity extends ActionBarActivity implements MyService.Callbacks{

    ToggleButton toggleButton;
    ToggleButton tbStartTask;
    TextView tvServiceState;
    TextView tvServiceOutput;
    Intent serviceIntent;
    MyService myService;
    int seconds;
    int minutes;
    int hours;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
         serviceIntent = new Intent(MainActivity.this, MyService.class);
        setViewsWidgets();
    }

    private void setViewsWidgets() {
        toggleButton = (ToggleButton)findViewById(R.id.toggleButton);
        toggleButton.setOnClickListener(btListener);
        tbStartTask = (ToggleButton)findViewById(R.id.tbStartServiceTask);
        tbStartTask.setOnClickListener(btListener);
        tvServiceState = (TextView)findViewById(R.id.tvServiceState);
        tvServiceOutput = (TextView)findViewById(R.id.tvServiceOutput);

    }

    private ServiceConnection mConnection = new ServiceConnection() {

        @Override
        public void onServiceConnected(ComponentName className,
                                       IBinder service) {
            Toast.makeText(MainActivity.this, "onServiceConnected called", Toast.LENGTH_SHORT).show();
            // We've binded to LocalService, cast the IBinder and get LocalService instance
            MyService.LocalBinder binder = (MyService.LocalBinder) service; 
            myService = binder.getServiceInstance(); //Get instance of your service! 
            myService.registerClient(MainActivity.this); //Activity register in the service as client for callabcks! 
            tvServiceState.setText("Connected to service...");
            tbStartTask.setEnabled(true);
        }

        @Override
        public void onServiceDisconnected(ComponentName arg0) {
            Toast.makeText(MainActivity.this, "onServiceDisconnected called", Toast.LENGTH_SHORT).show();
            tvServiceState.setText("Service disconnected");
            tbStartTask.setEnabled(false);
        }
    };

    View.OnClickListener btListener =  new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            if(v == toggleButton){
                if(toggleButton.isChecked()){
                    startService(serviceIntent); //Starting the service 
                    bindService(serviceIntent, mConnection,            Context.BIND_AUTO_CREATE); //Binding to the service! 
                    Toast.makeText(MainActivity.this, "Button checked", Toast.LENGTH_SHORT).show();
                }else{
                    unbindService(mConnection);
                    stopService(serviceIntent);
                    Toast.makeText(MainActivity.this, "Button unchecked", Toast.LENGTH_SHORT).show();
                    tvServiceState.setText("Service disconnected");
                    tbStartTask.setEnabled(false);
                }
            }

            if(v == tbStartTask){
                if(tbStartTask.isChecked()){
                      myService.startCounter();
                }else{
                    myService.stopCounter();
                }
            }
        }
    };

    @Override
    public void updateClient(long millis) {
        seconds = (int) (millis / 1000) % 60 ;
        minutes = (int) ((millis / (1000*60)) % 60);
        hours   = (int) ((millis / (1000*60*60)) % 24);

        tvServiceOutput.setText((hours>0 ? String.format("%d:", hours) : "") + ((this.minutes<10 && this.hours > 0)? "0" + String.format("%d:", minutes) :  String.format("%d:", minutes)) + (this.seconds<10 ? "0" + this.seconds: this.seconds));
    }
}
```

Service

```java
public class MyService extends Service {
    NotificationManager notificationManager;
    NotificationCompat.Builder mBuilder;
    Callbacks activity;
    private long startTime = 0;
    private long millis = 0;
    private final IBinder mBinder = new LocalBinder();
    Handler handler = new Handler();
    Runnable serviceRunnable = new Runnable() {
        @Override
        public void run() {
            millis = System.currentTimeMillis() - startTime;
            activity.updateClient(millis); //Update Activity (client) by the implementd callback
            handler.postDelayed(this, 1000);
        }
    };


    @Override
    public int onStartCommand(Intent intent, int flags, int startId) {

        //Do what you need in onStartCommand when service has been started
        return START_NOT_STICKY;
    }

    @Override
    public IBinder onBind(Intent intent) {
        return mBinder;
    }
    //returns the instance of the service
    public class LocalBinder extends Binder{
        public MyService getServiceInstance(){
            return MyService.this;
        }
    }

    //Here Activity register to the service as Callbacks client
    public void registerClient(Activity activity){
        this.activity = (Callbacks)activity;
    }

    public void startCounter(){
        startTime = System.currentTimeMillis();
        handler.postDelayed(serviceRunnable, 0);
        Toast.makeText(getApplicationContext(), "Counter started", Toast.LENGTH_SHORT).show();
    }

    public void stopCounter(){
        handler.removeCallbacks(serviceRunnable);
    }


    //callbacks interface for communication with service clients! 
    public interface Callbacks{
        public void updateClient(long data);
    }
}
```

# 



