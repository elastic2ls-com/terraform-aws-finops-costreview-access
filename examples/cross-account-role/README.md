# Example: Cross-Account Role Access

This example shows how to configure the `terraform-aws-finops-costreview-access` module in `cross-account-role` mode.

It creates a cross-account IAM role trusted by an external FinOps provider, granting limited read-only access.

## Usage

```hcl
module "finops_access" {
  source                      = "../../"
  mode                        = "cross-account-role"
  service_provider_account_id = "123456789012"
  service_provider_role_name  = "finops-review-role"
  external_id                 = "your-secure-external-id"
  role_name                   = "FinOpsCostReviewRole"
  attach_organizations_policy = true
}
```

## Requirements

* The trusting account must be configured to allow the trusted account ID.

* Terraform ≥ 1.3