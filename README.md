# AWS Financial Services Framework
Opinionated software assets to accelerate successful use of AWS by financial services customers

## Overview
The AWS Financial Service Framework (FSF) is a collection of software assets and documentation whose purpose it is to accelerate the pace at which financial services customers adopt usage of AWS. This acceleration is a function of providing software assets that instantiate AWS resources with the kind of considerations that are typically asked by customers in financial services. These considerations include for example:

*  Isolated VPCs with no internet gateways
*  Ubiquitous encryption with KMS CMKs wherever possible
*  The least permissive entitlements 
*  Segregation of duties through IAM

These software assets, some of which are encapsulated by opinionated , some of which instantiate Config Rules or Lambda Functions, are backed by the documentation required to satisfy not just technical questions but also those asked by an organization’s governance, risk, and compliance functions. Examples of the questions the FSF assets are prepared to answer include, for example: 

*  How do I know which controls are satisfied by this software asset?
*  How do I know that this control, which forces ELB access logging, is effective?
*  How do the controls listed as part of this installation map to frameworks such as NIST 800-53?

We believe that by producing software assets that achieve an outcome and explain the way in which their construction was decided we can accelerate the customer’s journey to AWS. One of the ways in which FSF accomplishes this is by publishing control design documents. Control design documents describe the logic employed by a particular control. For example, a control whose purpose it is to detect unencrypted kinesis streams, would be accompanied by a control design document that describes the logic of the code and how it makes that determination. This is done so that an auditor can test and then attest to the effectiveness of that control. In this example the document would explain that an auditor could test effectiveness by sampling a random number of kinesis streams, use the logic to make a conclusion as to whether the selected kinesis stream is encrypted, and then compare those conclusions to those that were automatically determined by the installed control for the same set of streams. Should the manual and automatic results be the same the auditor should feel comfortable attesting to the effectiveness of the control.

## FSF Modules Roadmap
The first tranche of FSF modules are those required to construct a minimally viable architecture (MVA) for an internally facing three-tier web application. We plan to release those in Q4 of 2020 along with a repo which constructs the infrastructure for the MVA and installs a sample Java Spring based banking application via the MVA's pipeline. In early 2021, we plan to release CloudFormation versions of the modules and the MVA. 

The backlog of FSF modules includes:

### Parameters and secrets
* AWS Secrets Manager Random Secret - for database and other passwords
* AWS Systems Manager Parameter Store parameter
* AWS Key Management Service Customer Managed Key (CMK)

### Networking
* Amazon VPC - spoke VPC for hub-and-spoke networking architecture
* Amazon Classic Elastic Load Balancer
* Amazon VPC security group
* Amazon VPC subnet
* Amazon VPC route table
* Amazon VPC endpoint
* Amazon VPC flow logs

### Compute
* Amazon EC2 Auto Scaling 

### Database and storage
* Amazon RDS for MySQL
* Amazon S3 bucket 

### CICD pipeline
* AWS CodeBuild
* AWS CodeCommit
* AWS CodeDeploy
* AWS CodePipeline

### IAM
* IAM role for EC2 instance profiles
* IAM role for CodeCommit
* IAM role for RDS enhanced logging

### Reference architectures
* Three-tier web application - minimally viable architecture
* CICD deployable sample banking application


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

