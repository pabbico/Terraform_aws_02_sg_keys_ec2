### `README.md`

```markdown
# Terraform AWS VPC + EC2 Setup

This project uses Terraform to provision the following infrastructure on AWS:

- Custom VPC
- Public and Private Subnets
- Internet Gateway (IGW)
- NAT Gateway
- Route Tables for public/private traffic
- Security Group for EC2
- Key Pair for SSH access
- EC2 instance in Public Subnet

---

## Project Structure

```

Terraform_aws_02_sg_keys_ec2 % tree
.
├── ec2.tf
├── igw.tf
├── key.tf
├── nat_gateway.tf
├── outputs.tf
├── private_route_table.tf
├── private_subnet.tf
├── provider.tf
├── public_route_table.tf
├── public_subnet.tf
├── region.tf
├── sg.tf
├── terraform.tfvars
├── variable.tf
└── vpc.tf
└── README.md

````

---

## **How to Use**

### 1. Clone the Repository
```bash
git clone https://github.com/pabbico/Terraform_aws_02_sg_keys_ec2.git
cd Terraform_aws_02_sg_keys_ec2
````

### 2. **Update Variables**

Edit `terraform.tfvars` and fill in your own values:

```hcl
vpc_name       = "my-vpc"
aws_region     = "ap-south-1"
key_pair_name  = "my-key"
instance_type  = "t2.micro"
...
```

---

### 3. **Initialize Terraform**

```bash
terraform init
```

### 4. **Review Plan**

```bash
terraform plan
```

### 5. **Apply Infrastructure**

```bash
terraform apply
```

---

## WARNING

The following files are ignored by `.gitignore` to prevent committing secrets or state:

* `.terraform/`
* `*.tfstate`, `*.tfstate.backup`
* `terraform.tfvars`
* `*.pem`, `*.key`

---

## Outputs

* **Public IP of EC2**
* **VPC ID, Subnet IDs**
* **Security Group ID**

---

## Requirements

* [Terraform](https://www.terraform.io/downloads)
* AWS CLI configured (`aws configure`)
* Valid AWS credentials with EC2/VPC permissions

---

## Destroy Resources

```bash
terraform destroy
```
