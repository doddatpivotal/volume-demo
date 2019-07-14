=============
Persistent Volume Demo
=============

A sample application demonstrating persistent volumes.  This application includes a Concourse CI pipeline for automated deployment

<kbd>![alt-text](https://github.com/azwickey-pivotal/volume-demo/blob/master/ci.png)</kbd>

<kbd>![alt-text](https://github.com/azwickey-pivotal/volume-demo/blob/master/app.png)</kbd>


## How to use

```bash
mvn clean install
cf push --no-start
cf create-service nfs Existing volume-service -c '{"share":"192.168.7.37/export/vol1"}'
cf bind-service volume-demo volume-service -c '{"uid":"1000","gid":"1000"}'
```

## Delete All
```bash
http <URL>/delete_all
```