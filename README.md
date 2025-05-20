# Kubernetes three nodes cluster using Kind
Install [Kind](https://github.com/kubernetes-sigs/kind)
Install [kubectl](https://kubernetes.io/docs/tasks/tools/)
1. Clone the repository `git clone https://github.com/sageil/kind-k8s-cluster.git`
2. Change directory to kind-k8s-cluster or where the repository is cloned
3. From your terminal, run ` kind create cluster --config three-nodes.yaml --name mycluster`
4. Exec into your control plane using `docker exec -it mycluster-control-plane bash`
5. Once in the control plane, confirm you have three nodes by running `kubectl get no`

## Optional (Dashboard)

1. Install [helm](https://helm.sh/docs/intro/install/)
2. Run to add the dashboard repo to helm repository `helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard`

3. Install the Dashboard's helm chart by running `helm upgrade --install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace --namespace dev-dashboard`

4. Create a service account by running `kubectl apply -f service-account.yaml`

5. Generate the access token to use when accessing the dashboard by running `kubectl -n kube-system create token admin-user` Keep this token as it's required to access the dashboard.

6. Port forward the dashboard to port `8443` by running `kubectl -n kubernetes-dashboard port-forward svc/kubernetes-dashboard-kong-proxy 8443:443`

7. Access the dashboard using `https://localhost:8443`

8. Use the generated token to authenticate to the dashboard after accepting the certificate.
