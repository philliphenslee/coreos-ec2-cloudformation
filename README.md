## coreos-ec2-cloudformation
**AWS CloudFormation template for running CoreOS etcd clusters on EC2.**
 
### Overview
CoreOS provides excellent documentation, and you can get up and running quickly with the stack available on the CoreOS site. In a quest to use DNS for service discovery, and have the ability to scale my worker/minion nodes independently, I created a CloudFormation template. The template creates a three node service cluster, and creates an auto scale group for the worker instances.


The template automates the process of creating the DNS SRV records and A records. Then creates security group, launches three instances to form the service cluster. Finally creating the auto scaling group to create the worker instances.


![coreos-cluster](http://ph2.us/github/coreos-ec2-cloudformation/aws-etcd2-cluster-prod.png)


#### Required AWS Resources

* VPC
* Multiple Subnets
* Route53 Hosted Zone (private)
* Key Pair

### Using the template
Download the JSON template file, or clone the git repo. 

```shell
git clone https://github.com/philliphenslee/coreos-ec2-cloudformation.git
```



Use an existing Route53 private DNS Zone, or create a new one..

![DNS](http://ph2.us/github/coreos-ec2-cloudformation/aws-dns-zone.png)




Open the file in CloudFormation, and then click "Create Stack". 

![template](http://ph2.us/github/coreos-ec2-cloudformation/aws-cf-designer.png)




Enter the stack name and the required parameters...

![params](http://ph2.us/github/coreos-ec2-cloudformation/aws-cf-parameters.png)





