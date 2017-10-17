# Spring-ldap-demo
This is sample project for simple spring security with ldap.

## How to run
### Create docker image
Run following command

```
sh ./create-docker-image.sh
```

### Run docker containers
Run following command, then you can see apacheds and ldap-demo running.

```
docker-compose -f docker-compose.yml up
```

To see apacheds and ldap-demo running, run following command

```
docker ps
```

```
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
6c17d2ab297b        ryukato/ldap-demo   "java -Djava.secur..."   6 minutes ago       Up 5 seconds        0.0.0.0:8080->8080/tcp   ldap-demo
24c381089c39        h3nrik/apacheds     "/run.sh"                21 minutes ago      Up 5 seconds        0.0.0.0:389->10389/tcp   apacheds
```

### Add ldap entries
Run following command to add entries to apache ds, which is ldap server

```
sh ./create-test-ldap-entries.sh
```


### Check login
To check ldap-demo is running correctly, you need to get the ip address of the vm. it probably 192.168.99.100, but it may be different. So run following command and check the ip address of the default vm.

```
docker-machine ls
```

After that, open brower and open the url "[ip-address]:8080".
Put the "test" for both username and password.

if everything is working fine, then you're gonna see "Welcome to home page"
