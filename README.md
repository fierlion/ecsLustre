# ecsLustre
Resources for using ecs with lustre fs

## To create Cloud Formation Stack
To create an ECS cluster (configurable) within a vpc, 2 azs and subnets, as well
as all requisite security groups, IAM roles/profiles and the Lustre fs
You'll need the latest ecs-optimized (AL2) AMI ID for your region, and a valid
key-pair to ssh into the instance.

with these, run the following commands:

```
cd cloudformation
aws cloudformation create-stack --stack-name <stackName> \
        --template-body file://amazon-ecs-lustre.json \
        --parameters ParameterKey=KeyName,ParameterValue=<keyPairName> \
        ParameterKey=AmiId,ParameterValue=<ecsOptimizedAmiId> \
        ParameterKey=InstanceType,ParameterValue=<ec2InstanceType> \
        --capabilities CAPABILITY_IAM --region <region> 
```
