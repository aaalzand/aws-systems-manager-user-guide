# Use Cases and Best Practices<a name="systems-manager-best-practices"></a>

This topic lists common use cases and best practices for AWS Systems Manager capabilities\. If available, this topic also includes links to relevant blog posts and technical documentation\.

**Note**  
The title of each section here is an active link to the corresponding section in the technical documentation\.

**[Automation](systems-manager-automation.md)**
+ Create self\-service runbooks for infrastructure as Automation documents\.
+ Use Automation to simplify creating AMIs from the AWS Marketplace or custom AMIs, using public SSM documents or by authoring your own workflows\.
+ [Use the AWS\-UpdateLinuxAmi and AWS\-UpdateWindowsAmi Automation documents \(or create custom Automation documents\) to build and maintain AMIs\.](automation-walk.md)

**[Inventory](systems-manager-inventory.md)**
+ Use Systems Manager Inventory with AWS Config to audit your application configurations over time\.

**[Maintenance Windows](systems-manager-maintenance.md)**
+ Define a schedule to perform potentially disruptive actions on your instances such as OS patching, driver updates, or software installations\.

**[Parameter Store](systems-manager-parameter-store.md)**
+ Use Parameter Store to centrally manage global configuration settings\.
+ [Use Parameter Store to encrypt and manage secrets by using AWS KMS](sysman-paramstore-walk.md)\.
+ [Use Parameter Store with ECS task definitions to store secrets](https://aws.amazon.com/blogs/compute/managing-secrets-for-amazon-ecs-applications-using-parameter-store-and-iam-roles-for-tasks/)\.

**[Patch Manager](systems-manager-patch.md)**
+ Use patch manager to rollout patches at scale and increase fleet compliance visibility across your instances\.

**[Run Command](execute-remote-commands.md)**
+ [Manage Instances at Scale without SSH Access Using EC2 Run Command](https://aws.amazon.com/blogs/aws/manage-instances-at-scale-without-ssh-access-using-ec2-run-command/)\.
+ Audit all API calls made by on or on behalf of Run Command using AWS CloudTrail\.
+ [Use the targets and rate control features in Run Command to perform a staged command execution](send-commands-multiple.md)\.
+ [Use fine\-grained access permissions for Run Command \(and all Systems Manager capabilities\) by using AWS Identity and Access Management \(IAM\) policies](auth-and-access-control-iam-identity-based-access-control.md#customer-managed-policies)\.

**[State Manager](systems-manager-state.md)**
+ [Update SSM Agent at least once a month using the pre\-configured AWS\-UpdateSSMAgent document](sysman-state-cli.md)\.
+ [Bootstrap EC2 Instances on launch using EC2Config for Windows](http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-configuration-manage.html)
+ \(Windows\) Upload the PowerShell or DSC module to Amazon S3, and use AWS\-InstallPowerShellModule\.
+ Use Amazon EC2 tags to create application groups for your instances\. And then target instances using the `Targets` parameter instead of specifying individual instance IDs\.
+ [Automatically remediate findings generated by Amazon Inspector by using Systems Manager](https://aws.amazon.com/blogs/security/how-to-remediate-amazon-inspector-security-findings-automatically/)\.
+ [Use a centralized configuration repository for all of your SSM documents, and share documents across your organization](ssm-sharing.md)\.

**[Managed Instances](managed_instances.md)**
+ Systems Manager requires accurate time references in order to perform its operations\. If your instance's date and time are not set correctly, they may not match the signature date of your API requests\. In some cases, this will lead to errors or incomplete functionality\. For example, instances with incorrect time settings will not be included in your lists of managed instances\.

  For information on setting the time on your instances, see the following topics: 
  +  [Setting the Time for Your Linux Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/set-time.html)
  +  [Setting the Time for a Windows Instance](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/windows-set-time.html)