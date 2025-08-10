#  Using `for_each` to Create Multiple EC2 Instances  

## Introduction  

This lab is part of my DevOps learning journey.  I used Terraform’s `for_each` meta argument to create multiple AWS EC2 instances dynamically from a map variable. This approach helps me avoid repeating code and makes the infrastructure easier to manage and scale.  

---

## Tools & Technologies  
- Terraform 

- AWS (EC2)  

- HCL (HashiCorp Configuration Language)  

---

## Project Structure  

├── main.tf # EC2 resource definition using for_each

├── variables.tf # Variable declarations

├── terraform.tfvars # Variable values (EC2 names, AMI, instance type)

├── providers.tf # AWS provider setup

├── screenshots/ # Screenshot of terraform apply output

└── README.md # This documentation

---

## How It Works 

- I define a map variable `ec2_instances` in `terraform.tfvars` with keys and values representing instance IDs and names. 

- The `for_each` argument in `main.tf` loops over that map and creates one EC2 instance per entry.  

- Each instance gets tagged with its corresponding name from the map.  


## Steps to Run

- Clone the repository

- git clone git@github.com:donaemeka/terraform-meta-arguments-aws.git

- cd terraform-meta-arguments-aws

- Initialize Terraform

- terraform init

- terraform plan

- terraform apply

## Screenshot

- Here is a screenshot of the output after running terraform apply:



## What I Learned

- How to use the for_each meta argument to create multiple resources from a map.

- The difference between each.key and each.value in Terraform loops.

- How to write cleaner, more scalable Terraform code.

## Challenges & Solutions

1. Remembering each.key vs each.value

  - I tested and observed the tags during terraform plan and apply to understand which to use for names and IDs.

2. Finding the correct AMI ID for my AWS region

  - I checked the AWS console to get the right AMI for us-east-1 and updated terraform.tfvars.

## Thank you for checking out my project.

This hands-on lab is helping me build my skills as a junior DevOps engineer.
