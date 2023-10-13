### terraform-OSX

--------------

1 . terraform CLI

### [Terraform CLI ](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

#### Install Terraform
--------------


```
brew tap hashicorp/tap
```

```
brew install hashicorp/tap/terraform
```

```
brew update
```

```
brew upgrade hashicorp/tap/terraform
```
#### Verify the installation


```
terraform -help
```

#### Enable tab completion

```
touch ~/.bashrc
```

```
terraform -install-autocomplete
```


#### Write configuration

```
mkdir learn-terraform-aws-instance
```

```
cd learn-terraform-aws-instance
```

```
touch main.tf
```

```
code .
```

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


#### Initialize the directory


```
terraform init
```

```
terraform fmt
```

```
terraform validate
```

```
terraform apply
```

```
terraform show
```

```
terraform state list
```

#### Destroy infrastructure

```
terraform destroy
```

2 . AWS CLI

### [AWS CLI ](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

```
export AWS_ACCESS_KEY_ID=
```

```
export AWS_SECRET_ACCESS_KEY=
```
#### Install or update the AWS CLI


```
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
```

```
sudo installer -pkg AWSCLIV2.pkg -target /
```

```
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
```


```
sudo installer -pkg ./AWSCLIV2.pkg -target /
```

```
which aws
```

```
aws --version
```