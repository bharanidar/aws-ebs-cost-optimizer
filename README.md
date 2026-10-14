# AWS EBS Snapshot Cost Optimizer

## Overview

The AWS EBS Snapshot Cost Optimizer is a cloud cost optimization project designed to identify potentially stale Amazon EBS snapshots and help reduce unnecessary AWS storage costs.

The project uses AWS Lambda and Python to analyze EBS snapshots, check their associated volumes, and identify potential cleanup candidates.

## Technologies Used

- Amazon Web Services (AWS)
- AWS Lambda
- Amazon EC2
- Amazon EBS
- Python
- Boto3
- AWS IAM
- Amazon CloudWatch

## Architecture and Workflow

1. AWS Lambda executes the Python function.
2. The function retrieves EBS snapshots owned by the AWS account.
3. It identifies running EC2 instances.
4. It checks the source volumes associated with snapshots.
5. It logs snapshots that should be skipped and potential cleanup candidates.
6. The cleanup workflow can be extended to automate deletion after validation and safety checks.

## Key Features

- Automated snapshot inventory analysis through AWS Lambda.
- Identification of potential stale snapshots.
- EC2 instance and EBS volume status checks.
- IAM-based access control.
- Dry-run analysis to avoid unintended snapshot deletion.
- Execution logs for monitoring and troubleshooting.

## Testing

The Lambda function was deployed and executed successfully in AWS.

During testing, the function identified a snapshot associated with a volume attached to a running EC2 instance and correctly skipped it.

The current implementation operates in dry-run mode. Automatic snapshot deletion and actual cost savings have not yet been validated.

## Cost Optimization

EBS snapshots can incur storage charges over time. Identifying snapshots that are no longer needed can help reduce unnecessary storage costs.

Before deleting a snapshot, its backup retention requirements and recovery dependencies must be checked.

## Future Enhancements

- Implement validated automatic snapshot deletion.
- Add configurable snapshot retention policies.
- Schedule periodic execution using Amazon EventBridge.
- Improve monitoring and reporting through Amazon CloudWatch.
- Add notifications for potential cleanup candidates.

## Skills Demonstrated

AWS Lambda, EC2, EBS, Python, Boto3, IAM permissions, cloud resource monitoring, and cost optimization.

## Author

Bharanidar
