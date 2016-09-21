# docker-datastore-integration

Example showing running tests against docker datastore

## Usage

[docker-compose.yml](docker-compose.yml) defines a container configuration to start a datastore container called `mydatastore`.  We can start it with  
```bash
docker-compose up mydatastore
``` 
and optionally add a `-d` argument to background the container.

[docker-compose.yml](docker-compose.yml) also defines a container configuration called `mytest` to test that datastore is working properly.  It will automatically start `mydatastore` if it is not already running, and can be run with
```bash
docker-compose run mytest
``` 
If the test fails, it may be because `mydatastore` was just started and google datastore needs time to startup.  Try running it again.
You can mitigate this by explicitly running the `docker-compose up mydatastore` before running `docker-compose mytest`.  

#### Don't forget to cleanup!
```bash
docker-compose down --remove-orphans
```

## References:
 - [docker-compose.yml reference](https://docs.docker.com/compose/compose-file/)
