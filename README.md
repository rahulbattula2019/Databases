# Databases

1. touch docker-compose.yml

2. version: '3'
services:
  oracle:
    image: gvenzl/oracle-xe
    container_name: oracle-xe
    environment:
      ORACLE_PASSWORD: MyRootPassword123
      ORACLE_DISABLE_ASYNCH_IO: true
    ports:
      - "1521:1521"
      - "5500:5500"

3. docker compose up -d

4. docker ps

5. docker logs oracle-xe | grep "DATABASE IS READY"

6. docker exec -it oracle-xe bash
7. sqlplus system/4869@XEPDB1

