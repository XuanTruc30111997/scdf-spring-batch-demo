# Start Spring Cloud Data Flows, Postgres Database, Spring Cloud Skipper
```docker-compose -f ./docker-compose-base.yml -f ./docker-compose-dood.yml up```

## Access Spring Cloud Data Flows Dashboard
http://localhost:9393/dashboard/index.html#/apps

### Register application as task
```http://localhost:{{SCDF-port}}/apps/task/<nameOfTask>?bootVersion=2```
Body:
```
uri=<register url>
    ex: docker:trucnguyen301197/batch-demo-service:1.0.4
```

### List all applications
```
http://localhost:{{SCDF-port}}/apps?search=&type=task&defaultVersion=true&page=0&size=10&sort=name%2CASC
```

### Create task
```
http://localhost:{{SCDF-port}}/tasks/definitions?definition=<app-name>&name=Ahihi-5&description=
```

### Launch task
```
http://localhost:{{SCDF-port}}/tasks/executions/launch?name=<task-name>&arguments=app.<app-name>%3Dsomething112233;Testing112233

arguments = something112233;Testing112233
```