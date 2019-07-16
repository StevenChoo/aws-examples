# Simple EC2 CloudFormation Template

## Create Stack
```bash
aws cloudformation create-stack --stack-name simple-ec2-example \
--template-body file://./simple-ec2-example.yaml \
--region eu-west-1
```

## Update Stack

Change:
```yaml
#Tags:
      #  -
      #    Key: "Name"
      #    Value: "simple-ec2-cloudformation-template-instance"
```

to

```yaml
Tags: 
    -
      Key: "Name"
      Value: "simple-ec2-cloudformation-template-instance"
```

Run:
```bash
aws cloudformation update-stack --stack-name simple-ec2-example \
--template-body file://./simple-ec2-example.yaml \
--region eu-west-1
```

#Delete Stack
```bash
aws cloudformation delete-stack --stack-name simple-ec2-example
```

#Deploy one command for create / update
```bash
# Note that the template parameter is --template and  file:// is omitted from the file url 
aws cloudformation deploy --stack-name simple-ec2-example \
--template ./simple-ec2-example.yaml \
--region eu-west-1
```
