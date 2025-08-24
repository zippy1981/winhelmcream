# winhelmcream Helm Chart

This Helm chart deploys two Windows nodepools:
- **servercore-iis**: Runs IIS on Windows Server Core
- **nanoserver**: Runs a container on Windows Nanoserver

## Prerequisites
- Kubernetes cluster with Windows nodes
- Helm installed
- Node labels for nodepools:
  - `nodepool=servercore` for Server Core nodes
  - `nodepool=nanoserver` for Nanoserver nodes

## Usage

1. **Clone the repository**
   ```pwsh
   git clone <your-repo-url>
   cd winhelmcream/helmchart
   ```

2. **Install the chart**
   ```pwsh
   helm install winhelmcream .
   ```

3. **Customize values**
   Edit `values.yaml` to change image versions, replica counts, etc.

4. **Uninstall the chart**
   ```pwsh
   helm uninstall winhelmcream
   ```

## Files
- `Chart.yaml`: Chart metadata
- `values.yaml`: Default values
- `templates/`: Kubernetes manifests

## Notes
- Ensure your cluster nodes are labeled correctly for node selection.
- The IIS container exposes port 80 by default.

For advanced configuration, edit the deployment and service templates in the `templates/` directory.
