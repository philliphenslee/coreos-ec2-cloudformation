## coreos-ec2-cloudformation
**AWS CloudFormation template for running CoreOS etcd clusters on EC2.**
 
### Overview
CoreOS provides excellent documentation, and you can get up and running quickly with the stack available on the CoreOS site. In a quest to use DNS for service discovery, and have the ability to scale my worker/minion nodes independently, I created a CloudFormation template. The template creates a three node service cluster, and creates an auto scale group for the worker instances.


The template automates the process of creating the DNS SRV records and A records. Then creates a security group for the cluster, launches three instances to form the service cluster. Finally creating the Auto Scaling group to create the worker instances.


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



Use an existing Route53 private DNS Zone, or create a new one...

![DNS](http://ph2.us/github/coreos-ec2-cloudformation/aws-dns-zone.png)




Upload the file to CloudFormation and create the stack...

![template](http://ph2.us/github/coreos-ec2-cloudformation/aws-cf-designer.png)




Enter the stack name and the required parameters...

![params](http://ph2.us/github/coreos-ec2-cloudformation/aws-cf-parameters.png)




Launch the stack, take a five minute break...

![instances](http://ph2.us/github/coreos-ec2-cloudformation/aws-instances.png)



Edit the Auto Scaling group and spawn more workers...
![instances-scaled](http://ph2.us/github/coreos-ec2-cloudformation/aws-instances-scaled.png)







