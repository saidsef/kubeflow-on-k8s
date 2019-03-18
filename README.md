# Kubeflow on Kubernetes Cluster

Kubeflow Pipelines are a new component of Kubeflow that can help you compose, deploy, and manage end-to-end (optionally hybrid) machine learning workflows. Because they are a useful component of Kubeflow, they give you a no lock-in way to advance from prototyping to production. Kubeflow Pipelines also support rapid and reliable experimentation, so users can try many ML techniques to identify what works best for their application.

## Useful Links
 - [Getting Started Kubeflow Pipelines](https://cloud.google.com/blog/products/ai-machine-learning/getting-started-kubeflow-pipelines)
 - [Introducing Kubeflow Composable](https://kubernetes.io/blog/2017/12/introducing-kubeflow-composable/)

# Kubeflow Version
 - Kubeflow v0.4.1

# Prerequisites
 - Git
 - Ksonnet
 - Golang
 - Kubernetes Cluster
 - Kubectl

# Components
 - ambassador
 - argo
 - centraldashboard
 - jupyterhub
 - katib
 - params.libsonnet
 - pytorch-operator
 - seldon
 - spartakus
 - tf-job-operator

# Deployment

```shell
export KUBEFLOW_TAG=0.4.1
export NAMESPACE=kubeflow

git clone https://github.com/saidsef/kubeflow-on-k8s.git

cd kubeflow-on-k8s/

git submodule foreach git pull origin master

mkdir -p /mnt/{katib-mysql,kf-ml-data,kf-openvino,kf-minio}

kubectl apply -f ./deployment --namespace ${NAMESPACE}

ks apply default --namespace ${NAMESPACE} # append `--dry-run` for dry run

kubectl get all -n ${NAMESPACE}

```


