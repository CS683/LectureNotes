# Data Storage
## Some questions:
* what type of data need to be stored in app?
  * small setting/configuration data, structured data, unstructured data (general files), local/remote
* Where are they stored in the device?
  * Under /data/data/<appname>/. 
  * Each folder has its own uid/gid. Cannot be accessed by other applications. 
  * This is usually called the internal storage, which other applications cannot access.
* What APIs are used to store/access the data? (see below)
## SharedPreferences
* Used to store small amount of configuration data. Stored the key value pairs in xml files under /data/data/<appname>/shared_prefs/.
* An app can have multiple shared preference files, each stores multiple key value pairs.
* To access the sharedPreferences object, call getSharedPreferences(name, mode) in a context such as activity.  
* SharedPreferences defines a number of getter methods to get values based on keys. 
* To write data in the sharedPreferences, we need to user editor and its putter methods. 
* You can also call getPreferences(mode) in an activity. No need to pass a name into this method, as the default name is the actiyt name. This is intended to have a private sharedpreferences just for that activity.
## Database - SQLite.
* SQLite: a lite, simple SQL database. A database is simply a file. No server and no need for special configuration. Support SQL statements.
* Databases are stored under /data/data/<appname>/databases/. You can create multiple databases. Each database is just a simiple file.
* The file extension name doesn't matter. (It can be .db, .sqlite, or no extension name).
* Database operations: Open/close, CRUD (create tables/insert records, Read(query), Update records, Delete records/drop the table)
* First, design the database schema. Create a separate Contract class which defines a lot of constant strings related to the schema.
* Two main classes: 
  * SQLiteOpenHelper (an abstract class with two abstract methods: onCreate(), onUpgrade()),
  * SQLiteDatabase (a final class that cannot be extended/subclassed. You cannot change its behavior in subclasses)
* Database Implementation:
  * First create a subclass of SQLiteOpenHelper, implement its two abstract methods onCreate() and onUpgrade(), 
  * Then create an instance of this helper where you need to use it (e.g. in a Dao class), call its getReadableDatabase() or getWritableDatabase(). This will return the reference to a SQLiteDatabase object. If the database does not exist before, the database is created, and the onCreate() method of the helper will be called.
  * When you have the SQLiteDatab object reference, you can call its CRUD methods to perform any necessary database operations.
  * ContentValue object is offen used to store a set of value in a record . 
  * cursor object is returned when performing a database query, enabling traversal over the records returned from the database query. 
  * A separate Dao calss can be used to separate the database code from UI code. 
  
  
  







