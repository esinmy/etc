# Memory usage

Open `redis-cli`:
```
# redis-cli
```

Memory command to check the memory usage of the redis server:
```
INFO memory # or MEMORY stats
```

DB size - the total number of stored keys:
```
dbsize
```

Set/get memory limit:
```
config set maxmemory 100mb
config get maxmemory
```

# Key eviction policies

Reference: [Official documentation - Key eviction](https://redis.io/docs/reference/eviction/)

Set/get maxmemory-policy:
```
config get maxmemory-policy 
config set maxmemory-policy allkeys-lru
```