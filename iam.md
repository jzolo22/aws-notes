# IAM

### Users & Groups

- Identity & access management
- Global service
- Users are people within the org
- Groups can contain users

  - groups can't contain other groups

- Users or groups can be assigned JSON documents called policies (to grant permissions)
- Use **least privilege principle** - give users the least amount of priveleges necessary
- Root AWS user should very rarely be used - default to using a provisioned user

### IAM Roles (for Services)

- IAM roles are used to grant permissions to entities that you trust
- Some AWS services will need to perform actions on a user's behalf
  - Therefore, these services will need to be assigned permissions via IAM roles
- Common roles:
  - EC2 Instance Roles (e.g. an EC2 instance needing an IAM role to access AWS)
  - Lambda Function Roles
  - CloudFormation Roles

### IAM Security Tools

- IAM Credentials Report (account-level)
  - lists account's users and the status of their credentials
- IAM Access Advisor (user-level)
  - shows service permissions granted to a user and when those services were last accessed
  - use this to revise policies to make sure the servcies that are not being used are removed from permissions (least privilege principle)

### IAM Best Practices

- Use root account _only_ for AWS account setup, otherwise use a regular IAM user
- One physical user = one AWS user
- Assign users to groups and assign permissions to groups
- Strong password policy & MFA
- Create and use roles for giving permissions to AWS services
- Never share IAM users & Access Keys
