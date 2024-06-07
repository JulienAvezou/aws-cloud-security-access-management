# aws-cloud-security-access-management
Notes from DevSecOps ch.8 AWS Cloud Security &amp; Access Management

Administration vs Usage 
Admin includes:
  - access management
  - network security
Usage includes:
  - EC2 deployment
  - ECR
  - ...

Concept of least privilege access -> every usr should only have permissions they need

Regular review of accesses in organization is important

IAM service controls access mgmnt via users, groups, roles and policies

1. Secure root user
- add MFA
- delete access keys for root user
<img width="728" alt="Capture d’écran 2024-06-06 à 21 16 32" src="https://github.com/JulienAvezou/aws-cloud-security-access-management/assets/62488871/a8d88b7d-488c-478c-a2e6-7e5c6e57155c">

2. Create Admin user
-> the admin will then create other users with less permissions
-> human users vs system users, give each the appropriate access: programmatic for system users and console login for human users

<img width="314" alt="Capture d’écran 2024-06-06 à 21 46 05" src="https://github.com/JulienAvezou/aws-cloud-security-access-management/assets/62488871/fa1138e4-5618-4844-8709-3fd20139a809">
   
Policy is a set of permissions that define what actions someone is able to perform to which resources
-> AWS provides policies out of the box if needed

Groups allow to attach policies to a set of all users belonging to that group

Can enforce password policies for users to comply with
Can also look generate credentials report to get overview of user password setup

3. Create System user
ie. Gitlab User for using in CI/CD pipeline

<img width="556" alt="Capture d’écran 2024-06-06 à 21 54 23" src="https://github.com/JulienAvezou/aws-cloud-security-access-management/assets/62488871/bd5b83ca-10bf-460f-9d4d-35ed3098b3e5">

Role is an AWS identity with permission policies
- Entities assume roles when they need to perform certain actions on resources
- No permanenent credentials
- One service can assume multiple roles
- Can also be used to attach policies to users for temporary periods of time
- AWS provides roles with pre-attached policies out of the box

