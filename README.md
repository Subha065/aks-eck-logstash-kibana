# aks-eck-logstash-kibana
# Deploy Logstash and Filebeat On AKS With ECK and SSL

## Architecture:

![architecture](https://user-images.githubusercontent.com/98942600/186127228-9f2769a3-9378-4ebb-891b-9eaa0bb03044.jpg)

## Steps to deploy logstash and filebeat on AKS cluster with ECK and SSL:

### Step 1: Create an 3 node AKS cluster

az aks create --resource-group <resource-group-name> --name <cluster-name> --node-count 3 --generate-ssh-keys
  
### Step 2: Connect to the AKS cluster
  
az aks get-credentials --resource-group <resource-group-name> --name <cluster-name>
 
  

 

  
