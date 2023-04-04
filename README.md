Securely sharing files over SFTP, FTP, and FTPS is a staple within many business-to-business (B2B)
workflows. Across industries, companies use this mechanism to report inventory, invoice, and
compliance information. AWS's framework for protecting against ransomware events includes
continuous monitoring to detect and respond to security findings for your workloads. For your file
transfer workloads, you can scan each file you receive, and isolate malicious files before they ever reach
your downstream systems. New files only reach your systems after an automated vetting process runs a
series of security tooling, like antivirus checks.

Deploying the solution
In this section, you deploy the AWS CloudFormation templates that create the following resources: 
•	Amazon S3 bucket
•	AWS Transfer Family server
•	AWS Lambda functions
•	AWS Secrets Manager secrets
•	AWS CodeBuild project
•	Amazon ECR repository
•	Amazon EventBridge rules
•	IAM Roles and Policies
To deploy the CloudFormation template, follow these steps:
1.	Open AWS CloudShell in your AWS account
2.	Clone this post’s GitHub repository using git clone command (git clone https://github.com/aws-samples/transfer-family-anti-virus-cdk.git)
3.	Change into the transfer-family-anti-virus-cdk directory (cd transfer-family-anti-virus-cdk)
4.	Provide executable permissions to deployStack.sh bash script (chmod +x deployStack.sh)
5.	Run the deployStack bash script to create the required resources (./deployStack.sh)
6.	Copy the SFTPEndpoint, User name and password to use later. SFTPEndpoint is the fully qualified domain name of your Transfer Family server.
The script takes less than 20 minutes to run and change to a CREATE_COMPLETE state. If you deploy the stack twice in the same AWS account and Region, some resources may already exists and the process fails with a message indicating the resource already exists in another template.
![image](https://user-images.githubusercontent.com/108286063/229862693-6374bafe-a26f-48b3-a9df-8bd401099fb2.png)