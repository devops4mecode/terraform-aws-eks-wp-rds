### EKS in AWS for Wordpress 


1. VPC File:
>>It Creates 1 VPC, 2 Subnet, Internet gateway and a Routing table attached with Internet gateway and associated with both the subnet.
2. EKS-Cluster File:
>>It first creates an IAM Role to allow EKS service to manage other AWS services. A security Group attracted our VPC and allow 443(https) and Creates an EKS-Cluster.
3. EKS-Worker-node File:
>>Creates IAM role allowing Kubernetes actions to access other AWS services and A EKS Node Group with 2 nodes with AMI AL2_x86_64 and t2.micro attracted with key for ssh.
4. RDS File:
>> It Creates a Database Instance of MySQL with username and password. These Credentials are stored in Var.tf file.
5. Update KubeConfig File:
>> This File Will update The Kube Configuration File with AWS EKS Cluster.
6. Kubernetes Configuration File:
>> It Creates a PVC For Our Deployment and then Deploys a WordPress Container linked with RDS as Database and has a LoadBlancer Service Exposed at port 80.

### Let Run Them!
“Terraform init” → this will install requiered Plugins
“Terraform Plan” → To Check Resources to be Created.
“Terraform apply” → Execute Every Task.