# Managing infrastructure as code with Terraform, Cloud Build, and GitOps

This is the repo for the [Managing infrastructure as code with Terraform, Cloud Build, and GitOps](https://cloud.google.com/solutions/managing-infrastructure-as-code) tutorial. This tutorial explains how to manage infrastructure as code with Terraform and Cloud Build using the popular GitOps methodology. 

```
       Managing-IAC-terraform-cloudbuild-gitops/
       ├── environments/
       │   ├── dev/
       │   │   ├── main.tf
       │   │   ├── variables.tf
       │   └── prod/
       │       ├── main.tf
       │       ├── variables.tf
       ├── modules/
       │   ├── network/
       │   │   ├── main.tf
       │   │   ├── variables.tf
       │   │   └── outputs.tf
       │   ├── compute/
       │   │   ├── main.tf
       │   │   ├── variables.tf
       │   │   └── outputs.tf
       │   └── storage/
       │       ├── main.tf
       │       ├── variables.tf
       │       └── outputs.tf
       ├── .gitignore
       ├── CONTRIBUTING.md
       ├── LICENSE
       ├── README.md
       └── cloudbuild.yaml

```



## Configuring your **dev** environment

Just for demostration, this step will:
 1. Configure an apache2 http server on network '**dev**' and subnet '**dev**-subnet-01'
 2. Open port 80 on firewall for this http server 

```bash
cd ../environments/dev
terraform init
terraform plan
terraform apply
terraform destroy
```

## Promoting your environment to **production**

Once you have tested your app (in this example an apache2 http server), you can promote your configuration to prodution. This step will:
 1. Configure an apache2 http server on network '**prod**' and subnet '**prod**-subnet-01'
 2. Open port 80 on firewall for this http server 

```bash
cd ../prod
terraform init
terraform plan
terraform apply
terraform destroy
```
