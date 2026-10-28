# Secure AWS Landing Zone & Multi-Tier Architecture (Terraform)

An enterprise-ready, modular AWS landing zone provisioned using Terraform, designed with strict zero-trust principles, automated compliance scanning, and isolated multi-tier network architecture.

## Architecture Overview
This repository provisions a secure cloud perimeter adhering to AWS Well-Architected Framework security pillars:
- **VPC Design:** Isolated Public, Private, and Database subnets distributed across multiple Availability Zones (AZs).
- **Ingress/Egress Control:** NAT Gateways for secure private subnet internet access; restricted Security Groups implementing the principle of least privilege.
- **Storage Encryption:** S3 buckets configured with mandatory server-side encryption (SSE-S3/KMS), block public access, and enforced versioning.

## Security Compliance & Pre-Deployment Scanning
To catch infrastructure misconfigurations before deployment, this repository integrates automated static analysis:
```bash
# Run Checkov local compliance scan against Terraform code
checkov -f main.tf

# Run tfsec for security-focused static code analysis
tfsec .

Initialize Terraform modules:
terraform init

Validate infrastructure syntax and security posture:
terraform plan

Apply configurations:
terraform apply
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.
