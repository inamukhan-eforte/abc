# MongoDB

The [MongoDB](https://www.mongodb.com/) adaptor is capable of reading/tailing collections and receiving data for inserts.

Here is how a configuration file looks like

```ini
src_type=mongodb
src_uri=mongodb://user:pass@SERVER:PORT/DBNAME
tail=false

dest_type=elasticsearch
dest_uri=APP_NAME
# dest_uri=https://USER:PASSWORD@SERVER/INDEX
```

### Notes

For **tailing** to work, the user accessing the database will need to have `oplog` access. 
An admin user should have oplog access by default though if you are using a mongo database from an third-party provider like 
[mlab](https://mlab.com), this might not be the case. It is best to contact provider's support team in this case.
Also, you can see the provider docs for how to get `oplog` access.
Here is the [doc for mlab](http://docs.mlab.com/oplog/).