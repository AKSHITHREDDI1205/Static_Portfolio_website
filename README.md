 # STATIC PORTFOLIO WEBSITE IN AWS WITH TERRAFORM 🚀
This repository contains the Terraform configuration to deploy a fully functional, highly available static portfolio website on Amazon S3, complete with custom domain integration and secure public access. Automate your web presence with just a few commands!
## ✨ Why Terraform for a Static Website?
*	Infrastructure as Code (IaC): Define your AWS infrastructure (S3 buckets, public access settings, etc.) in human-readable code, ensuring consistency and repeatability.
*	Version Control: Track all changes to your infrastructure directly within Git, just like your application code.
*	Automation: Deploy your website effortlessly and reliably, eliminating manual configuration errors.
*	Cost-Effective: Leverage AWS S3's robust and economical static website hosting capabilities.
## 📦 What's Deployed?
*	Amazon S3 Bucket: Configured for static website hosting, serving your index.html and error.html files.
*	S3 Bucket Policy: Ensures secure public read access to your website content while maintaining overall bucket security.
*	(Optional: Future Enhancement Idea) Could include CloudFront for CDN, Route 53 for DNS, or even SSL/TLS certificates for HTTPS.
## 🚀 Getting Started
Follow these simple steps to deploy your static portfolio website to AWS using Terraform.
### Prerequisites:
*	An AWS Account configured with programmatic access (AWS CLI configured or environment variables set).
*	Terraform installed on your local machine.
*	Your static website files (index.html, error.html, style.css, etc.) ready in the directory where you run Terraform.
*	A registered domain name (e.g., yourdomain.com) that you wish to assign to your S3 bucket. Ensure your S3 bucket name matches your domain name (e.g., yourdomain.com).
### Deployment Commands:
1.	Initialize Terraform:

```bash
terraform init 
```
This command initializes the Terraform working directory. It downloads the necessary AWS provider plugins and sets up the backend configuration, ensuring Terraform can interact with your AWS account. You'll see confirmation that AWS is being configured.

2.	Review the Deployment Plan:

```bash
terraform plan
``` 

This crucial step generates an execution plan. It shows you exactly what Terraform will do (create, modify, or destroy resources) in your AWS environment before any changes are applied. Review this plan carefully to understand the future state of your infrastructure.

3.	Deploy the Website:

```bash
terraform apply -auto-approve 
``` 

This command executes the actions outlined in the plan. The -auto-approve flag automatically confirms the changes, bypassing the manual prompt. Terraform will provision your S3 bucket, configure it for static website hosting, and apply the necessary public access policy.
Once terraform apply is complete, Terraform will output the S3 static website endpoint URL.
## 🗑️ Cleaning Up
To destroy all the AWS resources provisioned by this Terraform configuration and avoid incurring further costs:

```bash
terraform destroy -auto-approve
```


Warning: This command will permanently delete your S3 bucket and all its contents. Ensure you have backups of your website files if needed.
