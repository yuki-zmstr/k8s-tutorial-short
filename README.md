### Repository for the K8s in 1 hour video

#### K8s manifest files

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

<br />

> :warning: **Known issue - Minikube IP not accessible**

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:

    minikube service webapp-service

<br />

Get terminal message:
Because you are using a Docker driver on darwin, the terminal needs to be open to run it.

ChatGPT:
"When you use Minikube with the Docker driver, Minikube creates a virtualized environment inside Docker that may handle port forwarding differently than a bare-metal or cloud-based Kubernetes cluster. Minikube often uses dynamic port forwarding from the host (your local machine) to the Minikube virtual machine."

#### Links

- mongodb image on Docker Hub: https://hub.docker.com/_/mongo
- webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
- k8s official documentation: https://kubernetes.io/docs/home/
- webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour
