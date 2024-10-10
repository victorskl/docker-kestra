# kestra tute

- https://github.com/kestra-io/kestra
- https://kestra.io/docs/installation/docker-compose

```
docker compose up -d
```

## Create a flow

- Go to http://localhost:8080/ui/flows
- Create using the following hello world logging workflow in yaml
- Execute

```yaml
id: hello_world
namespace: dev

tasks:
  - id: say_hello
    type: io.kestra.plugin.core.log.Log
    message: "Hello, World!"
```

```commandline
curl -s -X POST -H 'Content-Type: multipart/form-data' 'http://localhost:8080/api/v1/executions/dev/hello_world' | jq
```
