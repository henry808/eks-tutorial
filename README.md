# AWS EKS Tutorial
(for MACOS)

## Prerequisites

### 1 Install awscli

```bash
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
aws --version
```

```bash
pip3 install awscli --upgrade --user
```

### Set up credentials

1. Set up an IAM user and give them permissions for EKS
2. on local computer enter credentials of IAM user:

```bash
aws configure
```

### 2 Install Install eksctl

(using homebrew )

```bash
brew tap weaveworks/tap
brew install eksctl
brew upgrade eksctl && brew link --overwrite eksctl
eksctl version
```

### 3 Install and configure kubectl

(already installed by homebrew with eksctl)

## SET UP EKS CLUSTER

###Activate AWS STS

Go to console and activate region (https://console.aws.amazon.com/iam/home?region=us-east-2#/account_settings).

### Create Cluster

```bash
eksctl create cluster --config-file template/test-eks-cluster.yaml
```

```
[ℹ]  if you encounter any issues, check CloudFormation console or try 'eksctl utils describe-stacks --region=us-west-2 --cluster=test-cluster'
[ℹ]  CloudWatch logging will not be enabled for cluster "test-cluster" in "us-west-2"
[ℹ]  you can enable it with 'eksctl utils update-cluster-logging --enable-types={SPECIFY-YOUR-LOG-TYPES-HERE (e.g. all)} --region=us-west-2 --cluster=test-cluster'
[ℹ]  Kubernetes API endpoint access will use default of {publicAccess=true, privateAccess=false} for cluster "test-cluster" in "us-west-2"
[ℹ]  2 sequential tasks: { create cluster control plane "test-cluster", 2 sequential sub-tasks: { no tasks, create managed nodegroup "ng-linux" } }
[ℹ]  deploying stack "eksctl-test-cluster-cluster
```


