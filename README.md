# Terraform Projects

Small Terraform examples for learning AWS infrastructure concepts. Each example
is self-contained in its own `terraform-manifests` directory:

- [Intro: S3 bucket](Intro/terraform-manifests/README.md) — creates a uniquely
  named S3 bucket and prints its name, ID, and ARN.
- [VPC: networking](VPC/terraform-manifests/README.md) — creates a VPC, public
  and private subnets, an internet gateway, a NAT gateway, and route tables.

## Requirements

- Terraform 1.0 or later
- LocalStack running at `http://localhost:4566`
- Terraform's AWS and Random providers, downloaded during initialization

Both examples currently configure the AWS provider to use LocalStack with
placeholder `test` credentials. They are intended for local development, not
for deploying directly to an AWS account. Review and update the provider
configuration before using either example with AWS.

## General workflow

Run Terraform from the example's `terraform-manifests` directory:

```sh
terraform init
terraform validate
terraform plan
terraform apply
```

Inspect the outputs printed by Terraform after applying. To remove the
resources created by an example, run `terraform destroy` from that same
directory.

Terraform state and plan files are local runtime artifacts and are excluded by
the root `.gitignore`. Keep state files secure; they can contain sensitive
information.
