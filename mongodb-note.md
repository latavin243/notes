## Download and Install
1. https://www.mongodb.com/download-center/community
2. Download `server` & `shell` deb package and install

## start mongodb
```bash
sudo service mongodb start
```

### enter mongodb from shell
```bash
mongo
```

## CRUD
```bash
# db name e.g. person
# use db
use person

# create
db.person.save({username: "aa", age: 10})
db.person.insertOne(
	{
		name: "bb",
		age: 20,
		status: "alive"
	}
)

# read
db.person.find()
db.person.find().pretty()

# update
db.person.updateMany(
	{age: {$lt: 18}},
	{$set: {age: 18}}
)

# delete many
db.person.deleteMany(
	{age: {$lt: 19}}
)
```

## Use MongoDB in Golang
```bash
go get -v go.mongodb.org/mongo-driver/mongo
```