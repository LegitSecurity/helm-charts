<p align="center">
  <a href="https://legitsecurity.com" target="_blank" align="center">
    <img src="https://www.legitsecurity.com/hubfs/Legit%20Security%20-%20white%2c%20logo%20left.svg" width="425">
  </a>
  <br />
</p>

# Legit Kubernetes Agent

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square)

## How to use Legit Helm charts

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) for instructions.

After Helm is installed, add the Legit Security Helm repo.

```console
helm repo add legit https://helm.legitsecurity.com
```

### Installing the Legit Kubernetes Agent (manual install):

To install the agent under the name <RELEASE_NAME>.
First, acquire the Agent Identifier from the Legit Platform integrations page.
Then, install the agent on your Kubernetes cluster using the following command -

```console
helm upgrade --install <RELEASE_NAME> \
--set agent.identifier='<AGENT_IDENTIFIER>' \
--namespace legit --create-namespace \
legit/legit-kubernetes-agent
```

### Uninstalling the Chart

To uninstall an Agent deployment named <RELEASE_NAME>:

```bash
helm uninstall <RELEASE_NAME>
```

The command removes all the Kubernetes components associated with the chart and deletes the Helm release.

## All configuration options

The following table lists the configurable parameters of the chart. Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| agent.endpoint | string | `"https://app.legitsecurity.co/broker"` |  |
| agent.identifier | string | `""` | Agent identifier acquired from the Legit platform |
| fullnameOverride | string | `""` |  |
| image.broker.pullPolicy | string | `"IfNotPresent"` |  |
| image.broker.repository | string | `"ghcr.io/legitsecurity/legit-broker"` |  |
| image.broker.tag | string | `"v0.5"` |  |
| image.proxy.pullPolicy | string | `"IfNotPresent"` |  |
| image.proxy.repository | string | `"ghcr.io/legitsecurity/legit-kubectl-proxy"` |  |
| image.proxy.tag | string | `"1.0.0"` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"500m"` |  |
| resources.limits.memory | string | `"512Mi"` |  |
| resources.requests.cpu | string | `"500m"` |  |
| resources.requests.memory | string | `"512Mi"` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | object | `{}` |  |
