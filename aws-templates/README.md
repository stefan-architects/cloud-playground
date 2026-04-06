## 📌 What's being built?

CloudFormation and CLI templates for deploying and testing AWS resources — the practical, slightly chaotic toolkit you use when you want real infrastructure spinning up fast and you’re not afraid...*yet*.

## 🎯 Purpose

Before everything spirals into even more cloud‑powered experimentation, here’s the real purpose behind it all:

- What the AWS CLI is and how to run basic commands… even when things don’t behave exactly the way the docs say they should
- What CloudFormation is and how templates attempt to create resources in a predictable way—until a dependency or parameter decides otherwise
- How the CLI and CloudFormation work together, and occasionally step on each other’s toes when you forget a flag or misname a stack
- When to use each tool in real-world scenarios, especially when speed, automation, or damage control is involved
- Methodologies for architecting on AWS while embracing the fact that cloud environments are never as static or orderly as diagrams suggest  

## 🚧 Project Status & Features

And because nothing teaches faster than breaking things in the cloud, here are the files born from that glorious chaos:

Current files include:  
- **ChaosVPC.yaml** – A VPC stack that’s actively being shaped, reshaped, and pushed toward something chaotic or awesome  
- **create-key-pair-cli.md** – A script that spins up fresh EC2 SSH key pairs while nudging you toward SSM so you can eventually ditch keys altogether  
- **create-user-and-group.md** – A growing IAM setup script that keeps evolving as you add users, groups, and the policies they swear they need  
- **dynamo-cli.md** – A DynamoDB table builder that I have absolutely no practical use for, but fun to build
- **ec2-cli.md** – An EC2 provisioning script that keeps expanding as you test instance types, AMIs, and whatever chaos you throw at it next  
- **rds-cli.md** – A steadily improving RDS setup script that handles the long, suspenseful wait for your database to finally become “available”  
- **s3-cli.md** – An S3 bucket creator that evolves as you experiment with versioning, encryption, lifecycle rules, and all the ways S3 can surprise you  
- **security-groups-cli.md** – A hands‑on security group builder that grows with your networking needs and occasionally reminds you what it feels like to lock yourself out  

## ⭐ AWS Patterns Demonstrated

If nothing else, these files prove one thing: AWS has patterns, and you’ll learn them whether you meant to or not:

- Infrastructure as Code with CloudFormation templates… even when you’re wondering if that one missing comma is about to ruin your whole day
- Repeatable and consistent deployments, assuming nothing mysteriously breaks between environments (it will)
- Automated provisioning using the AWS CLI, because clicking around the console again is not the life you want
- Template validation and basic testing, followed by the inevitable “why is this failing now when it worked yesterday?” moment
- Clear separation between defining resources (CloudFormation) and deploying them (CLI), though you’ll still ask yourself if you should go back and tweak the template one more time
- Methodologies for architecting on AWS while embracing the fact that cloud environments are never as static or orderly as diagrams suggest, no matter how pretty those diagrams look