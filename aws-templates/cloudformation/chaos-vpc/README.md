
## 🎯 Why I Built an s3 Bucket
For whatever this bucket becomes, it’s already locked down, versioned, and ready for the day I decide it needs to store something important… or something I forgot about.

*For details on how this project handles documentation updates, see `docs/evolving-docs.md`.*

## 🏗️ Current Build
| Category | What Gets Built | Notes |
| --- | --- | --- |
| **ChaosVpc** | VPC environment | Networking, security, IAM, launch templates, ASGs, and outputs |

### 🧭 Evolving Documentation
This CloudFormation template is evolving — and this README will evolve with it. Instead of maintaining multiple documents, this one will stay continuously updated… because version‑controlling my own thoughts is apparently the only way to keep things sane.

## 🛠️ Added to Build
As the infrastructure grows, new components will be documented here in the same format as the core stack above.
| Category | What Gets Built | Notes |
| --- | --- | --- |
| **S3 Bucket** | 1× Private S3 Bucket | Core storage bucket for application or logging. |
| **AccessControl** | ACL = Private | Ensures no public ACLs are allowed. |
| **BucketEncryption** | AES256 SSE | Encrypts all objects at rest. |
| **BucketNamespace** | ``account-regional`` | Ensures bucket names are unique per account + region. |
| **BucketNamePrefix** | ``ChaosBucket7779311`` | Predictable prefix; CloudFormation appends unique suffix. |
| **BucketName** | *Not used* | Mutually exclusive with prefix; prefix chosen for safer naming. |
| **Versioning** | Enabled | Protects against accidental overwrites/deletes. |
| **Public Access Block** | All public access blocked | Enforces best‑practice security posture. |

## ☁️ AWS Patterns Demonstrated
- How an infrastructure is built using CloudFormation.
- Using `Conditions` to enable/disable features.

## 📚 What I Learned
- I really need to start using Git before my work decides to evolve on its own.
- Slowing down matters; you can’t build everything at once, and undocumented chaos only multiplies.
- The template I used before was functional.
- CloudFormation eliminates a lot of manual console work and reduces mistakes.
- Able to interact with deployed resources through AWS CLI.
- CloudFormation supports bringing existing or recently created resources under CloudFormation management.
- AWS CLI and AWS Toolkit for VS Code each use their own authentication method.

## 🌀 What's Next  
- Walk through the template to understand the resources it builds and the patterns it uses
- Use the environment to practice and get comfortable with how AWS resources interact in a real setup.
- Adopt Git so my work stays organized instead and the infrastructure starts drifting in ways I can’t explain.
- Use lightweight project management practices to keep your architecture organized as it evolves.
- Pacing the build is critical—trying to deploy everything at once without documentation just creates operational debt.
