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


