# VoltDB Example - Running and Using VoltDB with Docker

This project demonstrates how to quickly run a VoltDB instance using Docker, connect to it, and perform basic SQL operations.

## Steps

### 1. Pull and Run VoltDB Docker Image

First, we need to run the VoltDB Docker container.  
I used the [full360/docker-voltdb-ce](https://hub.docker.com/r/full360/docker-voltdb-ce) image, which is the Community Edition.

```bash
docker run -d --name voltdb-test -p 21212:21212 -p 8080:8080 full360/docker-voltdb-ce
```
You can verify the container is running with:
```bash
docker ps
```
Screenshot:

### 2. Connect to the VoltDB Container and Start SQL Command Line

After the container is running, connect to it with:
```bash
docker exec -it voltdb-test bash
```
Then start the VoltDB SQL command line tool:
```bash
sqlcmd
```
Screenshot:

### 3. Create a Table and Insert Data
Inside the SQL command line, you can now create a table and insert data:
```bash
CREATE TABLE kullanici (
    id INTEGER NOT NULL,
    isim VARCHAR(50),
    PRIMARY KEY(id)
);

INSERT INTO kullanici (id, isim) VALUES (1, 'İlker');
```
You will see messages like Command succeeded. and (Returned 1 rows in 0.06s) if everything is correct.

### 4. Query the Data
You can retrieve the data using:
```bash
SELECT * FROM kullanici;
```
This will show your inserted row.

### Summary
	•	Pulled and ran VoltDB Docker container.
	•	Connected to the container and started the SQL command tool.
	•	Created a table and inserted sample data.
	•	Queried the data and confirmed everything worked.
