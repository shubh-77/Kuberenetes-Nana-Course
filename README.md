### Repository for the K8s in 1 hour video

##### remove minikube completely

    minikube stop; minikube delete && docker stop $(docker ps -aq) && rm -rf ~/.kube ~/.minikube && sudo rm -rf /usr/local/bin/localkube /usr/local/bin/minikube && launchctl stop '*kubelet*.mount' && launchctl stop localkube.service && launchctl disable localkube.service && sudo rm -rf /etc/kubernetes/ && docker system prune -af --volumes

##### remove minikube completely

     https://stackoverflow.com/questions/73600518/how-do-i-uninstall-minikube-on-a-mac

#### K8s manifest files

- K8S-mongo-webapp
  - mongo-config.yaml
  - mongo-secret.yaml
  - mongo.yaml
  - webapp.yaml

#### K8s commands

##### start Minikube and check status

    minikube start --vm-driver=hyperkit
    minikube status

##### get minikube node's ip address

    minikube ip

##### get basic info about k8s components

    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

##### get extended info about components

    kubectl get pod -o wide
    kubectl get node -o wide

##### get detailed info about a specific component

    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs

    kubectl logs {pod-name}

##### stop your Minikube cluster

    minikube stop
