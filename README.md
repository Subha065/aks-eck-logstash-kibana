# aks-eck-logstash-kibana
# Deploy Logstash and Filebeat On AKS With ECK and SSL

## Architecture:

![architecture](https://user-images.githubusercontent.com/98942600/186127228-9f2769a3-9378-4ebb-891b-9eaa0bb03044.jpg)

## Steps to deploy logstash and filebeat on AKS cluster with ECK and SSL:

### Step 1: Create an 3 node AKS cluster

az aks create --resource-group resourceGroupName --name clusterName --node-count 1 --generate-ssh-keys
  
### Step 2: Connect to the AKS cluster
  
az aks get-credentials --resource-group resourceGroupName --name clusterName

### Step 3: Install the ECK operators

kubectl create -f https://download.elastic.co/downloads/eck/2.3.0/crds.yaml
kubectl apply -f https://download.elastic.co/downloads/eck/2.3.0/operator.yaml

Monitor the operator logs
kubectl -n elastic-system logs -f statefulset.apps/elastic-operator
 
### Step 4: Apply simple Elastic search cluster 

kubectl apply -f elasticsearch.yaml

Check for the elastic search service:
kubectl get elasticsearch
  

 

  
