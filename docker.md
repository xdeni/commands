## DOCKER

#### How Install?
[Rocketseat tutorial](https://www.notion.so/Instalando-Docker-6290d9994b0b4555a153576a1d97bee2#cca124d4118944bc95437577fbeb8450)

Create and init a container (-p before ':' is the local port and after is container port)
- vefify if the port 5434 already in use 
  - (mac): lsof -i :5432
    - to kill (kill -9 'PID')
  - (linux): netstat -ntpl
    - to kill (kill -9 'PID' or service postgresql stop)
 
``` sh
 sudo docker run --name container_name -e POSTGRES_PASSWORD=postgres -p 5432:5432 -d postgres:latest
```

Create POSTGRES table dump using docker.
```sh
 sudo docker exec postgres_last pg_dump -U postgres -t public.column -t public.column -t public.column -a table_name --inserts > dump.sql
```

Entering in a postgres console on container.
``` sh
docker exec -it postgres_last psql -U postgres
```

#### How see logs
docker logs 'nome da imagem'
