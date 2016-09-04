# Android_Session7_Assignment

DATABASE BASICS

a) What is the use of SQLite open helper class in SQLite?

SQLite open helper is a helper class to manage database creation and version management.
You create a subclass implementing onCreate(SQLiteDatabase), onUpgrade(SQLiteDatabase, int, int) and optionally onOpen(SQLiteDatabase), and this class takes care of opening the database if it exists, creating it if it does not, and upgrading it as necessary. Transactions are used to make sure the database is always in a sensible state.
This class makes it easy for ContentProvider implementations to defer opening and upgrading the database until first use, to avoid blocking application startup with long-running database upgrades.


b) What is the use of OnUpgrade function in SQLiteOpenHelper class?

void onUpgrade (SQLiteDatabase db,  int oldVersion, int newVersion) is called when the database needs to be upgraded. The implementation should use this method to drop tables, add tables, or do anything else it needs to upgrade to the new schema version.
If you add new columns you can use ALTER TABLE to insert them into a live table. If you rename or remove columns you can use ALTER TABLE to rename the old table, then create the new table and then populate the new table with the contents of the old table.
This method executes within a transaction. If an exception is thrown, all changes will automatically be rolled back.



c) How to show SQLite database table information in Android application what is the best way to do it?

	Showing database information will be better suited with table layout. Since table layout is not in adapter view, you can’t use cursor adapter with it. So use table layout with cursor to show the data base information.

