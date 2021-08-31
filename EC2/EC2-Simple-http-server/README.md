# Basic HTTP Web app based

This template shows how to deploy an EC2 instance with an ubuntu image, grab an app file from s3 and installed on the web server inside the instance

**NOTE** : You can query ubuntu images using the following command:

```bash
aws ssm get-parameters --names \
        /aws/service/canonical/ubuntu/server/20.04/stable/current/amd64/hvm/ebs-gp2/ami-id \
    --query 'Parameters[0].[Value]' --output text
```

You can also change the version to 18.04 or other 

To deploy the template use:

```bash
aws cloudformation --profile <your profile> --region=<region-to-deploy> create-stack --stack-name architecture-test --template-body file://./simple-http-ec2.yml --capabilities CAPABILITY_IAM
```