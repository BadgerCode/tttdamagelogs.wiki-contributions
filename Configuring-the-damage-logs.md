# Configuring the damage logs
Most of the configuration is done through a lua configuration file: `lua/damagelogs/config/config.lua`<br>
The current version of this file can be found here - [tttdamagelogs/lua/damagelogs/config/config.lua](https://github.com/BadgerCode/tttdamagelogs/blob/master/lua/damagelogs/config/config.lua)

<br>

> **Note**: When updating your copy of the damage logs addon, make a backup of your copy of the configuration files!
> 
> Otherwise, you may accidentally overwrite your changes to your configuration files.


<br>


# MySQL
By default, the addon stores the damage logs for previous rounds in the built-in SQLite table that comes with every Garry's Mod server.<br>
You can choose to store this information in a MySQL table instead, in order to access the logs from outside of the server (E.g. from a website).


The MySQL connection information is set via a lua configuration file: `lua/damagelogs/config/mysqloo.lua`<br>
The current version of this file can be found here - [tttdamagelogs/lua/damagelogs/config/mysqloo.lua](https://github.com/BadgerCode/tttdamagelogs/blob/master/lua/damagelogs/config/mysqloo.lua)
