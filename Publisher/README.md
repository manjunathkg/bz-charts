# bzpublisher Helm Chart.

[bzpublisher](https://github.com/manjunathkg/bz-charts/) Publishing engine.

 

```console
$ helm install bzpublisher
```

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release bzpublisher
```

The command deploys bzpublisher on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration
 
```
 
$ helm install \
  --set labels='app=bzpublisher\,stage!=prod',namespaces='!kube-system\,!production' \
  bzpublisher --debug | grep -A4 args
```
