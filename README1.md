## Create New Workspace and Provision Infra 
```t
# New Workspace
terraform workspace new dev

# checkup on the folder
tree terraform.tfstate.d 
   |_ dev

## Terraform pipeline

# Terraform Plan
terraform plan -var-file="dev.tfvars"

# Terraform Apply
terraform apply -var-file="dev.tfvars"

# Verify Dev Workspace statefile
cd terraform.tfstate.d/dev
ls
Observation: You should fine "terraform.tfstate" in "current-working-directory/terraform.tfstate.d/dev" folder

# Verify EC2 Instance in AWS mgmt console
Observation:
1) Name should be with "vm-dev-0"
2) Security Group names should be as "vpc-ssh-dev, vpc-web-dev"
```
