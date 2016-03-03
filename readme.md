# loopback-component-storage-gridfs

Uses mongoDB [GridFS](https://docs.mongodb.org/manual/core/gridfs/) to manage binary contents of your loopback application.

## Datasource

Add datasource to your datasources.json

```json
"storage": {
   "name": "gridfs",
   "connector": "loopback-component-storage-gridfs",
   "host": "hostname",
   "port": 27017,
   "database": "database",
   "username": "username",
   "password": "password"
 }
```

**username** and **password** are optional

## API

### List containers

    GET /FileContainers

#### Arguments

* none


### Delete container

    DELETE /FileContainers/:containerName

#### Arguments

  * **containerName** - name of container to delete


### List files in container

    GET /FileContainers/:containerName/files

#### Arguments

  * **containerName** - name of container


### Get file information

    GET /FileContainers/:containerName/files/:fileId

#### Arguments

  * **containerName** - name of container
  * **fileId** - id of file


### Delete file

    DELETE /FileContainers/:containerName/files/:fileId

* **containerName** - name of container
* **fileId** - id of file to delete


### Upload files

    POST /FileContainers/:containerName/upload

* **containerName** - name of container


### Download file

    GET /FileContainers/:containerName/download/:fileId

* **containerName** - name of container
* **fileId** - id of file to download
