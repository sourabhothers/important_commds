# important_commds

# MongoDB

starting instances of replica set
maximum 50

* --replSet option should have same name
## sudo mongod --port 27017 --dbpath "/var/lib/mongodb-data/db0" --replSet rs0 --bind_ip "localhost"
## sudo mongod --port 27018 --dbpath "/var/lib/mongodb-data/db1" --replSet rs0 --bind_ip "localhost"
## sudo mongod --port 27019 --dbpath "/var/lib/mongodb-data/db2" --replSet rs0 --bind_ip "localhost"

- go in mongoshell
- rs.status()
- rs.initiate()
- rs.add("localhost:27018")
- rs.add("localhost:27019")
- rs.status()

## Backup all databases
mongodump --uri="mongodb://localhost:27017" --out "output/directoryName"

## Restore
- 2nd optio is input_directory with any args name
mongorestore --uri="mongodb://localhost:27017" "output/directoryName"

## restore to replicasSet
-  mongorestore --uri="mongodb://127.0.0.1:27017,127.0.0.1:27018,127.0.0.1:27019/?replicaSet=rs0" "/tmp/mongodb-backup"
