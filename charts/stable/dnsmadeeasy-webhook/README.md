# dnsmadeeasy-webhook

![Version: 4.4.1](https://img.shields.io/badge/Version-4.4.1-informational?style=flat-square) ![AppVersion: 1.2.0](https://img.shields.io/badge/AppVersion-1.2.0-informational?style=flat-square)

Cert-Manager Webhook for DNSMadeEasy

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/k8s-at-home/dnsmadeeasy-webhook>
* <https://cert-manager.io>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://charts.jetstack.io | cert-manager | v1.6.2 |
| https://library-charts.k8s-at-home.com | common | 4.3.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install dnsmadeeasy-webhook k8s-at-home/dnsmadeeasy-webhook
```

## Installing the Chart

To install the chart with the release name `dnsmadeeasy-webhook`

```console
helm install dnsmadeeasy-webhook k8s-at-home/dnsmadeeasy-webhook
```

## Uninstalling the Chart

To uninstall the `dnsmadeeasy-webhook` deployment

```console
helm uninstall dnsmadeeasy-webhook
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install dnsmadeeasy-webhook \
  --set env.TZ="America/New York" \
    k8s-at-home/dnsmadeeasy-webhook
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install dnsmadeeasy-webhook k8s-at-home/dnsmadeeasy-webhook -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cert-manager.enabled | bool | `false` | Install cert-manager chart as dependency. Usually this is already installed in the cluster and not needed. |
| certManager.namespace | string | `"cert-manager"` | Namespace where the cert-manager operator was installed to |
| certManager.serviceAccountName | string | `"cert-manager"` | Service account used by the cert-manager |
| generateCerts | bool | `true` | Generate dedicated certs instead of re-using the cert-manager webhook certificate. |
| groupName | string | `"acme.mycompany.com"` | The GroupName here is used to identify your company or business unit that created this webhook. This name will need to be referenced in each Issuer's `webhook` stanza to inform cert-manager of where to send ChallengePayload resources in order to solve the DNS01 challenge. This group name should be **unique**, hence using your own company's domain here is recommended. |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"ghcr.io/k8s-at-home/dnsmadeeasy-webhook"` | Image repository |
| image.tag | string | `"v1.2.0"` | Image tag |
| serviceAccount.create | bool | `true` | Create service account |

## Changelog

### Version 4.4.1

#### Added

N/A

#### Changed

* Upgraded `cert-manager` chart dependency to version `v1.6.2`.

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/dnsmadeeasy-webhook?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)
