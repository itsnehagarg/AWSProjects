# AWS EKS🎉

🌻 Amazon Elastic Kubernetes Service (Amazon EKS) is a managed Kubernetes service to run Kubernetes in the AWS cloud and on-premises data centers. 
- EKS is a managed control plane and not managed data plane.
- EKS provides a highly available K8s cluster in terms of control plane components.
- Components in Control plane are managed by AWS.
- AWS provides an easy way to attach your worker nodes to the control plane.
- AWS provides 2 options for the worker nodes namely, EC2 & Fargate(Fargate is a serverless compute services that allows us to run the containers).
- 2 ways of installing K8s on AWS cloud: 1) Create EC2 instances and use some tools such as KOPS, kubeadm etc to setup cluster on AWS without using EKS. 2) Use EKS
- Other way to use K8s is to setup K8s cluster on on-premise servers/ data centre (without using cloud).
- 
