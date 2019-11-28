# Module 5
## Related github repositories:
* ProjectPortal release M5.1 (https://github.com/CS683/ProjectPortal)
* HandlerThread (https://github.com/CS683/HandlerThread)
* MyServiceAsynExample (https://github.com/CS683/MyServiceAsynExample)
## Broadcast Receiver
* Android components: Activities, Content Providers, Broadcast Receivers, Services
  * Declared in the manifest file (Broadcast receivers can be registered in the code dynamically
  without being decalred in the manifest file)
  * They can be exposed to other applications for communciation. 
  * ICC: Intercomponent communication (Activities, broadcast receivers, services: send/receive messages (intent)) 
 * Broadcast receivers are used to receive broadcast messages (intents), including both system defined and self defined intents.
 * To send intents:
    * send broadcast intents:sendBroadcast(intent) 
    * send an intent to an activity: startActivity(intent)
 * Implmentation
  * Create a subclass of BroadcastReceiver and override the onReceive() method
  * Declare the broadcast receiver in the manifest file or use registerReceiver() in the java code to register it dynamically
 
## Process and Thread
* A Process: a resource consumption unit and a protection/isolation unit (separate address space )
* A thread (multiple threads in a process): an execution unit for parallelism. Each thread of execution has its own execution path)
* Basic memory layout: code, data (constant, global varaible (final,static)), 
 stack (hold the unreturned functiona call data including arguments, return address, local variables)  and heap (objects)  
* Each thread has its own stack. All threads in the process share code, data and heap.  
* Each android application runs in a separate single-threaded process by default. This thread is called the main thread, or the UI thread.
All components are run in this thread. The Key is to never block the UI thread. 
* The challenge of a multithreaded process is the synchronization.

## AsyncTask
* Provid a background thread to do the task and communicate with the UI thread.
* Is an abstract class with an abstract method doInBackground()
* the execute() method is a final method, which will call 
  * onPreExecute() on the UI thread
  * doInBackground() on the background thread. The parameters are passed into this method, and the returned result 
  will be passed to onPostExecute(). You can call publishProgress() in this method, which will trigger 
  the onProgressUpdate() method to be executed on the UI thread.
  * onPostExecute() on the UI thread
* Implementation:
  * Subclass AsyncTask and implement doInBackground(), maybe also override other methods such as onPostExecute()
  * Create an object of the subclass, and call its execute() method. 

## Handler and HandlerThread
* A handlerThread is a special thread with a looper.
* The main thread has a looper
* Multiple handlers can be created for one thread (with one looper)
* If a thread (the main thread) wants to send a message to another thread (e.g the handler thread), 
it need to use a handler associated with the receiving thread, and use that handler.sendMessage().
* Use handler to schedule a future execution.

## Services
* A component without UI
* The service is run in the UI thread by default.
* Since usually a long operation is run in the service, a background thread is usually used to prevent the UI thread
from blocking. You need to either create a background thread using Java thread API or Handler thread API or 
or using an intent service
* To send an intent to a startservice, use startService(intent). To handle the intents in the startedService, 
override onStartCommand(). 
* Intent Services
  * Provide a background worker thread to handle all incoming intents.
  * The callback onHandleIntent() is called by onStartCommand(). Be aware that onStartCommand() is executed 
  in the UI thread, but onHandleIntent() is executed in the background worker thread. 
  * Like AsyncTask, only one background thread is provided. If you need multiple background threads, you need to use 
  the general service and create them explicitly.
  * It also stops itself automatically. 
  





 

 

