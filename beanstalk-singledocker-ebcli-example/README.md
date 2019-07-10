# BeanStalk Singledocker NodeJS EBCLI example

A NodeJS Express application docker example running with Beanstalk

## Info

This example is based on the following AWS provided [example](https://nodejs.org/de/docs/guides/nodejs-docker-webapp/).

## Notes
* Dockerrun.aws.json port mapping not needed. If not provided it will automatically use the exposed port in the DockerFile

* 
    ```json
      {
          "Image": {
            "Name": "janedoe/image",
            "Update": "true"
          }
      }
    ```
    Only needed when using a Docker image from a registry. When omitted it will used the provided DockerFile to build the image



## Instructions

### Init Beanstalk
```bash
eb init eb-singledocker-nodejs-ebcli-example \
--region eu-west-1 \
--keyname default \
--platform docker \
--tags Name=EBSingleDockerNodeJSEBCLIExample
```

### Test docker container locally
```bash
eb local run --port 5000
```

### Open docker container running locally
```bash
eb local open
```

### Deploy using docker
```bash
eb create eb-singledocker-nodejs-ebcli-example \
--cname eb-singledocker-nodejs-ebcli-example \
--instance_type t2.micro \
--keyname default \
--platform docker \
--process \
--region eu-west-1 \
--scale 1 \
--tags Name=EBSingleDockerNodeJSEBCLIExample \
--timeout 5
```

### Terminate
```bash
eb terminate --region eu-west-1
```
