# docker

Three Repos for the Debian-kings under the sky,  
Seven for the Centos-lords in their halls of stone,  
Nine for Mortal Web doomed to die,  
One for the Dark Linus on his dark throne  
In the Land of Docker where the Scripts lie.  
One Repo to rule them all, One Repo to find them,  
One Repo to bring them all, and in the dankness bind them,  
In the Land of Docker where the Scripts lie.  

## Example build and push

```bash
docker login
cd medium
docker build --no-cache -t myrostadler/medium:0.0.0 -t myrostadler/medium:latest .
docker push myrostadler/medium:0.0.0 && docker push myrostadler/medium:latest
```

## Testing

**TODO: automate tests**

### Testing requirements

1. **Have your local development environment set up so you know how to hit the docker container.**
The setup I have on MacOS is having docker, docker-compose, and docker-machine installed via homebrew. 
So to get the container IP I issue the command `docker-machine ip`  (this is different in other docker provisioners e.g. Docker Desktop for Mac / Windows).
I have an entry in `/etc/hosts` that binds this IP to http://localhost.docker so I can use that canonical URL to view whatever I've spun up.

### Testing conventions

1. Tests are in the `.test` directory, in subdirectories with the same name as the directory of the container under test
1. The containers will bind to ports 80 and 443 directly
1. Docker-compose is used to spin up tests, since the intention is to use docker-compose during dev where
the real-world applications of these tests are implemented

### Trivial testing example

#### 1. Spin up the container

```bash
cd ubupache
docker-compose up -d
```

#### 2. Test using a local web browser

http://localhost.docker/test.html - test page is served  
http://localhost.docker/test.php - test PHP is interpreted  
http://localhost.docker/phpinfo.php - verify PHP version  

#### 3. Spin down the container

```bash
docker-compose down
```

