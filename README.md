# mock-deploy
This repository is a mock deployment repository to demonstrate the use of Kustomize and ArgoCD for deploying applications to Kubernetes clusters.

**Usage:**
1. Export `KUBECONFIG` environment variable to point to the kubeconfig file.
```bash
export KUBECONFIG=<path-to-kubeconfig-file>
```
2. Generate the kustomize manifests with a dry run and verify that everything looks good.
```bash
kubectl -n <namespace> create -k kustomize/overlays/prod/ --dry-run=client -o yaml | yq  # yq for readability
```
3. Deploy the ArgoCD application. If all permissions are set correctly, the application should be deployed successfully.
```bash
kubectl create -f application.yaml
    