# zerotier

![Version: 1.8.10](https://img.shields.io/badge/Version-1.8.10-informational?style=flat-square) ![AppVersion: 1.8.10](https://img.shields.io/badge/AppVersion-1.8.10-informational?style=flat-square)

securely connected any device

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/k8s-at-home/charts>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.4.2 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install zerotier k8s-at-home/zerotier --set
'args={ZeroTierNetworkId}' --set 'image.tag=1.8.10-[arm64|amd64]'
```

## Installing the Chart

To install the chart with the release name `zerotier`

```console
helm install zerotier k8s-at-home/zerotier
```

## Uninstalling the Chart

To uninstall the `zerotier` deployment

```console
helm uninstall zerotier
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install zerotier \
  --set env.TZ="America/New York" \
    k8s-at-home/zerotier
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install zerotier k8s-at-home/zerotier -f values.yaml
```

## Custom configuration

You need to set the ZeroTier network ID --set 'args={NetworkId}'.
Be aware the hostNetwork is set to true by default.
And if you want the configure somewhere set persistence.config.hostPath.path=...
Don't forget to set the image.tag=1.8.10-[arm64|amd64]


```console

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| args | array | [] | ZeroTier network ID |
| hostNetwork | bool | `true` | ZeroTier should join the Hosts Network |
| persistence.config.hostPath | string | `/var/lib/zerotier-one` | path to zerotier configuration |
| image.tag | string | `latest` | latest-[arch] |

## Changelog

### Version 1.3.3

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.4.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/k8s-at-home/wireguard?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)
