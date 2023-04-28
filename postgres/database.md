Drop databases:
```
drop database "Database_1"; drop database "Database_2";
```

Drop all databases
```
SELECT 'DROP DATABASE ' || quote_ident(datname) || ';' FROM pg_database WHERE datistemplate=false \gexec
```