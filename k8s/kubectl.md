# Windows

Kubectl installation:

```
choco install kubernetes-cli
```

Test to ensure the version you installed is up-to-date:

```
kubectl version --client
```

# Linux

Kubectl installation:

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

Test to ensure the version you installed is up-to-date:

```
kubectl version --client
```

## Kubectl autocompletion (for Linux only)

Add the following to `~/.bashrc`:

```
source <(kubectl completion bash)
source /etc/bash_completion
alias k=kubectl
complete -o default -F __start_kubectl k
```

# Adding existing AKS clusters (contexts)

```
az login
az account set --subscription "<subscription-guid>"
az aks get-credentials --resource-group <resource-group-name> --name <aks-name>
```

# Useful kubectl commands

Get pods by node:

```
kubectl get pods -A -o wide --field-selector spec.nodeName=<node>
```