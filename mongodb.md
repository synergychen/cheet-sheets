# MongoDB Cheet Sheet

## Basic

```
# show databases
show dbs
# use database
use <db_name>
# show collections
show collections
# find all documents of a collection
db.<collection_name>.find()
```

## List Collection Sizes

List collection sizes in descending order.

```bash
function getReadableFileSizeString(fileSizeInBytes) {
    var i = -1;
    var byteUnits = [' kB', ' MB', ' GB', ' TB', 'PB', 'EB', 'ZB', 'YB'];
    do {
        fileSizeInBytes = fileSizeInBytes / 1024;
        i++;
    } while (fileSizeInBytes > 1024);

    return Math.max(fileSizeInBytes, 0.1).toFixed(1) + byteUnits[i];
};
var collectionNames = db.getCollectionNames(), stats = [];
collectionNames.forEach(function (n) { stats.push(db.getCollection(n).stats()); });
stats = stats.sort(function(a, b) { return b['size'] - a['size']; });
for (var c in stats) { print(stats[c]['ns'] + ": " + getReadableFileSizeString(stats[c]['size']) + " (" + getReadableFileSizeString(stats[c]['storageSize']) + ")"); }
```

## List Collections From Shell

List collections from shell

```bash
mongo <db_name> --quiet --eval 'db.getCollectionNames()'
```

## Allow Reads on Secondary/Slave

Let mongo know we are going to read on secondaries

```bash
rs.slaveOk()
```

## Find Master Node From Slave

The value of `primary` key from returned result is master node.

```
db.runCommand("ismaster")
```

## Migrate Data

```
# find target db
mongo
show dbs
# migrate with script
mongo localhost/<db_name> migrate-script.js
```

In `migrate-script.js`

```
db.<source-table-name>.find().forEach(function (sourceRecord) {
    const targetRecord = {...};
    db.<target-table-name>.insert(targetRecord);
});
```
