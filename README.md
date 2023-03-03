# amp_3



PRACTICAL 3
Aim : Programming Activities and fragments 
Activity Life Cycle, Activity methods, Multiple Activities. 

1. onCreate()
It is called when the activity is first created. This is where all the static work is done 
like creating views, binding data to lists, etc. This method also provides a Bundle 
containing its previous frozen state if there was one.
2. onStart()
It is invoked when the activity is visible to the user. It is followed by onResume() if 
the activity is invoked from the background. It is also invoked after onCreate()
when the activity is first started. 
3. onRestart()
It is invoked after the activity has been stopped and prior to its starting stage and thus 
is always followed by onStart() when any activity is revived from background to 
on-screen. 
4. onResume()
It is invoked when the activity starts interacting with the user. At this point, the 
activity is at the top of the activity stack, with a user interacting with it. Always 
followed by onPause() when the activity goes into the background or is closed by 
the user.
5. onPause()
It is invoked when an activity is going into the background but has not yet been killed. 
It is a counterpart to onResume(). When an activity is launched in front of another 
activity, this callback will be invoked on the top activity (currently on screen).
6. onStop()
It is invoked when the activity is not visible to the user. It is followed by 
onRestart() when the activity is revoked from the background, followed by 
onDestroy() when the activity is closed or finished, and nothing when the activity 
remains on the background only. Note that this method may never be called, in low 
memory situations where the system does not have enough memory to keep the 
activity’s process running after its onPause() method is called. 
7. onDestroy()
The final call received before the activity is destroyed. This can happen either because 
the activity is finishing (when finish() is invoked) or because the system is 
temporarily destroying this instance of the activity to save space.
The Log.d() method is used to display messages with the Debug level priority on 
the Logcat. The method requires two arguments: The tag argument is the tag of the 
message.


Steps :
1. Open Android Studio and select New Project > Empty Activity
2. Enter project name and click on Finish
3. Once the Project starts, the activity_main.xml and MainActivity.java is open 
in the editor window.
4. In the MainActivity.java file, we have to do the following:
a. import android.util.Log;
b. In the main class, add the following code:

            String tag = "Android Activity Lifecycle";
            @Override
            protected void onCreate(Bundle savedInstanceState) {
             super.onCreate(savedInstanceState);
             setContentView(R.layout.activity_main);
             Log.d(tag,"in onCreate event");
            }
            public void onStart(){
             super.onStart();
             Log.d(tag,"in Start event");
            }
            public void onRestart(){
             super.onRestart();
             Log.d(tag,"in ReStart event");
            }
            public void onResume(){
             super.onResume();
             Log.d(tag,"in Resume event");
            }
            public void onPause(){
             super.onPause();
             Log.d(tag,"in Pause event");
            }
            public void onStop(){
             super.onStop();
             Log.d(tag,"in Stop event");
            }
            public void onDestroy(){
             super.onDestroy();
             Log.d(tag,"in Destroy event");
            }

