
# Create the helmchart
```bash
helm create webapp1
```

# Follow along with the video
- Create the files per the video, copying and pasting from templates-original
- you can also use the files in the solution folder


# Install the first one
```bash
helm uninstall mywebapp-release -n default
```

# Install the first one
```bash
helm install mywebapp-release webapp1/ --values webapp1/values.yaml
```

# Upgrade after templating
```bash
helm upgrade mywebapp-release webapp1/ --values webapp1/values.yaml
```

# Accessing it
```bash
minikube start
```
```bash
minikube tunnel
```

# Create dev/prod
```
k create namespace dev
k create namespace prod
helm install mywebapp-release-dev webapp1/ --values webapp1/values.yaml -f webapp1/values-dev.yaml -n dev
helm install mywebapp-release-prod webapp1/ --values webapp1/values.yaml -f webapp1/values-prod.yaml -n prod
helm ls --all-namespaces
```
