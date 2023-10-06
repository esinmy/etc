# Drop all schemas

```
do
$body$
declare
    f_rec record;
begin
    
    for f_rec in 
        SELECT schema_name::text
        FROM information_schema.schemata
        where schema_name not in ('public','cron','information_schema','pg_catalog')
    loop 
        execute 'DROP SCHEMA ' || f_rec.schema_name || ' CASCADE';
    end loop;   
    
end;
$body$
language 'plpgsql';
```