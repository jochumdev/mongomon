Munin Plugins for MongoDB
============

Plugins
----------
* mongo_collcount   : Count of documents in multible collections per db
* mongo_collsize    : Index, storage and data size per collection
* mongo_indexsize   : Index sizes of all collections in a db

Requirements
-----------
* pymongo 2.0+
* MongoDB 1.4+

Installation
-----------
Follow the following steps to install these plugins on your munin-node

- Copy `mongo_collcount` and `mongo_indexsize` into `/etc/munin/plugins`
- Copy the wildcard plugin `mongo_collsize` to `/etc/munin/plugins/mongo_collsize_<your collection>`, where `<your collection>` means the name of the collection you want to monitor, this is case sensetive!

- Edit `/etc/munin/plugin-conf.d/plugins`, and add the following:

        [mongo_*]
        user nobody
        env.HOST <mongodbs ip>
        env.PORT 27017
        env.DB <the database you want to monitor>

- At last restart munin-node:
    
        sudo /etc/init.d/munin-node restart

