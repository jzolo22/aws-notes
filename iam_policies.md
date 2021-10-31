# IAM: Policies

- A policy at the group level will get applied to each member of the group
- An "inline policy" can be assigned to a single user
- Users can have access to policies from different groups

## IAM Policy Structure (JSON object)

- Version: policy language version
- ID: an optional identifier for the policy
- Statement (an array of one or more individual statements) composed of:
  - Sid: optional identifier for the statement (i.e. statement ID)
  - Effect: whether the statements allows or denies access ("Allow" or "Deny")
  - Principal: account/user/role that the policy will apply to
  - Action: list of actions this policy allows or denies
  - Resource: list of resources to which the actions applied to (i.e. s3 bucket)
  - Condition: (optional) conditions for when this policy is in effect

## Example Policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ExplicitDenyIfNotTheOwner",
      "Effect": "Deny",
      "Action": [
        "datapipeline:ActivatePipeline",
        "datapipeline:AddTags",
        "datapipeline:DeactivatePipeline",
        "datapipeline:DeletePipeline"
      ],
      "Resource": ["*"],
      "Condition": {
        "StringNotEquals": { "datapipeline:PipelineCreator": "${aws:userid}" }
      }
    }
  ]
}
```
