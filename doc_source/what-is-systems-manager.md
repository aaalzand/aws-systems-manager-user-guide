# What Is AWS Systems Manager?<a name="what-is-systems-manager"></a>

AWS Systems Manager is a collection of capabilities for configuring and managing your Amazon EC2 instances, on\-premises servers and virtual machines \(VMs\), and certain other AWS resources\. Systems Manager includes a unified interface that lets you easily centralize operational data and automate tasks across your AWS resources\. Systems Manager shortens the time to detect and resolve operational problems in your infrastructure\. Systems Manager gives you a complete view of your infrastructure performance and configuration, simplifies resource and application management, and makes it easy to operate and manage your infrastructure at scale\.

**Note**  
AWS Systems Manager was formerly known as *Amazon Simple Systems Manager \(SSM\)* and *Amazon EC2 Systems Manager \(SSM\)*\. For more information, see [Service Name and Console Access](#service-naming-history)\.

**Topics**
+ [Systems Manager Capabilities](#features)
+ [How Systems Manager Works](#how-it-works)
+ [Service Name and Console Access](#service-naming-history)
+ [Accessing Systems Manager](#access-methods)
+ [AWS Region Availability](#prereqs-regions)
+ [Systems Manager Limits](#limits)
+ [Pricing](#pricing)
+ [We Want to Hear from You](#welcome-contact-us)
+ [Related Content](#related-content)
+ [Systems Manager Prerequisites](systems-manager-prereqs.md)

## Systems Manager Capabilities<a name="features"></a>

Systems Manager capabilities are grouped into the following capability types:

**Topics**
+ [Resource Groups](#features-rg)
+ [Insights](#features-insights)
+ [Actions](#features-actions)
+ [Shared Resources](#features-shared)

### Resource Groups<a name="features-rg"></a>

[AWS Resource Groups](https://docs.aws.amazon.com/ARG/latest/userguide/welcome.html): An AWS *resource* is an entity you can work with in AWS, such as Systems Manager SSM documents, patch baselines, maintenance windows, parameters, and managed instances; an Amazon Elastic Compute Cloud \(Amazon EC2\) instance; an Amazon Elastic Block Store \(Amazon EBS\) volume; a security group; or an Amazon Virtual Private Cloud \(VPC\)\. A *resource group* is a collection of AWS resources that are all in the same AWS Region, and that match criteria provided in a query\. You build queries in the Resource Groups console, or pass them as arguments to Resource Groups commands in the AWS CLI\. With Resource Groups, you can create a custom console that organizes and consolidates information based on criteria that you specify in tags\. You can also use groups as the basis for viewing monitoring and configuration insights in AWS Systems Manager\.

### Insights<a name="features-insights"></a>

Systems Manager provides the following capabilities for centrally viewing data about your AWS resources\. Choose the tabs to learn more\.

------
#### [ Built\-in Insights ]

[Insights](https://docs.aws.amazon.com/ARG/latest/userguide/viewing-group-insights.html) show detailed information about the resources in your AWS Resource Groups, such as AWS CloudTrail logs, results of evaluations against AWS Config rules, and AWS Trusted Advisor reports\. Insights show information about a single, selected resource group at a time\.

------
#### [ CloudWatch Dashboards ]

[Amazon CloudWatch Dashboards](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html) are customizable home pages in the CloudWatch console that you can use to monitor your resources in a single view, even those resources that are spread across different regions\. You can use CloudWatch dashboards to create customized views of the metrics and alarms for your AWS resources\. 

------
#### [ Inventory Management ]

[Inventory Manager](systems-manager-inventory.md) automates the process of collecting software inventory from managed instances\. You can use Inventory Manager to gather metadata about applications, files, components, patches, and more on your managed instances\.

------
#### [ Configuration Compliance ]

Use [Systems Manager Configuration Compliance](systems-manager-compliance.md) to scan your fleet of managed instances for patch compliance and configuration inconsistencies\. You can collect and aggregate data from multiple AWS accounts and Regions, and then drill down into specific resources that aren’t compliant\. By default, Configuration Compliance displays compliance data about Patch Manager patching and State Manager associations\. You can also customize the service and create your own compliance types based on your IT or business requirements\.

------

### Actions<a name="features-actions"></a>

Systems Manager provides the following capabilities for taking action against your AWS resources\. Choose the tabs to learn more\.

------
#### [ Automation ]

Use [Systems Manager Automation](systems-manager-automation.md) to automate common maintenance and deployment tasks\. You can use Automation to create and update Amazon Machine Images, apply driver and agent updates, reset passwords on Windows instance, reset SSH keys on Linux instances, and apply OS patches or application updates\. 

------
#### [ Run Command ]

Use [Systems Manager Run Command](execute-remote-commands.md) to remotely and securely manage the configuration of your managed instances at scale\. Use Run Command to perform on\-demand changes like updating applications or running Linux shell scripts and Windows PowerShell commands on a target set of dozens or hundreds of instances\. 

------
#### [ Session Manager ]

Use [Session Manager](session-manager.md) to manage your Amazon EC2 instances through an interactive one\-click browser\-based shell or through the AWS CLI\. Session Manager provides secure and auditable instance management without the need to open inbound ports, maintain bastion hosts, or manage SSH keys\. Session Manager also makes it easy to comply with corporate policies that require controlled access to instances, strict security practices, and fully auditable logs with instance access details, while still providing end users with simple one\-click cross\-platform access to your Amazon EC2 instances\. 

------
#### [ Distributor ]

Use [Distributor](distributor.md) to create and deploy packages to managed instances\. Distributor lets you package your own software—or find AWS\-provided agent software packages, such as **AmazonCloudWatchAgent**—to install on AWS Systems Manager managed instances\. Distributor publishes resources, such as software packages, to AWS Systems Manager managed instances\.

------
#### [ Patch Management ]

Use [Patch Manager](systems-manager-patch.md) to automate the process of patching your managed instances with both security related and other types of updates\. You can use Patch Manager to apply patches for both operating systems and applications\. \(On Windows Server, application support is limited to updates for Microsoft applications\.\) This capability enables you to scan instances for missing patches and apply missing patches individually or to large groups of instances by using Amazon EC2 instance tags\. Patch Manager uses *patch baselines*, which can include rules for auto\-approving patches within days of their release, as well as a list of approved and rejected patches\. You can install security patches on a regular basis by scheduling patching to run as a Systems Manager maintenance window task\. For Linux operating systems, you can define the repositories that should be used for patching operations as part of your patch baseline\. This allows you to ensure that updates are installed only from trusted repositories regardless of what repositories are configured on the instance\. For Linux, you also have the ability to update any package on the instance, not just those that are classified as operating system security updates\. For Windows Server, you can also use Patch Manager to update supported Microsoft applications\.

------
#### [ Maintenance Windows ]

Use [Maintenance Windows](systems-manager-maintenance.md) to set up recurring schedules for managed instances to run administrative tasks like installing patches and updates without interrupting business\-critical operations\. 

------
#### [ State Management ]

Use [Systems Manager State Manager](systems-manager-state.md) to automate the process of keeping your managed instances in a defined state\. You can use State Manager to ensure that your instances are bootstrapped with specific software at startup, joined to a Windows domain \(Windows instances only\), or patched with specific software updates\. 

------

### Shared Resources<a name="features-shared"></a>

Systems Manager uses the following shared resources for managing and configuring your AWS resources\. Choose the tabs to learn more\.

------
#### [ Managed Instances ]

A [managed instance](systems-manager-setting-up.md) is any Amazon EC2 instance or on\-premises machine–a server or a virtual machine \(VM\)–in your hybrid environment that is configured for Systems Manager\. To set up managed instances, you need to install SSM Agent on your machines \(if not installed by default\) and configure AWS Identity and Access Management \(IAM\) permissions\. On\-premises machines also require an activation code\.

------
#### [ Activations ]

To set up servers and VMs in your hybrid environment as managed instances, you need to create a managed\-instance [activation](systems-manager-managedinstances.md)\. After you complete the activation, you receive an activation code and ID\. This code/ID combination functions like an Amazon EC2 access ID and secret key to provide secure access to the Systems Manager service from your managed instances\.

------
#### [ Systems Manager Documents ]

A [Systems Manager document](sysman-ssm-docs.md) \(SSM document\) defines the actions that Systems Manager performs\. SSM document types include *Command* documents, which are used by State Manager and Run Command, and *Automation* documents, which are used by Systems Manager Automation\. Systems Manager includes more dozens of pre\-configured documents that you can use by specifying parameters at runtime\. Documents can be expressed in JSON or YAML, and include steps and parameters that you specify\.

------
#### [ Parameter Store ]

[Parameter Store](systems-manager-parameter-store.md) provides secure, hierarchical storage for configuration data and secrets management\. You can store data such as passwords, database strings, and license codes as parameter values\. You can store values as plain text or encrypted data\. You can then reference values by using the unique name you specified when you created the parameter\.

------

## How Systems Manager Works<a name="how-it-works"></a>

Diagram 1 below shows a general example of the different processes that Systems Manager performs when executing an action like sending a command to your fleet of servers or performing an inventory of the applications running on your on\-premises servers\. Each Systems Manager capability, for example Run Command and Maintenance Windows, uses a similar process of set up, execution, processing, and reporting\. 

1. **Configure Systems Manager**: Use the Systems Manager console, SDK, AWS CLI, or AWS Tools for Windows PowerShell to configure, schedule, automate, and run actions that you want to perform on your AWS resources\. 

1. **Verification and processing**: Systems Manager verifies the configurations, including permissions, and sends requests to the SSM Agent running on your instances or servers in your hybrid environment\. SSM Agent performs the specified configuration changes\.

1. **Reporting**: SSM Agent reports the status of the configuration changes and actions to Systems Manager in the AWS cloud\. Systems Manager then sends the status to the user and various AWS services, if configured\.

**Diagram 1: General Example of Systems Manager Process Flow**

![\[Diagram showing how Systems Manager capabilities, for example Run Command or Maintenance Windows, use a similar process of set up, execution, processing, and reporting.\]](http://docs.aws.amazon.com/systems-manager/latest/userguide/images/how-it-works.png)

## Service Name and Console Access<a name="service-naming-history"></a>

 AWS Systems Manager \(Systems Manager\) was formerly known as "Amazon Simple Systems Manager \(SSM\)" and "Amazon EC2 Systems Manager \(SSM\)"\. The original abbreviated name of the service, "SSM", is still reflected in various AWS resources, including a few other service consoles\. Some examples:
+ **AWS CLI commands**: `aws ssm describe-patch-baselines`
+ **AWS Systems Manager Agent**: SSM Agent
+ **AWS Systems Manager documents**: SSM documents
+ **AWS Systems Manager parameters**: SSM parameters
+ **AWS Systems Manager resource ARNs**: `arn:aws:ssm:us-east-2:111222333444:patchbaseline/pb-07d8884178EXAMPLE`
+ **AWS CloudFormation resource types**: `AWS::SSM::Document`
+ **AWS Config rule identifier**: `EC2_INSTANCE_MANAGED_BY_SSM`
+ **AWS Identity and Access Management \(IAM\) managed policy names**: `AmazonSSMReadOnlyAccess`
+ **Service endpoints**: `ssm.us-east-2.amazonaws.com`
+ **Amazon CloudWatch Events event rule wizard**: EC2 Simple Systems Manager \(SSM\)

Systems Manager functionality was previously available only in the [Amazon EC2 console](https://console.aws.amazon.com/ec2/)\. There you’ll still find Systems Manager features and services in the left navigation pane under the headings **SYSTEMS MANAGER SERVICES** and **SYSTEMS MANAGER SHARED RESOURCES**\. However, the Amazon EC2 console offers access to only those Systems Manager features and services released before November 2017\. Systems Manager access through the Amazon EC2 console will be deprecated in the future\. We therefore encourage you to use the [AWS Systems Manager console](https://console.aws.amazon.com/systems-manager/)\. The AWS Systems Manager console offers access to all Systems Manager services, data, and shared resources\. This console also includes dashboards and access to related services that work with Systems Manager to help you manage your AWS resources\.

## Accessing Systems Manager<a name="access-methods"></a>

You can access Systems Manager using any of the following interfaces:
+ The [AWS Systems Manager console](https://console.aws.amazon.com/systems-manager/) — Provides a web interface that you can use to access Systems Manager\.
+ **AWS Command Line Interface \(AWS CLI\)** — Provides commands for a broad set of AWS services, including Systems Manager, and is supported on Windows, Mac, and Linux\. For more information, see [AWS Command Line Interface](https://aws.amazon.com/cli/)\.
+ **AWS Tools for Windows PowerShell** — Provides commands for a broad set of AWS services, including Systems Manager\. For more information, see [AWS Tools for Windows PowerShell](https://aws.amazon.com/powershell/)\.

  On your Windows Server instances, Windows PowerShell 3\.0 or later is required to run certain SSM documents \(for example, the `AWS-ApplyPatchBaseline` document\)\. Verify that your Windows instances are running Windows Management Framework 3\.0 or later\. The framework includes PowerShell\. 
+ **AWS SDKs** — Provides language\-specific APIs and takes care of many of the connection details, such as calculating signatures, handling request retries, and error handling\. For more information, see [AWS SDKs](http://aws.amazon.com/tools/#SDKs)\.

## AWS Region Availability<a name="prereqs-regions"></a>

AWS Systems Manager is available in the AWS Regions listed in the [AWS Systems Manager Supported Regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ssm_region) table in the *AWS General Reference*\. Before starting your Systems Manager configuration process, we recommend that you ensure the service is available in each of the AWS Regions you want to use it in\. 

For on\-premises servers and VMs in your hybrid environment, we recommend that you choose the Region closest to your data center or computing environment\.

## Systems Manager Limits<a name="limits"></a>

For information about Systems Manager resource and usage limits, see [AWS Systems Manager Limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_ssm) in the *AWS General Reference*\.

## Pricing<a name="pricing"></a>

Some Systems Manager capabilities charge a fee\. For more information, see [AWS Systems Manager Pricing](https://aws.amazon.com/systems-manager/pricing/)\.

## We Want to Hear from You<a name="welcome-contact-us"></a>

We welcome your feedback\. To contact us, visit [the AWS Systems Manager forum](https://forums.aws.amazon.com//forum.jspa?forumID=185)\.

## Related Content<a name="related-content"></a>

Systems Manager is also documented in the following references\.
+ [Blogs \(Management tools category\)](https://aws.amazon.com/blogs/aws/category/management-tools/amazon-ec2-systems-manager/)
+ [Blogs \(AWS Systems Manager tags category\)](https://aws.amazon.com/blogs/mt/tag/aws-systems-manager/)
+ [AWS Systems Manager API Reference](https://docs.aws.amazon.com/systems-manager/latest/APIReference/)
+ [Systems Manager AWS Tools for Windows PowerShell](https://docs.aws.amazon.com/powershell/latest/reference/items/Amazon_Simple_Systems_Management_cmdlets.html)
+ [Systems Manager section of the *AWS CLI Command Reference*](https://docs.aws.amazon.com/cli/latest/reference/ssm/index.html)
+  [AWS SDKs](http://aws.amazon.com/tools/#SDKs)
+ [AWS Systems Manager Limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_ssm)