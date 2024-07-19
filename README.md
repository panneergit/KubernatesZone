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
   > kubectl describe deployment nginx-deployment
   > kubectl rollout history deployment/nginx-deployment
   > kubectl rollout history deployment/nginx-deployment --revision=2
   > kubectl rollout undo deployment/nginx-deployment
   > kubectl rollout undo deployment/nginx-deployment --to-revision=2

   > kubectl scale deployment/nginx-deployment --replicas=10
   > kubectl autoscale deployment/nginx-deployment --min=10 --max=15 --cpu-percent=80


8. Service (Front End & Back end service)

9. Lets create a spring petclinic rs with loadbalancer service.image: shaikkhajaibrahim/spcjan2024:1.0

10. Container probs

11. Job & Cron Jobs

12. Config Map & Secret
    - Mysql
    - PostgressSQL
    - Mongo DB

13. Namespaces

14. PVC & PV

15. DeamanSet & Node Selector

16. Statefull Set

17. Ingress

18. Annotation - Deployment (Rolling update and Rollowing back)

19. Helma & Kostimize



### Create AKS Cluster

export RANDOM_ID="$(openssl rand -hex 3)" 
export MY_RESOURCE_GROUP_NAME="myAKSResourceGroup$RANDOM_ID" 
export REGION="eastus" 
export MY_AKS_CLUSTER_NAME="myAKSCluster$RANDOM_ID" 
export MY_DNS_LABEL="ltdevops$RANDOM_ID" 

## Create Resource Group

az group create --name $MY_RESOURCE_GROUP_NAME --location $REGION

## Create Kubernates Cluster

az aks create \    
    --resource-group $MY_RESOURCE_GROUP_NAME \    
    --name $MY_AKS_CLUSTER_NAME \    
    --node-count 2 \    
    --node-vm-size 'Standard_B2s'

az aks create --resource-group $MY_RESOURCE_GROUP_NAME --name $MY_AKS_CLUSTER_NAME --node-count 2 --node-vm-size 'Standard_B2s'

## Get credentails
az aks get-credentials --resource-group $MY_RESOURCE_GROUP_NAME --name $MY_AKS_CLUSTER_NAME

## Echo credentails for printing
echo "az aks get-credentials --resource-group $MY_RESOURCE_GROUP_NAME --name $MY_AKS_CLUSTER_NAME"

## Enable Autocomplete - Option
    # Windows
    source <(kubectl completion bash)

    # Linux / Mac
    echo"source <(kubectl completion bash)" >> ~/.bashrc

## Delete AKS Cluster => Deleting resourcve group

az group delete --name $MY_RESOURCE_GROUP_NAME --yes --no-wait


az group delete --name 'myAKSResourceGroup228d56' --yes --no-wait

