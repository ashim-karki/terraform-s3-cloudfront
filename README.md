## S3 and CloudFront Infrastructure with Terraform
This project sets up a static website hosting infrastructure using AWS S3 and CloudFront with Terraform. The infrastructure includes:

### An S3 bucket to store website files
A CloudFront distribution for content delivery
CloudFront Origin Access Identity to securely access the S3 content

### Infrastructure Components
S3 Bucket: Static content storage (ashimsbucketfors3cdn112358)
CloudFront Distribution: Content delivery network
Origin Access Identity: Secure access mechanism between CloudFront and S3

### Deployment
Initialize Terraform:
```
terraform init
```

Preview changes:
```
terraform plan
```

Apply the infrastructure:
```
terraform apply
```

### Accessing the Website
After deployment, the website is accessible via the CloudFront domain:

Output Values
The following outputs are provided:

bucket_name: Name of the S3 bucket
cloudfront_domain_name: Domain name of the CloudFront distribution

### Cleanup
To destroy the infrastructure:
```
terraform destroy
```

### Security Considerations
The S3 bucket is not directly accessible to the public
CloudFront accesses the S3 bucket via Origin Access Identity
Content is served over HTTPS (with redirect from HTTP)

### Notes
The CloudFront distribution is configured to use the cheapest price class (PriceClass_100)
Content caching is set to minimum TTL of 0 seconds, default TTL of 1 hour (3600 seconds), and maximum TTL of 24 hours (86400 seconds)
