# ↻ Exploring S3 With No Guarantees

I pushed my `ChaosBucket.yml` template to GitHub even if wasn’t ready. The commit was just a breadcrumb so I knew where I left off before diving back into the chaos. 

Starting with the S3 resource block, I’m forcing myself to slow the chaos just enough to practice a more maintainable approach as someone working their way into cloud engineering.

With no grand plan in mind for s3, besides seeing how I can interact with it through the console and programmatic AWS access. I was experimenting with different ways to control access to the bucket. Uploading the template without the policy attached and the `PublicAccessBlockConfiguration` set to true, I had no issues (*classic template‑level issues, not taken into account*). Once, I added the bucket policy and redeployed... hello `CREATE_FAILED` and good morning to my moka pot.
 
The star of the failed stack creation was was the bucket policy. 
```cloudformation
chaosbucket7779311:
  Type: AWS::S3::Bucket
  DeletionPolicy: Delete
  Properties:
    BucketNamePrefix: chaosbucket7779311
    BucketNamespace: "account-regional"
    AccessControl: Private
    BucketEncryption:
      ServerSideEncryptionConfiguration:
        - ServerSideEncryptionByDefault:
            SSEAlgorithm: AES256
    VersioningConfiguration:
      Status: Enabled
    PublicAccessBlockConfiguration:
      BlockPublicAcls: true
      BlockPublicPolicy: true
      IgnorePublicAcls: true
      RestrictPublicBuckets: true

ChaosBucketPolicy:
  Type: AWS::S3::BucketPolicy
  Properties:
    Bucket: !Ref chaosbucket7779311
    PolicyDocument:
      Version: 2012-10-17
      Statement:
        - Action:
            - s3:ListBucket
          Effect: Allow
          Resource: !Join
            - ''
            - - 'arn:aws:s3:::'
              - !Ref chaosbucket7779311
          Principal: '*'
```
So it turns out that AWS does put limits on your insanity and I just thought it was for quotas!!!. 

### ✔️ The Adjustment  
After much pain and sadness, I finally dropped (commented-out) the bucket policy and turned the `PublicAccessBlock` settings back on (true). The bucket’s private anyway(💡), and the `PublicAccessBlock` handles that. And like it was supposed too...the stack deployed without any drama — which, honestly, was almost disappointing (*almost*).

## 📘 Lessons Learned  
- **CloudFormation is petty.** It won’t tell you why it’s mad, just that it is mad.
- **Don’t mix access‑control strategies.** If Public Access Block is enabled, AWS will reject any public bucket policy — even if you have full permissions. 
- **Use Public Access Block for privacy.** It’s simpler, safer, and prevents accidental exposure.  
- **Use bucket policies only when granting access**, not when restricting it.  
- **Test one variable at a time.** Switching between approaches without resetting the template can create conflicts that look like permission issues.
- **Work backward** If it worked before you broke it. Start there.

## 🔮 What I’ll Do Next Time  
- Decide upfront whether the bucket should be **public**, **private**, or **private behind CloudFront**.  
- If the bucket is private, rely on **PublicAccessBlockConfiguration** first — no policy needed.
- Add small, intentional breakpoints — deploy early, deploy often, deploy before the chaos compounds.
- Only introduce a bucket policy when I need to grant access to a specific role, service, or CloudFront OAC.  
- Keep experimental policies in a separate branch so they don’t collide with the final configuration.
- Validate the template before the chaos. A quick cfn-lint run saves you from staring at a failed stack wondering what life choices led you here.