## coreos-ec2-cloudformation
**AWS CloudFormation template for running CoreOS etcd clusters on EC2.**
 
### Overview
CoreOS provides excellent documentation, and you can get up and running quickly with the stack available on the CoreOS site. In a quest to use DNS for service discovery, and have the ability to scale my worker/minion nodes independently, I created a CloudFormation template to do just that. 

#### Required AWS Resources

* VPC
* Multiple Subnets
* Route53 Hosted Zone (private)
* Key Pair

### Using the template





