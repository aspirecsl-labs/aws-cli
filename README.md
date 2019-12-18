# AWS CLI Command Reference

**aws configure** 
- sets up aws cli 
- requires: access key, secret access key, AWS Region, and output format `(default: json)`

**aws iam list-users**
- lists the IAM users for the AWS account

**aws ec2 describe-images**
- describes AWS EC2 images available to you
- *--filter* - filters the results (to filter on RHEL images:- `--filer "Name=description, Values=*RHEL*"`)
- *--query* - queries the values from the results (for example:- `--query 'Images[*].[CreationDate, ImageId]'`)
- *--output* - specifies the output format (for example:- `--output text`)

**aws ec2 describe-vpcs**
- describes the _virtual private clouds_ available

**aws ec2 create-security-group**
- creates a security group for a _VPC_
- requires: group name, description, and vpc_id

**aws ec2 authorize-security-group-ingress**
- configures ingress _(inbound)_ traffic rules
- `--port` specifies the port to allow the traffic
- `--protocol` specifies the protocol to allow (for example:- tcp)
- `--cidr` specifies the allowed ip (0.0.0.0/0 allows traffic from everywhere)

**aws ec2 create-key-pair**
- generates an SSH key pair at EC2
- `--key-name` specifies the name of the key
- the private key of the SSH key pair is specified as the _KeyMaterial_ in the command output

**aws ec2 describe-key-pairs**
- describes the specified key pair or all key pairs
- `--key-name` specifies a key pair name

**aws ec2 run-instances**
- runs (creating if absent) an EC2 instance
- `--instance-type` specifies the instance type (for example:- t2.micro)
- `--key-name` specifies the SSH key pair name to use for this instance
- `--security-group-ids` specifes the security group ids to use for this instance
- `--image-id` specifies the machine image id to use for this instance _(obtained via `aws ec2 describe-images` command)_
