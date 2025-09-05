kubernetes cluster configration:-

EKSCTL ---Install

cluster means Master or Control plane, we can go with AWS EKS(elastic kubernets service) or eksctl - (The official CLI for Amazon EKS - eksctl)

steps:-
website---https://eksctl.io/installation/

curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)\_amd64.tar.gz" | tar xz -C /tmp

sudo mv /tmp/eksctl /usr/local/bin

eksctl version -------------To check version

---

KUBECTL ---Install

website:-https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html#kubectl-install-update

steps:-

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.33.0/2025-05-01/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv kubectl /usr/local/bin/

kubectl version --client

---

Now eksctl and kubectl configuration done, so by using eksctl we need to create a cluster(EKS-service) in AWS.
-->By using "aws configure" goto I-AM users and check or U can add roles to ec2 instance
-->IAM
Users
kubernetes-admin
Create access key
-->AWS Access Key ID:
AWS Secret Access Key:
Default region name [None]: us-east-1
Default output format [None]:
-->website---https://eksctl.io/getting-started/

apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
name: expense-1
region: us-east-1

managedNodegroups:

- name: expense
  instanceType: m5.large
  desiredCapacity: 3
  spot: true
  ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
  Roles also we have to create manualy and cluster settings also check.
  please follow all instructions to do kubernetes
