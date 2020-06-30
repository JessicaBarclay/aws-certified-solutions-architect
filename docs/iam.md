##### Identity Access Management

* Users
* Groups
 - If you have Users in a Group, and a Policy is applied to the Group, the Policy will apply to the Users automatically.
* Roles
* Policies 
 - Policies are applied to the other three
- The “root account” is simply the account created when you first set up your AWS account. It has complete Admin access. Should be used for billing only.
- New Users have NO permissions when first created
- New Users are assigned an Access Key Id & Secret Access Key hen first created
- These are not the same as a password. You cannot use the Acces key & Secret Access key to login into the console. You can, however, use it to access AWS via APIs and Command-Line
- You only get to view these once. If you lose them you have to regenerate them
- Always set up MFA on your root account.
- You can set up password rules and rotation.

##### Organizations

Always enable MFA on the root account
Always use strong complex passwords on that account
Paying account should be for billing only. Don’t deploy resources from that account
Enable/Disable AWS services using Service Control Policies either on organizational units(OUs) like a group(HR/Finance for example) or on individual accounts