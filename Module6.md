# Module 6
## Android Security
* SE-Linux (Security enhanced Linux) is used in Android.
* Verified boot is used.
* Rooting is allowed, but require erase of the user data. 
* System Partition Read-only
* Android 5 supports full-disk encryption. Android 6 enforces it. Anroid 7 supports file-based encryption. 
* Password protected. Password is used in the encryption process. Device management API are provided.
* Application Sandbox
  * Each application is run in a separate process. Process isolation is provided by underneath Linux kernel. 
  Each application cannot access other application's member. Communication between different applications are done through IPC or ICC. 
  * Each application has a separate uid/gid. Using the file system permission mechanism, each application cannot access 
  another application's internal storage. Data share between different applications are through content provider or external storage.
* Android Permission Model
  * Request all at the installation (Android 5 and under) vs Request at the run time (Android 6 and above)
  * Permissions are used to protect sensitive APIs and ICC. 
    * the \<uses-permission\> tag and the \<permission\> tag
    * the android:permission attribute
* Storage
  * Internal vs external 
  * Content provider
  * Enryption 
* ICC
  * Explicit intent vs implicit intent
  * Pending intent
  * Open component
## Graphics 
* Drawable
* Customerized View
* Canvas
* Animation
  
    

