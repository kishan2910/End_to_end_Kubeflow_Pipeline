# End_to_end_Kubeflow_Pipeline
In this project, complete kubeflow pipeline has been created to deploy and manage machine learning model. 

## Requirements

## Requirement 1: Install Docker Desktop
https://www.docker.com/products/docker-desktop/

## Requirement 2: Install minikube
https://minikube.sigs.k8s.io/docs/start/

## Requirement 1: Deploy kubeflow pipelines
https://www.kubeflow.org/docs/components/pipelines/v1/installation/localcluster-deployment/

In the official document, the path suggested for "platform-agnostic-pns" is changed to "platform-agnostic". 


For windows run following commands in Windows PowerShell (administrator) to deploy kubeflow pipelines

'''
set PIPELINE_VERSION=2.2.0 
kubectl apply -k "github.com/kubeflow/pipelines/manifests/kustomize/cluster-scoped-resources?ref=$PIPELINE_VERSION"
kubectl wait --for condition=established --timeout=60s crd/applications.app.k8s.io
kubectl apply -k "github.com/kubeflow/pipelines/manifests/kustomize/env/platform-agnostic?ref=$PIPELINE_VERSION"
'''

Wait for approx 20 mins to run all the pods
You can check status in command prompt

'''
kubectl get pod -A
'''