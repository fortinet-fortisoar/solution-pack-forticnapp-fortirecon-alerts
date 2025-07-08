[Home](../README.md) |
|--------------------------------------------|

# Installation

1. To install a solution pack, click **Content Hub** > **Discover**.
2. From the list of solution pack that appears, search for and select **Lacework FortiCNAPP FortiRecon Alerts**.
3. Click the **Lacework FortiCNAPP FortiRecon Alerts** solution pack card.
4. Click **Install** on the lower part of the screen to begin the installation.

## Prerequisites
The **Lacework FortiCNAPP FortiRecon Alerts** solution pack depends on the following solution packs that are installed automatically &ndash; if not already installed.
| Solution Pack Name | Version | Purpose |
| :--------------------- | :---------------------| :--------------------------------------- |
| SOAR Framework | v2.0.0 and later | Required for Incident Response modules                   |



# Configuration

> [!Important]
> Before first-use, open the solution pack and modify the `Variables` step. Update the `fortirecon_config` value specifying your FortiRecon connector configuration name, replacing `<YOUR CONNECTOR CONFIG NAME HERE>`.

For optimal performance of **Lacework FortiCNAPP FortiRecon Alerts** solution pack, you can install and configure the connectors that help with the following:

* **AWS Commands** - Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage.. To configure and use the AWS Commands connector, refer to [Configuring AWS Commands](https://docs.fortinet.com/fortisoar/connectors/aws-commands).

    **Note:** This solution pack expects the **configuration name to match the AWS Account ID** (e.g. `123456789012`). This is because during the parsing of alerts the account id is dynamically extracted and then used to take the tagging action on the identified assets.

    * **Permissions**: `ec2:CreateTags`  
    * IAM role for instance tagging example:
        ```json   
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                "Action": [
                    "ec2:CreateTags"
                ],
                "Effect": "Allow",
                "Resource": "*",
                "Condition": {},
                "Sid": "AllowTagInstances"
            },
        }
        ```
    
    * **Permissions**: `see policy below or review fortirecon admin guide for details`
    * IAM Role for IASM discovery:
        ```json   
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Sid": "FortiReconRead",
                    "Effect": "Allow",
                    "Action": [
                        "elasticfilesystem:DescribeBackupPolicy",
                        "elasticfilesystem:DescribeReplicationConfigurations",
                        "route53:TestDNSAnswer",
                        "s3:Get*",
                        "elasticfilesystem:DescribeAccountPreferences",
                        "s3:List*",
                        "rds:Describe*",
                        "resource-groups:GetGroup",
                        "route53:Get*",
                        "route53:List*",
                        "elasticloadbalancing:Describe*",
                        "apigateway:GET",
                        "es:Describe*",
                        "resource-groups:ListGroupResources",
                        "resource-groups:GetGroupQuery",
                        "elasticfilesystem:ListTagsForResource",
                        "elasticfilesystem:DescribeLifecycleConfiguration",
                        "elasticfilesystem:DescribeFileSystemPolicy",
                        "elasticfilesystem:DescribeFileSystems",
                        "elasticfilesystem:DescribeMountTargets",
                        "es:Get*",
                        "ec2:Describe*",
                        "elasticfilesystem:DescribeAccessPoints",
                        "resource-groups:ListGroups",
                        "elasticache:Describe*",
                        "elasticfilesystem:DescribeTags",
                        "es:List*",
                        "elasticfilesystem:DescribeMountTargetSecurityGroups",
                        "cloudfront:List*",
                        "cloudfront:GetDistributionConfig",
                        "ecs:Describe*",
                        "ecs:List*",
                        "kinesis:List*",
                        "kinesis:Describe*",
                        "redshift:Describe*"
                    ],
                    "Resource": "*"
                }
            ]
        }
        ```

    * **Note**: Connector name must match the AWS account number integrated into Lacework. 


# Next Steps
| [Usage](./usage.md) | [Contents](./contents.md) |
|---------------------|---------------------------|