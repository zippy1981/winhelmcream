# WordPress Production Helm Chart on Minikube

This README describes how to start up the WordPress production Helm chart locally using Minikube.

## Prerequisites

- [Minikube](https://minikube.sigs.k8s.io/docs/) installed
- [kubectl](https://kubernetes.io/docs/tasks/tools/) installed
- [Helm](https://helm.sh/docs/intro/install/) installed

## Steps

### 1. Start Minikube

```bash
minikube start
```

### 2. Add Stable Helm Repository (if needed)

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
```

### 3. Deploy the Chart

From the `helmchart-wordpress` directory:

```bash
helm install wordpress-production .
```

### 4. Check Deployment Status

```bash
kubectl get pods
kubectl get svc
```

### 5. Access WordPress

To access WordPress from your browser, use Minikube's service tunnel:

```bash
minikube service wordpress-production-wordpress-service
```

This will open the WordPress site in your default browser.

## Notes

- This chart is designed for production on AKS, but can be tested locally on Minikube (Linux only).
- MySQL and WordPress will run as Linux containers.
- For persistent storage, Minikube uses hostPath volumes by default.

## Cleanup

To remove the deployment:

```bash
helm uninstall wordpress-production
```

---
Maintainer: GitHub Copilot
