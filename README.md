# Android-Activity-Lifecycle

This project will show you simple Toast message and pretty log message
in each and every lifecycle state of Activity

```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Logger.addLogAdapter(new AndroidLogAdapter());

        showMessage("onCreate");
    }

    @Override
    protected void onStart() {
        super.onStart();
        showMessage("onStart");
    }

    @Override
    protected void onResume() {
        super.onResume();
        showMessage("onResume");
    }

    @Override
    protected void onPause() {
        super.onPause();
        showMessage("onPause");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        showMessage("onRestart");
    }

    @Override
    protected void onStop() {
        super.onStop();
        showMessage("onStop");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        showMessage("onDestroy");
    }

    private void showMessage(String message){
        Toast.makeText(this, "MainActivity: " + message, Toast.LENGTH_SHORT).show();
        Logger.d("MainActivity: " + message);
    }

    public void goSecondActivity(View view) {
        startActivity(new Intent(this, SecondActivity.class));
    }

    public void finishActivity(View view) {
        finish();
    }
}
```