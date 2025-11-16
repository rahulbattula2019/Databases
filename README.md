# Databases

1. Create the `docker-compose.yml` file:

   ```bash
   touch docker-compose.yml
   ```

2. Add the following content to `docker-compose.yml`:

   ```yaml
   version: '3'
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
   ```

3. Start the Oracle XE container:

   ```bash
   docker compose up -d
   ```

4. Check running containers:

   ```bash
   docker ps
   ```

5. Verify the database is ready:

   ```bash
   docker logs oracle-xe | grep "DATABASE IS READY"
   ```

6. Enter the Oracle container:

   ```bash
   docker exec -it oracle-xe bash
   ```

7. Connect to Oracle using SQL\*Plus:

   ```bash
   sqlplus system/4869@XEPDB1
   ```
