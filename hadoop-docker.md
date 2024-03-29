### clone https://github.com/big-data-europe/docker-hadoop
```git clone https://github.com/big-data-europe/docker-hadoop```

### enter to directory
```cd docker-hadoop```

### change docker-compose.yml file because only 1 datanode is running after starting the cluster
```https://gist.github.com/themonster2015/35cf4252893cdcc831e79e76deb95cdb```

### To deploy an example HDFS cluster, run:
```docker-compose up```

### Run docker network inspect on the network (e.g. dockerhadoop_default) to find the IP the hadoop interfaces are published on. Access these interfaces with the following URLs:
```
Namenode: http://<dockerhadoop_IP_address>:9870/dfshealth.html#tab-overview
History server: http://<dockerhadoop_IP_address>:8188/applicationhistory
Datanode: http://<dockerhadoop_IP_address>:9864/
Nodemanager: http://<dockerhadoop_IP_address>:8042/node
Resource manager: http://<dockerhadoop_IP_address>:8088/
```

### Gunakan localhost / IP  dengan port diatas untuk melihat interface namenode
Namenode ```localhost:9870/dfshealth.html#tab-overview```

### masuk ke Datanode
```docker exec -it datanode bash```

### lihat hadoop version
```hadoop version```

### list all 
```hadoop fs -ls /```

### create folder
```hadoop fs -mkdir /newdata```

### create new file
```echo hai >> hai.txt```

### copy to HDFS
```hadoop fs -put hai.txt /newdata```

### cat file
```hadoop fs -cat /newdata/hai.txt```

### remove file
```hadoop fs -rm /newdata/hai.txt```

### remove folder
```hadoop fs -rmr /newdata```


### stop docker hadoop
```docker-compose down```
