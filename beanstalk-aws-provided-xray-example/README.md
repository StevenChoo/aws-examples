# BeanStalk Java Jetty Maven Example

## Prequisitions

* A EC2 key-pair named 'Default'
** https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

## Info

This project is based on an AWS provided BeanStalk XRay [example](https://docs.aws.amazon.com/xray/latest/devguide/xray-gettingstarted.html).
For the orginal docs check [the original README.md](README_ORG.md)

Because the instruction provided are for using the Web console, instruction for using the EB CLI are added

## Instructions

## Notes

* Each environment needs to have a unique name and cname

### Deploy using EB CLI

1. Initialize Beanstalk using the CLI client
```bash
eb init scorekeep-api \
--region eu-west-1 \
--keyname default \
--platform java-8 \
--tags Name=scorekeep-api
```

2. Create environment and deploy application
```bash
eb create scorekeep-api \
--cname scorekeep-api \
--instance_type t2.micro \
--keyname default \
--platform java-8 \
--process \
--region eu-west-1 \
--scale 1 \
--tags Name=scorekeep-api \
--timeout 5
```

### Update deployment using EB CLI 
```bash
eb deploy eb-microprofile-thorntail-ebcli-example --region eu-west-1
```

### Terminate deployment using EB CLI
```bash
eb terminate eb-microprofile-thorntail-ebcli-example --region eu-west-1
```

### AWS CLI describe environments
```bash
aws elasticbeanstalk describe-environments
```

### AWS CLI terminate environments
```bash
aws elasticbeanstalk terminate-environment --environment-name eb-microprofile-thorntail-ebcli-example
```
