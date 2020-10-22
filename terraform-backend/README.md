# terraform-backend

If you’re using Terraform with AWS, Amazon S3 (Simple Storage Service), which is Amazon’s managed file store, is typically your best bet as a remote backend for the following reasons:

- It’s a managed service, so you don’t have to deploy and manage extra infrastructure to use it.
- It’s designed for 99.999999999% durability and 99.99% availability, which means you don’t have to worry too much about data loss or outages.
- It supports encryption, which reduces worries about storing sensitive data in state files. Anyone on your team who has access to that S3 bucket will be able to see the state files in an un-encrypted form, so this is still a partial solution, but at least the data will be encrypted at rest (S3 supports server-side encryption using AES-256) and in transit (Terraform uses SSL to read and write data in S3).
- It supports locking via DynamoDB.
- It supports versioning, so every revision of your state file is stored, and you can roll back to an older version if something goes wrong.
- It’s inexpensive, with most Terraform usage easily fitting into the free tier.
