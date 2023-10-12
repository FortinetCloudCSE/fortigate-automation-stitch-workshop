---
title: "Task 2 - Run Terraform"
chapter: true
weight: 3
---

### Task 2 - Run the Terraform Deployment

Perform the following step in your Cloudshell console to create your environment.

1. Clone the Github repo `https://github.com/FortinetCloudCSE/fortigate-automation-stitch-workshop`
1. Change directory to the `fortigate-automation-stitch-workshop/terraform/azure` folder
1. Run `terraform init`
1. Run `terraform plan` for your `username`
1. Run `terraform apply` for your `username`

> **Copy and paste these commands into your Cloud Shell console.**
> The terraform variable `username` will be populated with the value of the environment variable `USER`

```sh
git clone https://github.com/FortinetCloudCSE/fortigate-automation-stitch-workshop
cd ./fortigate-automation-stitch-workshop/terraform/azure
terraform init
terraform plan -var="username=$env:USER"
terraform apply -var="username=$env:USER" -auto-approve

```

  ![terraform1](../images/terraform-01.jpg)
  ![terraform2](../images/terraform-02.jpg)
  ![terraform3](../images/terraform-03.jpg)
