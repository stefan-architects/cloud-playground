# ⚠️💰 Cost Considerations

Deploying the AWS templates in this directory **may incur charges** in your AWS account.  
Before running any deployment commands, review the information below to understand potential costs and how to avoid unexpected charges.

---

## 🧾 Services That May Generate Costs

Depending on which templates you deploy, AWS may bill for resources such as:

- 🖥️ **Compute** — EC2 instances, Lambda functions, Fargate tasks  
- 📦 **Storage** — S3 buckets, EBS volumes  
- 🌐 **Networking** — VPC components, NAT Gateways, Load Balancers  
- 🗄️ **Databases** — RDS, DynamoDB  
- 📊 **Monitoring & Logging** — CloudWatch metrics, logs, alarms  
- 🔐 **IAM** — Free, but misconfigured roles can enable costly services

Not all templates will create all of these resources, but **any deployed resource can generate charges**.

---

## 🛑 Before You Deploy

- ✔️ Confirm you are deploying into the **correct AWS account**  
- ✔️ Review the AWS pricing pages for the services used  
- ✔️ Understand whether the template creates **free‑tier‑eligible** or **billable** resources  
- ✔️ Ensure you have the necessary permissions to delete resources afterward  

---

## 🧹 After Deployment

To avoid ongoing charges:

- 🗑️ Delete CloudFormation stacks or manually remove deployed resources  
- 🔍 Verify that no dependent resources remain (e.g., EBS volumes, ENIs, S3 buckets)  
- 📝 Check CloudWatch Logs retention settings  
- 📈 Review the AWS Billing Dashboard for active usage  

---

## 🧭 Responsibility

You are fully responsible for any AWS charges incurred by deploying these templates.  
If you are unsure about the cost impact of a specific template, review it carefully before deployment.
