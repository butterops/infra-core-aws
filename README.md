# infra-core-aws

ButterOps Infrastructure Core Services (IaC for VPC, IAM, S3 etc.) for supporting butterops community projects on aws cloud

## Inside service modules

1. [terraform-backend](./terraform-backend/README.md) - Remote state management and state locking for aws services managed through terraform scripts.
2. [members-access-policy](./members-access-policy/README.md) - IAM roles & access policy for aws users to the community.
