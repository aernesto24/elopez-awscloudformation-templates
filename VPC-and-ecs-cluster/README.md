# Cloudformation Template for TEST INFRASTRUCTURE CREATION

This cloudformation template will create a VPC with:
    - 2 Public subnets (where ecs cluster lives)
    - 2 Private subnets (can be used for RDS Databases)
    - 1 ECS Cluster with autoScaling on public subnets 

The idea is to use this cluster for testing purpose

To launch the template:

1. Modify the ClientIP with yor public IP so the Security Groups could connect only with you

2. change directory to the directory where your template is located

3. Launch the template using the following command

```bash
aws cloudformation --profile <your profile> --region=<region-to-deploy> create-stack --stack-name architecture-test --template-body file://./vpc-and-ecs-cluister.yml --capabilities CAPABILITY_IAM
```

4. you can update your stack using:

```bash
aws cloudformation --profile <your profile> --region=<region-to-deploy> create-stack --update-name architecture-test --template-body file://./vpc-and-ecs-cluister.yml --capabilities CAPABILITY_IAM
```