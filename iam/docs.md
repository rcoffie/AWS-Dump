# Dummy notes and research

## this will be converted to a real notes d

Identity base Policies and Resource Base Policy
What is and Identiy base Policy
Identiy base policies are JSON permisssions Policy documents that control what action an identity can perform, on which resources and under what conditions

Inline Policy
Manage Policy Policy 
Aws Managed 
Custom Managed

Resource Base Policies
Resource Based Policies are JSON policy documents that you attach to a resource such as an Amazon s3


Access Control Methods RBAC & ABAC 
Role-Based Access Control 

ABAC
Atrtibute Based Access Control 

Permission Boundries 

Privilege Esclation


IAM Policy Evaluation Logic 


IAM Policy Structure 
An IAM policy is a JSON document that consists of one or more statements 
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": ["s3:*", "ec2:*", "cloudwatch:*"],
            "Resource": "*"
        },
        {
            "Effect": "Deny", 
            "Action": "iam:*",
            "Resource": "*"
        }
    ]
}
The effect element can be Allowed or Deny 
The Actions element is the Specific API action for which you are granting or denying permission 

The Resource Elemen specifies the resource that's affect by the action 
The condition element is optional and cna be used to control when your policy is  in effect 

with conditions 

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": ["s3:*", "ec2:*", "cloudwatch:*"],
            "Resource": "*"
        },
        {
            "Effect": "Deny",
            "Action": "iam:*",
            "Resource": "*",
            "Condition": {
                "StringNotEquals": {
                    "aws:PrincipalArn": "arn:aws:iam::123456789012:user/AdminUser"
                }
            }
        }
    ]
}

Using Role-Based Access Control 


Attribute Based Access Control  (ABAC)
This is use to allow or deny acces to users baseed on Attributes
Apply Permissions Boundary 


AWS Policy Generator 

IAM Policy Simulator