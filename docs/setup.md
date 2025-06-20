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
For optimal performance of **Lacework FortiCNAPP FortiRecon Alerts** solution pack, you can install and configure the connectors that help with the following:

* **AWS Commands** - Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage.. To configure and use the AWS Commands connector, refer to [Configuring AWS Commands](https://docs.fortinet.com/fortisoar/connectors/aws-commands)
    * **Permissions**: `s3:GetBucketTagging`, `s3:PutBucketTagging`, `s3:DeleteBucketTagging`  
    * IAM role example:
        ```json   
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Action": [
                        "s3:GetBucketTagging",
                        "s3:PutBucketTagging",
                        "s3:DeleteBucketTagging"
                    ],
                    "Effect": "Allow",
                    "Resource": "*",
                    "Sid": "AllowBucketTaggingActions"
                }
            ]
        }
        ```

    * **Note**: Connector name must match the AWS account number integrated into Lacework. 


# Next Steps
| [Usage](./usage.md) | [Contents](./contents.md) |
|---------------------|---------------------------|