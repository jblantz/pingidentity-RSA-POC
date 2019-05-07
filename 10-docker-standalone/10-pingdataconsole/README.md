# Running PingDataConsole Image
Demonstrate how to stand up a PingDataConsole container that can talk to other
PingData components (i.e. PingDirectory, PingDataAccess)

## How to startup a PingDataConsole container...

### Using docker run

The following example will create a docker network, run the PingDataConsole
and open up a webpage to the conosole.

```Bash
docker network create pingnet

docker run -d \
       --network pingnet \
       --publish 8080:8080 \
       --name pingdataconsole \
       pingidentity/pingdataconsole
       
open http://localhost:8080/admin-console
```

If you are using the PingDirectory container from these standalone images, you should be able to login with

```
     Server: pingdirectory:636
   Username: administrator
   Password: 2FederateM0re
```