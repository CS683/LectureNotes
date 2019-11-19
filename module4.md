# Data Storage
## Some questions:
1. what type of data need to be stored in app?
small setting/configuration data, structured data, unstructured data (general files), local/remote
2. Where are they stored in the device?
/data/data/<appname>/
each folder has its own uid. Cannot be access by other users. 
internal storage (private storage): each application cannot access other application's data 
3. What APIs are used to store/access the data?
## SharedPreferences
1. Used to store small amount of configuration data
2. getSharedPreferences(name, mode), SharedPreferences, getter method to get values based on keys, 
3. User editor and putter method to write data
4. getPreferences(mode), default name is the activity name, - private sharedpreferences for that activity.
5. /data/data/<appname>/shared_prefs/
## Database - SQLite.
1. SQLite: lite, simple, one file for a database, no server, no configuration, still can run SQL statements.
2. /data/data/<appname>/databases/ - can have multiple databases, each database is just a simiple file
3. File extension name doesn't matter. (.db, .sqlite, no extension)
4. Database operations: Open/close, CRUD (create tables/insert records, Read (query ), Update records, Delete records /drop the table)
5. First, design database schema, - create a separate Contract class (defines a lot of constant strings)
6. SQLiteOpenHelper - abstract class (two abstract methods: onCreate(), onUpgrade())
7. SQLiteDatabase - final class (cannot extend/subclass it, cannot change its behavior in subclasses)
8. Subclass SQLiteOpenHelper, create an instance of this helper, call its getReadableDatabase() or getWritableDatabase()
9. If the database does not exist before, the database is created, and the onCreate() method of the helper will be called.







