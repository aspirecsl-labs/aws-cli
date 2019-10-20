# AWS CLI Command Reference

**aws configure** 
- sets up aws cli 
- requires: access key, secret access key, AWS Region, and output format `(default: json)`

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
