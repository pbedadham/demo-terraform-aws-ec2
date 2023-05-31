# Demo Terraform AWS EC2 instance 
Demos of AWS EC2 resource creation with Terraform IAC

# Prerequisites
To follow this Demos, you will need

- The [Terraform CLI][def] (1.2.0+) installed .
- The [AWS CLI][def2] installed.
- Free [AWS account][def3] and [associated credentials][def4] that allow you to create resources.

# Terraform configuration of EC2 instance
```touch m**a**in.tf```

Copy and paste the below content to main.tf file

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

Initialize the directory

```
terraform init
```

Format and validate the configuration

```
terraform fmt
➜  demo-terraform-aws-ec2 git:(main) ✗ cat ../../README.md 
# Demo Terraform AWS EC2 instance 
Demos of AWS EC2 resource creation with Terraform IAC

# Prerequisites
To follow this Demos, you will need

- The [Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) (1.2.0+) installed .
- The [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) installed.
- Free [AWS account](https://aws.amazon.com/free) and [associated credentials](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html) that allow you to create resources.

# Terraform configuration of EC2 instance
```touch main.tf```

Copy and paste the below content to main.tf file

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

Initialize the directory

```
terraform init
```

Format and validate the configuration

```
terraform fmt
```
```
terraform validate
```
```
terraform plan
```
Create infrastructure

```
terraform apply
```

# Destroy
To destroy the EC2 instance which you created
```
terraform destroy
```
