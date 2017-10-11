# application-loadbalancer-multi-cert
 This cloudformation template is a modification of [CloudFormation Sample Template AutoScalingMultiAZWithNotifications ](https://s3.amazonaws.com/cloudformation-templates-us-east-1/AutoScalingMultiAZWithNotifications.template) that adds a second listener service using an additional SSL cert to demonstrate the feature mentioned in this [blog post] (https://aws.amazon.com/about-aws/whats-new/2017/10/elastic-load-balancing-application-load-balancers-now-support-multiple-ssl-certificates-and-smart-certificate-selection-using-server-name-indication-sni/)


 ### Assumptions:
 - This cloud formation template assumes you have access to modify and create EC2 and VPC resources via your AWS account. 
 - It also assumes you have already set up your aws cli account and have two working SSL certificates uploaded to the AWS Certificate Manager. 

 ## Usage

 This template includes defaults values that will work in the Stelligent labs account with the following command

 ```
 aws cloudformation create-stack --stack-name myteststack \
--template-body file:///AutoScalingMultiAzWithNotificationsAndMultiCerts.template
```

To override the default paramaters you can pass them in via the command line as follows
```aws cloudformation create-stack --stack-name myteststack \
--template-body file:///AutoScalingMultiAzWithNotificationsAndMultiCerts.template \
--parameters ParamaterKey=Certificate1ARN,ParamaterValue=ARNofCert1 \
 ParamaterKey=Certificate2ARN,ParamaterValue=ARNofCert2
 ```

 A full list of parameters and their defaults values can be found in the template file itself. 


