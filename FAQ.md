**Q**: Where are the saved pages stored?

**A**: Pages are stored in an SQLite database. Location of this database depends on browser name and OS. See [ExtractingPages](ExtractingPages.md) for more details.

**Q**: Is there any backup/synchronization functionality?

**A**: No, not yet. But if you want, you can copy the database file to some other location and use it as a backup. See [ExtractingPages](ExtractingPages.md) for location of a database file. If you'd like to move the database to another computer, then install Chrome Scrapbook there first. This will create an empty database on this computer. Quit the browser, find the new database and copy the saved database over it.

**Q**: Can I use your code in my program/extension/etc?

**A**: The code is licensed under GNU [LGPL](http://www.gnu.org/licenses/lgpl.html) version 3 or later, so it can be used in other programs, if you comply with conditions of the license. Especially, you should preserve copyright notices of the authors.