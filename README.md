## Docker image packaging for Apache Zookeeper Based on Tencent KonaJDK

### about tencent konajdk
You can learn more about tencent konajdk through [konajdk wiki](https://github.com/Tencent/TencentKona-11/wiki).

### how to user this image

#### Start a Zookeeper server instance
```
$ docker run --name some-zookeeper --restart always -d yuezht/zookeeper-konajdk:3.8.0
```

This image includes EXPOSE 2181 2888 3888 8080 (the zookeeper client port, follower port, election port, AdminServer port respectively), so standard container linking will make it automatically available to the linked containers. Since the Zookeeper "fails fast" it's better to always restart it.


#### Connect to Zookeeper from an application in another Docker container
```
$ docker run --name some-app --link some-zookeeper:zookeeper-konajdk -d application-that-uses-zookeeper
```



