# Cloudformation Wordpress AWS provided

## Create stack (without parameters provided)
```bash
aws cloudformation create-stack \
--stack-name wordpress-aws-provided-example \
--template-url https://s3-us-west-2.amazonaws.com/cloudformation-templates-us-west-2/WordPress_Single_Instance.yaml
```

give

```bash
when calling the CreateStack operation: Parameters: [KeyName, DBPassword, DBUser, DBRootPassword] must have values
```

## Create stack (with parameters provided)
```bash
aws cloudformation create-stack \
--stack-name wordpress-aws-provided-example \
--template-url https://s3-us-west-2.amazonaws.com/cloudformation-templates-us-west-2/WordPress_Single_Instance.yaml \
--parameters  \
ParameterKey=KeyName,ParameterValue=default \
ParameterKey=DBPassword,ParameterValue=test1234 \
ParameterKey=DBUser,ParameterValue=steven \
ParameterKey=DBRootPassword,ParameterValue=test1234 \
ParameterKey=InstanceType,ParameterValue=t2.micro
```

## Delete stack
aws cloudformation delete-stack help

