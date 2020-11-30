# MySQL
By default, the addon stores the damage logs for previous rounds in the built-in SQLite table that comes with every Garry's Mod server.<br>
You can choose to store this information in a MySQL table instead, in order to access the logs from outside of the server (E.g. from a website).


## Install MySQLOO
In order to talk to a MySQL database, this addon requires the MySQLOO module.<br>
Follow the [install instructions](https://github.com/FredyH/MySQLOO#install-instructions) to add it to your server.

## Configuring your MySQL connection
The MySQL connection information is set via a lua configuration file: `lua/damagelogs/config/mysqloo.lua`<br>
The current version of this file can be found here - [tttdamagelogs/lua/damagelogs/config/mysqloo.lua](https://github.com/BadgerCode/tttdamagelogs/blob/master/lua/damagelogs/config/mysqloo.lua)


## Enabling logging to MySQL
Once you have set up your MySQL connection, enable logging to MySQL via the addon's configuration file - `lua/damagelogs/config/config.lua`.

Find the following line:<br>
```lua
Damagelog.Use_MySQL = false
```

And change this to:<br>
```lua
Damagelog.Use_MySQL = true
```
