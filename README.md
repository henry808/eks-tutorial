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


