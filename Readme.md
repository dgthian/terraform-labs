## First Lab Terraform

## Create directory 

mkdir learn-terraform-get-started-aws

## Create main.tf file 
touch main.tf

## Check config AWS
aws configure list

## Add configuration for Providers, Datasources and Resources

## Format Configuration
terraform fmt

## Initialisation workspace
terraform init

## Validate configuration
terraform validate

## Create Infrastructure 
terraform apply

## Inspect state
terraform state list

## Print out entire workspace
terraform show

## Delete all resources created
terraform destroy

## Check name AMI in specific region

```sh
   aws ec2 describe-images \
    --owners 099720109477 \
    --filters \
        "Name=name,Values=ubuntu/images/hvm-ssd-gp3/ubuntu-noble-24.04-amd64-server-*" \
        "Name=state,Values=available" \
        "Name=architecture,Values=x86_64" \
    --query 'sort_by(Images, &CreationDate)[-1].[ImageId,Name,CreationDate]' \
    --output table \
    --region us-east-1
    ```

## Get default region
```sh
   aws configure get region
   ```
## My first ec2 instance launched from terraform on 23 April 2026 at 04:16