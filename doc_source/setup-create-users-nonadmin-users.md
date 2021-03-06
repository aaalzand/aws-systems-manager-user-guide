# Task 3: Create Users and Assign Permissions<a name="setup-create-users-nonadmin-users"></a>

Create IAM users for the individuals who require access to AWS Systems Manager, and add each user to the appropriate user group to ensure that they have the right level of permissions\. 

Depending on whether the user accounts for this group were already created, use one of the following procedures:

**To create users and add permissions**

1. In the navigation pane of the IAM console, choose **Users**, and then choose **Add user**\.

1. For **User name**, enter the name that the user will use to sign in to AWS Systems Manager\.

1. To allow the user access to the AWS API, AWS CLI, AWS SDK, and other development tools, select the check box next to **Programmatic access**\.

   This creates an access key for the new user\. You can view or download the access keys when you get to the **Final** page\. 

1. To allow the user access to the AWS Management Console, select the check box next to **AWS Management Console access**\. If you choose **Custom password**, enter an initial password for the user\. You can optionally select **Require password reset** to force the user to create a new password the next time the user signs in\. 

1. Choose **Next: Permissions**\.

1. On the **Set permissions for user** page, choose **Add user to group**\.

1. In the group list, choose the user group to add the user to, and then choose **Next: Tags**\.

1. \(Optional\) Add one or more tag key\-value pairs to organize, track, or control access for this user, and then choose **Next: Review** to see the list of group memberships that the new user is joining\. 

1. Choose **Create user**\.

1. To view the users' access keys \(access key IDs and secret access keys\), choose **Show** next to each password and access key that you want to see\. To save the access keys, choose `Download .csv` and then save the file to a safe location\.
**Important**  
This is your only opportunity to view or download the secret access keys, and you must provide this information to your users before they can use the AWS API or AWS CLI\. Save the user's new access key ID and secret access key in a safe and secure place\. **You will not have access to the secret keys again after this step\.**

1. Provide each user with his or her credentials\. On the final page you can choose **Send email** next to each user\. Your local mail client opens with a draft that you can customize and send\. The email template includes the following details for each user:
   + User name
   + URL of the account sign\-in page\. Use the following example, substituting the correct account ID number or account alias:

     ```
     https://AWS-account-ID or alias.signin.aws.amazon.com/console
     ```

   For more information, see [How IAM Users Sign In to AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_sign-in.html) in the *IAM User Guide*\.
**Important**  
The user's password is not included in the generated email\. You must provide them to the user in a way that complies with your organization's security guidelines\.

**To add permissions for an existing user**

1. In the IAM console navigation pane, choose **Users**\.

1. Choose the name of the user to add to a group, and then choose **Add permission**\.

1. For **Add user to group**, select the box next to the group to add the user to, such as **SSMUserGroup**, or the name of a different user group that you created\.

1. Add any other available permission policies to assign to the user\.

1. Choose **Next: Review** to see the list of group memberships that will be added to the new user\.

1. Choose **Add permissions**\.

Continue to [Step 4: Create an IAM Instance Profile for Systems Manager](setup-instance-profile.md)\.