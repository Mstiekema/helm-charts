# Helm Charts

Welcome to my helm chart repository!

## Charts

- [rustfs-nginx-static-site](https://github.com/Mstiekema/rustfs-nginx-static-site)

## Usage

Below are generic usage instructions

### CLI

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```bash
helm repo add ALIAS https://Mstiekema.github.io/helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages. You can then run `helm search repo ALIAS` to see the charts.

To install the `CHART_NAME` chart:

```bash
helm install RELEASE_NAME ALIAS/CHART_NAME
```

To uninstall the chart:

```bash
helm uninstall RELEASE_NAME
```

### Kustomize

I personally use `kustomize` with [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
which allows you to import the chart with the yaml below.

```yaml
helmCharts:
  - name: CHART_NAME
    releaseName: RELEASE_NAME
    namespace: default
    repo: https://Mstiekema.github.io/helm-charts
    version: v0.0.0
    valuesFile: values.yaml
```
