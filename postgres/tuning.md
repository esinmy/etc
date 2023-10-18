# Tuning Your PostgreSQL Server

## Get all settings
```
SELECT * FROM pg_setting;
```

## max_connections
max_connections sets exactly that: the maximum number of client connections allowed. The default is typically 100 connections.
Get and set:
```
show max_connections;
ALTER SYSTEM SET max_connections TO '450';
```

## shared_buffers
The shared_buffers configuration parameter determines how much memory is dedicated to PostgreSQL to use for caching data. The default is 128MB.
It’s a good rule of thumb to allocate no more than 25% of the available memory for this.
Get and set:
```
show shared_buffers;
ALTER SYSTEM SET shared_buffers TO '4000MB';
```

## maintenance_work_mem
Specifies the maximum amount of memory to be used by maintenance operations, such as VACUUM, CREATE INDEX, and ALTER TABLE ADD FOREIGN KEY. The default is 64MB.
Larger settings might improve performance for vacuuming and for restoring database dumps.
Get and set:
```
show maintenance_work_mem;
ALTER SYSTEM SET maintenance_work_mem TO '500MB';
```

References:

* https://wiki.postgresql.org/wiki/Tuning_Your_PostgreSQL_Server
* https://stackoverflow.com/questions/30778015/how-to-increase-the-max-connections-in-postgres
* https://postgresqlco.nf/doc/en/param/shared_buffers/