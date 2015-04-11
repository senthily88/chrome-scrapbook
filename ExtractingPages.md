# Where are those pages? #

The Chrome Scrapbook extension saves all pages into an [SQLite](http://www.sqlite.org/) database.
The location of this database depends on the browser used (Chrome, Chromium, etc..) and the operating system.
For example, in Chromium on Linux the database is located here (for Chrome one probably should replace 'chromium' with 'chrome'):

```
~/.config/chromium/Default/databases/chrome-extension_gokffdfnlmampchciemmflgbckijpmlb_0
```

In Windows this path should look so:
```
C:\Documents and Settings\<username>\Local Settings\Application Data\Google\Chrome\User Data\Default\databases\chrome-extension_gokffdfnlmampchciemmflgbckijpmlb_0
```

There should be one file located in this directory.
It stores all the information about pages saved by Chrome Scrapbook.
It can be backed-up or moved to another system/user account if needed.

# How to get them? #

It is possible to extract the pages using sqlite3 command-line utility.
The following examples are for Linux operating system.
Commands for other operating systems should be similar.

First, one should find an ID for the page.
It is possible to do using the following command:

```
$ sqlite3 2 'select id, header from documents;'
14|HTML5: Techniques for providing useful text alternatives
16|Debian -- The Universal Operating System
17|Web SQL Database
18|HTML5 Web SQL Database – Intro to Versioning and Migrations « occasionally useful
19|Annotating JavaScript for the Closure Compiler - Closure Compiler - Google Code
20|JSDoc Homepage - JavaScript Documentation Tool
21|
```

Here, 2 — is the name of a database file.
In the output of the command you can see IDs and titles for all pages stored in a database.
The page with ID 21 has no title.

Now pages can be saved with the following command (in this example for page 17 with title "Web SQL Database"):

```
$ sqlite3 2 'select content from document_contents where id=17;' > doc.html
```

After executing this command file `doc.html` will contain the page with all graphics embedded. This file can be viewed by other browsers.