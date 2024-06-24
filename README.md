### Activities

1. Create simple pod

2. Lets create a pod spec for nop commerce (shaikkhajaibrahim/nopcommercejune2024:070624)
   kubectl get pods
   kubectl get all
   kubectl describe pod nop-pod
   kubectl get pods -o wide
   kubectl get pods -w
   kubectl get pods --show-labels
   kubectl get pods -l "app=nop"
   kubectl get pod nop-pod --output='yaml'

   kubectl apply -f nop-pod.yaml
   kubectl delete -f nop-pod.yaml
   

3. Demonstrate init containers
   
    kubectl exec podName -c containerName -- pwd(command)
    kubectl exec podName -c containerName -it -- /bin/bash(sh)


4. Create a pod manifest for mysql where we need to pass environmental variables

5. Create a pod manifest for postgres where we need to pass environmental variables

6. ReplicaSet example

7. deployment and rollowing update

8. Service (Front End & Back end service)

9. Lets create a spring petclinic rs with loadbalancer service.image: shaikkhajaibrahim/spcjan2024:1.0

10. Container probs

11. Job & Cron Jobs

12. Config Map & Secret
    - Mysql
    - PostgressSQL
    - Mongo DB

13. Namespaces



### Create AKS Cluster

export RANDOM_ID="$(openssl rand -hex 3)"
export MY_RESOURCE_GROUP_NAME="myAKSResourceGroup$RANDOM_ID"
export REGION="eastus"
export MY_AKS_CLUSTER_NAME="myAKSCluster$RANDOM_ID"
export MY_DNS_LABEL="ltdevops$RANDOM_ID"

az group create --name $MY_RESOURCE_GROUP_NAME --location $REGIONaz 

aks create \    
    --resource-group $MY_RESOURCE_GROUP_NAME \    
    --name $MY_AKS_CLUSTER_NAME \    
    --node-count 2 \    
    --node-vm-size 'Standard_B2s'
    
az aks get-credentials --resource-group $MY_RESOURCE_GROUP_NAME --name$MY_AKS_CLUSTER_NAME

## Delete AKS Cluster

az group delete --name $MY_RESOURCE_GROUP_NAME --yes --no-wait

