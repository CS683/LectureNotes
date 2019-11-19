# Data Storage
## Some questions:
* what type of data need to be stored in app?
small setting/configuration data, structured data, unstructured data (general files), local/remote
* Where are they stored in the device?
Under /data/data/<appname>/. 
Each folder has its own uid/gid. Cannot be accessed by other applications. 
This is usually called the internal storage, which other applications cannot access.
* What APIs are used to store/access the data? 
## SharedPreferences
1. Used to store small amount of configuration data. Stored the key value pairs in xml files under /data/data/<appname>/shared_prefs/.
2. An app can have multiple shared preference files, each stores multiple key value pairs.
3. To access the sharedPreferences object, call getSharedPreferences(name, mode) in a context such as activity.  
4. SharedPreferences defines a number of getter methods to get values based on keys. 
5. To write data in the sharedPreferences, we need to user editor and its putter methods. 
5. You can also call getPreferences(mode) in an activity. No need to pass a name into this method, as the default name is the actiyt name. This is intended to have a private sharedpreferences just for that activity.
## Database - SQLite.
1. SQLite: a lite, simple SQL database. A database is simply a file. No server and no need for special configuration. Support SQL statements.
2. Databases are stored under /data/data/<appname>/databases/. You can create multiple databases. Each database is just a simiple file.
3. The file extension name doesn't matter. (It can be .db, .sqlite, or no extension name).
4. Database operations: Open/close, CRUD (create tables/insert records, Read(query), Update records, Delete records/drop the table)
5. First, design the database schema. Create a separate Contract class which defines a lot of constant strings related to the schema.
6. Two main classes: SQLiteOpenHelper (an abstract class with two abstract methods: onCreate(), onUpgrade()), 
  SQLiteDatabase (a final class that cannot be extended/subclassed. You cannot change its behavior in subclasses)
7. First create a subclass of SQLiteOpenHelper, implement its two abstract methods onCreate() and onUpgrade(), 
8. Then create an instance of this helper where you need to use it (e.g. in a Dao class), call its getReadableDatabase() o getWritableDatabase(). This will return the reference to a SQLiteDatabase object. If the database does not exist before, the database is created, and the onCreate() method of the helper will be called.
9. When you have the SQLiteDatab object reference, you can call its CRUD methods to perform any necessary database operations.
10. A ContentValue object is offen used to store a set of value in a record . 
11. A cursor object is returned when performing a database query, enabling traversal over the records returned from the database query. 
12. A separate Dao calss can be used to separate the database code from UI code. 
  
  
  







