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

7. deployment

8. Service (Front End & Back end service)

9. Container probs

10. Job & Cron Jobs

 -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template,
        templatefile, jsonpath, jsonpath-as-json, jsonpath-file, custom-columns,
        custom-columns-file, wide). See custom columns
        [https://kubernetes.io/docs/reference/kubectl/#custom-columns], golang template
        [http://golang.org/pkg/text/template/#pkg-overview] and jsonpath template
        [https://kubernetes.io/docs/reference/kubectl/jsonpath/].