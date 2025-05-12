# Example: IAM User Access

This example demonstrates how to use the `terraform-aws-finops-costreview-access` module in `iam-user` mode.

It creates an IAM user with read-only permissions for billing, CloudWatch, and Cost Explorer APIs, suitable for FinOps cost reviews.

## Usage

```hcl
module "finops_access" {
  source     = "../../"
  mode       = "iam-user"
  account_id = "123456789012"
  user_name  = "finops-review-user"
  role_name  = "finops-review-role"
}
