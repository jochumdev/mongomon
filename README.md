Munin Plugins for MongoDB
============

Plugins
----------
* mongo_collcount   : Count of documents in multible collections per db
* mongo_collsize    : Index, storage and data size per collection
* mongo_indexsize   : Index sizes of all collections in a db

Requirements
-----------
* pymongo 1.4+
* MongoDB 1.4+

Installation
-----------
Follow the following steps to install these plugins on your munin-node

- Copy "mongo_collcount" and "mongo_indexsize" into "/etc/mongo/plugins"
- Copy the wildcard plugin "mongo_collsize" to "/etc/mongo/plugins/mongo_collsize_\(you collection>)", where \(your collection\) means the name of the collection you want to monitor, this is case sensetive!

- Edit /etc/munin/plugin-conf.d/plugins, and add the following:

    [mongo_*]
    user nobody
    env.HOST <mongodbs ip>
    env.PORT 27017
    env.DB <the database you wanna watch>

- At last restart munin-node:
    sudo /etc/init.d/munin-node restart

