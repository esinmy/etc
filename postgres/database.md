## Dropping

Drop databases:
```
drop database "Database_1"; drop database "Database_2";
```

Drop all databases
```
SELECT 'DROP DATABASE ' || quote_ident(datname) || ';' FROM pg_database WHERE datistemplate=false \gexec
```

## Backup and restore

Backup all databases:
```
PGPASSWORD=<password> pg_dumpall -U <user> -h <ip_address_or_domain_name> > backup_file.sql
```

Restore from backup:
```
psql -f backup_file.sql
```

### Upgrade

Check existing Postgres versions:

```
dpkg -l | grep ii | cut -d" " -f3 | grep postgresql
```

Upgrade the existing Postgres (let's say upgrade version 13 to version 15):
```
pg_upgradecluster 13 main
```

Stop the older one and run the new one:
```
service postgresql@13-main stop
service postgresql@15-main start
```

Verify Postgres statuses:
```
pg_lsclusters
```

