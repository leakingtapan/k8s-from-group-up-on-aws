# Single Node Cluster
This module will guide through how to set up singal node kubernetes cluster on AWS.

## Prerequisites
Since kubernetes use docker as container runtime by defualt, install docker on the EC2 instance or use an AMI that has pre-installed docker. The AMI I use is (TODO). Step to provision EC2 instance (TODO)

Then install kubelet:

```
wget https://storage.googleapis.com/kubernetes-release/release/v1.12.1/bin/linux/amd64/kubectl
chmod +x kubectl
```
We will use it to interact with the single node kubenetes cluster that we are going to create.

# Kubelet
Kubelet is the primary “node agent” that runs on each node. Its main responsibility is to spin up Pods on node where it is running on. Pod is a collecion of containers that share some resources. 

Pod is defined by manifest file which could be either Json or Yaml file. The following is a sample Yaml manifest file for nginx server:

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

There are a few ways kubelet reads Pod manifest from:
  1.  a directory it polls for new pod manifests to run
  1.  an URL it polls and downloads pod manifests from
  1.  kubernetes API server

The simplest way to run kubelet is the 1st way. Let's try this by first downloading kubelet:
```
wget https://storage.googleapis.com/kubernetes-release/release/v1.12.1/bin/linux/amd64/kubelet
chmod +x kubelet
```
Then create the manifest folder and start kubelet:
```
cd $HOME
mkdir manifest
sudo ./kubelet --pod-manifest-path ./manifest/
```
Once kubelet is up and running, save the above nginx manifest file inside manifest folder using your favoriest editor. Shortly after that, you will see Pod is created by kubelet. This can be verified using docker:

```

```

Since we are running nginx server, we can connect to it using defined port and pod's IP:
```

```
It works!

Finally, the Pod can be tore down by simply remove the filed under manifest folder.

# Kube API Server



```
kubectl config set-cluster ground-up-cluster --server=http://127.0.0.1:8080 --insecure-skip-tls-verify=true --kubeconfig=single.kubeconfig
kubectl config set-context ground-up-context --cluster=ground-up-cluster --kubeconfig=single.kubeconfig
kubectl config use-context ground-up-context --kubeconfig=single.kubeconfig
sudo cp single.kubeconfig /var/lib/kubelet/kubeconfig
```

# Kube Scheduer


# Kube Controller Manager
```
wget https://storage.googleapis.com/kubernetes-release/release/v1.12.1/bin/linux/amd64/kube-controller-manager
chmod +x kube-controller-manager
```
daemonset, stateful set
