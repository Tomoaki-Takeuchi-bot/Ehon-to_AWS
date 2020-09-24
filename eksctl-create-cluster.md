eksctl create cluster \
--vpc-public-subnets **WorkerSubnets の値** \
--name eks-work-cluster \
--region ap-northeast-1 \
--version 1.14 \
--nodegroup-name eks-work-nodegroup \
--node-type t2.small \
--nodes 2 \
--nodes-min 2 \
--nodes-max 5
