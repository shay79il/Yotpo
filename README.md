# Yotpo

## Prerequirments:
### 1. Terraform installed (relevent version indicated on `.terraform-version` file)
### 2. Kind K8s cluster installed 


## How to run
```bash

# Install kind configuration
kind create cluster --config kind/config.yaml

# Provision the k8s resources
terraform init
terraform apply --auto-run

# To see the Welcome page of Nginx just run the following
curl -v $(kg nodes -o wide | tail +2 | head -1 | tr -s ' ' | cut -d ' ' -f 6):30080

```