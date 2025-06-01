STATIC PORTFOLIO WEBSITE IN AWS WITH TERRAFORM 🚀
This repository contains the Terraform configuration to deploy a fully functional, highly available static portfolio website on Amazon S3, complete with custom domain integration and secure public access. Automate your web presence with just a few commands!

✨ Why Terraform for a Static Website?
Infrastructure as Code (IaC): Define your AWS infrastructure (S3 buckets, public access settings, etc.) in human-readable code, ensuring consistency and repeatability.
Version Control: Track all changes to your infrastructure directly within Git, just like your application code.
Automation: Deploy your website effortlessly and reliably, eliminating manual configuration errors.
Cost-Effective: Leverage AWS S3's robust and economical static website hosting capabilities.
📦 What's Deployed?
Amazon S3 Bucket: Configured for static website hosting, serving your index.html and error.html files.
S3 Bucket Policy: Ensures secure public read access to your website content while maintaining overall bucket security.
(Optional: Future Enhancement Idea) Could include CloudFront for CDN, Route 53 for DNS, or even SSL/TLS certificates for HTTPS.
🚀 Getting Started
Follow these simple steps to deploy your static portfolio website to AWS using Terraform.

Prerequisites:
An AWS Account configured with programmatic access (AWS CLI configured or environment variables set).
Terraform installed on your local machine.
Your static website files (index.html, error.html, style.css, etc.) ready in the directory where you run Terraform.
A registered domain name (e.g., yourdomain.com) that you wish to assign to your S3 bucket. Ensure your S3 bucket name matches your domain name (e.g., yourdomain.com).
Deployment Commands:
Initialize Terraform:

Bash

terraform init
This command initializes the Terraform working directory. It downloads the necessary AWS provider plugins and sets up the backend configuration, ensuring Terraform can interact with your AWS account. You'll see confirmation that AWS is being configured.

Review the Deployment Plan:

Bash

terraform plan
This crucial step generates an execution plan. It shows you exactly what Terraform will do (create, modify, or destroy resources) in your AWS environment before any changes are applied. Review this plan carefully to understand the future state of your infrastructure.

Deploy the Website:

Bash

terraform apply -auto-approve
This command executes the actions outlined in the plan. The -auto-approve flag automatically confirms the changes, bypassing the manual prompt. Terraform will provision your S3 bucket, configure it for static website hosting, and apply the necessary public access policy.

Once terraform apply is complete, Terraform will output the S3 static website endpoint URL.

Post-Deployment Steps (DNS Configuration):
After Terraform successfully deploys your S3 bucket, you'll need to point your custom domain to your S3 website endpoint.

Retrieve S3 Website Endpoint: You can find this in the output of terraform apply or by navigating to your S3 bucket in the AWS Console, going to Properties -> Static website hosting.
Configure DNS Records:
Log in to your domain registrar's DNS management console (e.g., GoDaddy, Namecheap, Route 53).
Create a CNAME record for www (e.g., www.yourdomain.com) pointing to your S3 website endpoint.
If you want yourdomain.com (the root domain) to also work, consider setting up a redirect from your root domain to www.yourdomain.com through your domain registrar, or use AWS Route 53 with an Alias record pointing to the S3 bucket.

