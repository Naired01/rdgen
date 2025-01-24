## 🚀 RDGEN
Is a RustDesk client generator to use with your self-hosted rustdesk server.

## The client generator
Is currently hosted [here](https://mass.selfip.com/). 

If you would like to host the generator yourself, see [here](setup.md)

---

### This client generator is currently integrated into my rustdesk [api server](https://github.com/bryangerlach/rustdesk-api-server), which is a fork of [rustdesk-api-server](https://github.com/kingmo888/rustdesk-api-server). If you are running my api server, then you will still need to fork RDGEN and go through the setup process, but you won't need to actually run the rdgen server.

---

### Docker

To use **RDGEN** with Docker, you need to run the following command to build the project.
1. **Build the Docker image**

```bash
docker build -t rdgen .
```
2. **Run the Docker container**

```bash
docker run -d -p 3721:3721 undb
```
---
You can also use `docker-compose.yml` and a `.env` file to load environment variables.


### docker-compose.yml

```bash
services:
 rdgen:
   image: rdgen
   container_name: rdgen
   ports:
     - "8005:8000"
   environment:
     DEBUG: ${DEBUG}
     GENURL: ${GENURL}
     GHBEARER: ${GHBEARER}
     GHUSER: ${GHUSER}
   env_file:
     - .env
   volumes:
      - ./data-t:/app/data-t
      - ./ws:/app/ws
      - ./db:/app/db
```
### .env
```bash
GHUSER='github profile'
GHBEARER='github token'
DEBUG="true"
```

### Run the Docker container
```bash
docker-compose up -d
```
