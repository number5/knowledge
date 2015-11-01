# AWS CLI

## Getting the latest official Ubuntu Trusty x86_64 hvm-ssd EBS AMI id

```
aws ec2 describe-images \
    --region <your region> \
    --owners 099720109477 \
    --filters Name=root-device-type,Values=ebs \
              Name=architecture,Values=x86_64 \
              Name=name,Values='*hvm-ssd/ubuntu-trusty-14.04*' \
    --query 'sort_by(Images, &Name)[-1].ImageId' \
    --output text
```

In above example:
  - `099720109477` is Canonical/Ubuntu AWS account owner id
  - replace `<your region>` with your region, e.g. `ap-southeast-2`
  - `--query` accept JMESPATH expression, see more at http://jmespath.org/tutorial.html

Refs:
  - http://opensourceconnections.com/blog/2015/07/27/advanced-aws-cli-jmespath-query/
  - https://alestic.com/2013/11/aws-cli-query/
