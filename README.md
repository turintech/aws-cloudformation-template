# AWS Cloud Formation Template
AWS CloudFormation simplifies provisioning and management on AWS. You can create templates for the service or application architectures you want and have AWS CloudFormation use those templates for quick and reliable provisioning of the services or applications (called “stacks”). You can also easily update or replicate the stacks as needed.

## Prerequisites
- docker
- [taskcat](https://github.com/aws-ia/taskcat) (for testing)

## Examples
- Run template `taskcat deploy run`
- Delete stack template `taskcat delete evoml`
- delete all taskcat stacks from s3 `for bucket in $(aws s3 ls | awk '{print $3}' | grep tcat-evoml-*); do  aws s3 rb "s3://${bucket}" --force ; done`

## Debug

1. `/var/log/cfn-init-cmd.log`: cfn-init and command output with timestamps
2. `/var/log/cfn-init.log`: cfn-init and command output
3. `/var/log/cloud-init.log`: cloud init logs pertaining to running the commands in user-data
4. `/var/log/cloud-init-output.log`: output from the user-data commands themselves


## References
- https://www.cyberciti.biz/faq/how-to-install-docker-on-amazon-linux-2/
- https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
