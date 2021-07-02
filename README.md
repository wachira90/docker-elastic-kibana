# docker-elastic-kibana

docker-elastic-kibana cluster

## url 

```
http://localhost:9200

http://localhost:5601
```


## check node
```
http://localhost:9200/_cat/nodes?v=true&pretty
```

```
ip         heap.percent ram.percent cpu load_1m load_5m load_15m node.role   master name
172.23.0.3            9          69  18    3.05    1.13     0.40 cdfhilmrstw *      es03
172.23.0.4           18          69  18    3.05    1.13     0.40 cdfhilmrstw -      es01
172.23.0.2           14          69  18    3.05    1.13     0.40 cdfhilmrstw -      es02
```

## linux

The vm.max_map_count setting should be set permanently in /etc/sysctl.conf:
```
grep vm.max_map_count /etc/sysctl.conf
vm.max_map_count=262144
```
## To apply the setting on a live system, run:

```
sysctl -w vm.max_map_count=262144
```

## Configuration files must be readable by the elasticsearch user

```
mkdir esdatadir
chmod g+rwx esdatadir
chgrp 0 esdatadir
```

## for more info
```
https://medium.com/machinereading/elasticsearch-%E0%B8%A0%E0%B8%B2%E0%B8%84%E0%B8%A5%E0%B8%B8%E0%B8%A2%E0%B8%AA%E0%B8%99%E0%B8%B2%E0%B8%A1-%E0%B8%95%E0%B8%AD%E0%B8%99%E0%B8%97%E0%B8%B5%E0%B9%88-2-4979e03b8e02
```
