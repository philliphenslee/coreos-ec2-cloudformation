## coreos-ec2-cloudformation
**AWS CloudFormation template for running CoreOS etcd clusters on EC2.**
 
### Overview
[CoreOS](https://coreos.com) provides excellent documentation which allows you to get up and running quickly with the stack available on the CoreOS site. I wanted to use DNS for service discovery, while having the ability to scale the worker/minion nodes independently.


The template automates the process of creating the DNS SRV records and A records. Then creates a security group for the cluster and it launches three instances to form the service cluster. Finally, creating the Auto Scaling group to create the worker instances.

Hope you find this template useful, send me a message if you have any suggestions or feedback.


![coreos-cluster](http://ph2.us/github/coreos-ec2-cloudformation/aws-etcd2-cluster-prod.png)

Learn more about the CoreOS cluster architecture here...

[https://coreos.com/os/docs/latest/cluster-architectures.html](https://coreos.com/os/docs/latest/cluster-architectures.html)


#### Required AWS Resources

* VPC
* Subnet(s)
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

## License
MIT Copyright © [Phillip J. Henslee II](https://github.com/philliphenslee/coreos-ec2-cloudformation/blob/master/LICENSE)








