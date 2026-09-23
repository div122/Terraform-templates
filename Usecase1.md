# Create Ec2 resource with help of terraform.

```
# Terraform Settings Block
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      #version = "~> 3.21" # Optional but recommended in production
    }
  }
}

# Provider Block
provider "aws" {
  profile = "default" # AWS Credentials Profile configured on your local desktop terminal  $HOME/.aws/credentials
  region  = "us-east-1"
}

# Resource Block
resource "aws_instance" "ec2demo" {
  ami           = "ami-04d29b6f966df1537" # Amazon Linux in us-east-1, update as per your region
  instance_type = "t2.micro"
}
```

if we use below terraform commands to create Ec2 resource with help of terraform.

```
terraform init
terraform validate
terraform plan
terraform apply
```

**Verify the EC2 Instance in AWS Management Console:**
- Go to AWS Management Console -> Services -> EC2
- Verify newly created EC2 instance

**Destroy Infrastructure**

terraform destroy # Destroy EC2 Instance

rm -rf .terraform*   # Delete Terraform files 
rm -rf terraform.tfstate*

