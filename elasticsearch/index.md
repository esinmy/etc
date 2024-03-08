## Curl

Remove all indexes:
```
curl -X DELETE -u <user>:<password> "localhost:9200/_all?pretty"
```

Remove specific index (my_index):
```
curl -X DELETE -u <user>:<password> "localhost:9200/my_index?pretty"
```

Remove heaviest indexes containing a specific word:
```
 curl -XGET -u  <user>:<password> "http://localhost:9200/_cat/shards?v" | sort -n -r -k6 | grep nexusperth-hub | awk '{print $1}' | xargs -I{} curl -X DELETE -u  <user>:<password> "http://localhost:9200/{}" 
```

Reference:
- [Delete index API](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-delete-index.html#delete-index-api-request)
- [Delete index API](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-delete-index.html#delete-index-api-request)

## Kibana Dev Tools Console


Get overview status:
```
GET _cluster/health?pretty
```

Get current settings:
```
GET /_cluster/settings
```

List shards:
```
GET _cat/shards?h=index,shards,state,prirep,unassigned.reason 
```

Reducing the number of replicas to zero for the indexes with UNASSIGNED shards:
```
PUT /*/_settings
{
 "index" : {
  "number_of_replicas":0
 }
}
```

Changing the shard max number per node:
```
PUT /_cluster/settings
{
    "persistent" : {
        "cluster.max_shards_per_node" : 2000
    }
}
```

Changing the shard max number per node (transient, it is not clear yet when exactly this applies):
```
PUT /_cluster/settings
{
  "transient": {
	"cluster.routing.allocation.total_shards_per_node": 2000
  }
}
```