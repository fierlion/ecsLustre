# ecsLustre
Resources for using ecs with lustre fs

## To create Cloud Formation Stack
To create an ECS cluster (configurable) within a vpc, 4 azs and subnets, as well
as all requisite security groups, IAM roles/profiles and the Lustre fs
You'll need a valid key-pair to ssh into the instance.

```
cd cloudformation
aws cloudformation create-stack --stack-name ecsLustreTestStack \
          --template-body file://amazon-ecs-lustre.yml \
          --parameters ParameterKey=KeyName,ParameterValue=<keyPairName> \
          --region <region> \
          --capabilities CAPABILITY_IAM
```
