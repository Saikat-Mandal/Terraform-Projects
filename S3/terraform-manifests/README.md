# Intro: S3 bucket

This example provisions one S3 bucket through LocalStack. A random lowercase
suffix is appended to the bucket name to reduce naming collisions. Terraform
also outputs the bucket name, ID, and ARN.

## Files

- `c1-versions.tf` — Terraform/provider requirements and AWS provider settings.
  The provider targets the S3 API at `http://localhost:4566`.
- `c2-s3bucket.tf` — random suffix and S3 bucket resources.
- `c3-outputs.tf` — bucket name, ID, and ARN outputs.

## Requirements

- Terraform 1.0 or later
- LocalStack running and exposing its S3 API at `http://localhost:4566`

The provider uses placeholder credentials and LocalStack-specific settings.
Do not use this configuration against AWS without changing the provider
configuration and supplying appropriate credentials.

## Run

From this directory:

```sh
terraform init
terraform validate
terraform plan
terraform apply
```

Terraform prints the bucket outputs after a successful apply. To remove the
bucket and other resources managed by this example:

```sh
terraform destroy
```

Terraform state and saved plans are local artifacts; do not commit them.
