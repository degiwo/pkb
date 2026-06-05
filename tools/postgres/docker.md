## Run SQL inside Postgres Docker Container

```bash
docker exec -it <container-name> bash
psql -h localhost -U postgres
select * from information_schema.tables;
```
