
## 🎯 Why I *re*Built It
Much like the template before it, this one ran off on its own adventure. Instead of chasing it after it, I decided a clean rebuild was the sane option.

## 📌 What I *re*Built
| Category | What Gets Built | Notes |
| --- | --- | --- |
| **VPC** | 1× VPC (``ChaosVpc``) | CIDR comes from environment mapping or overrides. |
| **Internet Access** | Internet Gateway + VPC attachment | Enables outbound internet for public subnets. |
| **Route Tables** | 1× Public RT, 1× Private RT | Public RT has default route to IGW. |
| **Subnets (Public)** | 3× Public subnets | ``PublicIngress1/2/3`` with optional CIDR overrides. |
| **Subnets (Private)** | 3× Private subnets | ``PrivateApp1/2/3`` with optional CIDR overrides. |
| **Route Table Associations** | 3× public + 3× private associations | Each subnet mapped to correct RT. |
| **Security Groups** | ICMP, SSH, HTTP, HTTPS, RDP, NFS | All created regardless of OS toggles; attached conditionally. |
| **IAM** | 1× SSM Role + 1× Instance Profile | Grants SSM Session Manager access. |
| **Launch Templates** | Linux, Windows, Ubuntu (conditional) | Includes AMI mapping, instance type, SSM profile, SG toggles. |
| **Auto Scaling Groups** | Linux, Windows, Ubuntu (conditional) | Each spans all 3 public subnets; size controlled by parameters. |
| **Outputs** | VPC ID, Subnet IDs, SG IDs, ASG names, LT IDs, SSM profile ARN | Provides all major resource identifiers. |

## ☁️ AWS Patterns Demonstrated
- How an infrastructure is built using CloudFormation.
- Using `Conditions` to enable/disable features.

## 📚 What I Learned
- I really need to start using Git before my work decides to evolve on its own.
- Slowing down matters; you can’t build everything at once, and undocumented chaos only multiplies.
- The template I used before was functional.
- CloudFormation eliminates a lot of manual console work and reduces mistakes.
- Able to interact with deployed resources through AWS CLI.

## 🌀 What's Next  
- Walk through the template to understand the resources it builds and the patterns it uses
- Use the environment to practice and get comfortable with how AWS resources interact in a real setup.
- Adopt Git so my work stays organized instead and the infrastructure starts drifting in ways I can’t explain.
- Use lightweight project management practices to keep your architecture organized as it evolves.
- Pacing the build is critical—trying to deploy everything at once without documentation just creates operational debt.
