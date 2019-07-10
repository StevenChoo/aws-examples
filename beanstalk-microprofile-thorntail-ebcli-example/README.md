# BeanStalk Java Jetty Maven Example

## Prequisitions

* A EC2 key-pair named 'Default'
** https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

## Info

This project is created using:
* https://thorntail.io/generator/
    * selected the MicroProfile dependency
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/java-se-platform.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html

## Instructions

## Notes

* Each environment needs to have a unique name and cname

### Deploy using EB CLI

1. Initialize Beanstalk using the CLI client
```bash
eb init eb-microprofile-thorntail-ebcli-example \
--region eu-west-1 \
--keyname default \
--platform java-8 \
--tags Name=BeanstalkMicroprofileThorntailEbcliExample
```

2. Create environment and deploy application
```bash
eb create eb-microprofile-thorntail-ebcli-example \
--branch_default \
--cname eb-microprofile-thorntail-ebcli-example \
--instance_type t2.micro \
--keyname default \
--platform java-8 \
--process \
--region eu-west-1 \
--scale 1 \
--tags Name=BeanstalkMicroprofileThorntailEbcliExample \
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
