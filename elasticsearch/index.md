Remove all indexes:
```
curl -X DELETE -u <user>:<password> "localhost:9200/_all?pretty"
```

Remove specific index (my_index):
```
curl -X DELETE -u <user>:<password> "localhost:9200/my_index?pretty"
```