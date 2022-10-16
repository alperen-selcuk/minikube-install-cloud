# minikube-install-cloud

pre-req olarak bir kaç tool yükleyeceğiz.

```
sudo su -

apt-get update
apt-get install -y conntrack socat selinux-utils ebtables ethtool
```


## docker install

curl https://raw.githubusercontent.com/alperen-selcuk/docker-install/main/install-docker.sh | bash -

## kubectl install

curl https://raw.githubusercontent.com/alperen-selcuk/kubectl-install/main/install-kubectl-helm.sh | bash -

## minikube install

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## minikube start

```
minikube start \
--kubernetes-version=1.23.1 \
--vm-driver=none \
--extra-config=controller-manager.node-cidr-mask-size=16 \
--extra-config=controller-manager.allocate-node-cidrs=true \
--extra-config=controller-manager.cluster-cidr=10.244.0.0/16 \
--extra-config=kubeadm.pod-network-cidr=10.244.0.0/16
```
