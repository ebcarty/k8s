# Kubernetes
Testing Kubernetes resources through setting up clusters on AWS and running quick demos.

## Tools

1. [kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl) command line tool lets you interact with and control Kubernetes clusters; it looks for a file named config (usually located under the $HOME/.kube directory).  [Cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/) for reference.

_kubeconfig clean-up in 3 steps_

- `kubectl config unset users.<mycluster_name>`
- `kubectl config unset contexts.<mycluster_name>`
- `kubectl config unset clusters.<mycluster_name>`

2. [kops](https://kubernetes.io/docs/setup/production-environment/tools/kops/#creating-a-cluster) provides a way to create kubernetes clusters through the terminal.

_AWS_
- `export KOPS_STATE_STORE=s3://<aws_bucket_name>`
- `export AWS_ACCESS_KEY_ID=$(aws configure get aws_access_key_id)`
- `export AWS_SECRET_ACCESS_KEY=$(aws configure get aws_secret_access_key)`

Example:  `kops create cluster --node-count 2 --node-size t3a.medium --master-size t3a.medium --zones us-east-1b,us-east-1c --networking cilium --cloud-labels "Team=myTeam,Owner=myName,env=T3sTing" er1ck.k8s.local`

3. [helm](https://helm.sh/docs/intro/install/#through-package-managers), sometimes known as the package manager for kubernetes.  Search for software packages on https://artifacthub.io/
