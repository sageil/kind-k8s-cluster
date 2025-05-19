# Kubernetes three nodes cluster using Kind
1. Clone the repo
2. Change directory to kind-config or where the repo is cloned
3. From your terminal, run ` kind create cluster --config three-nodes.yaml --name mycluster`
4. Exec into your control plane using `docker exec -it mycluster-control-plane bash`
5. Once in the control plane, confirm you have three nodes by running `kubectl get no`

