# Kubernetes three nodes cluster using Kind
1. Clone the repository `git clone https://github.com/sageil/kind-k8s-cluster.git`
2. Change directory to kind-k8s-cluster or where the repository is cloned
3. From your terminal, run ` kind create cluster --config three-nodes.yaml --name mycluster`
4. Exec into your control plane using `docker exec -it mycluster-control-plane bash`
5. Once in the control plane, confirm you have three nodes by running `kubectl get no`

