"# rm-ticketing-admin" 

basic implementation was done at https://github.com/Roman75/ticketing

here we begin to split each part into separate project to run each in separate docker container (microservice concept will be implemented) 

on your docker host create config file in '/etc/rm-ticketing/admin/config.yaml'

```bash
cd rm-ticketing-admin
docker build --force-rm --no-cache -t rm-ticketing-admin .
docker run --name=rm-ticketing-admin -p 8081:8080 -d -v e:\git\rm-ticketing\rm-ticketing-admin\config.yaml:/app/config.yaml rm-ticketing-admin
cd ..
```

```yaml
# misc
server:
  sleep: 100 # wait for startup in ms

# logging
log:
  logfile: true
  err: true
  info: true
  debug: true
  msg: true
  datePattern: 'yyyy-mm-dd HH:MM:ss'
  colors:
    msg: 'green'
    info: 'blue'
    debug: 'cyan'
    err: 'gray'

# http
http:
  port: 8080
#  domain: 'domain.at'
#   ssl:
#     key: '/etc/ssl/certs/localhost.key'
#     cert: '/etc/ssl/certs/localhost.cert'

```