# bzcms Helm Chart.

[bzcms](https://github.com/manjunathkg/bz-charts/) Presentation layer for bizzns apps. Serves static content

 

```console
$ helm install bzcms
```

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release bzcms
```

The command deploys bzcms on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration
 
```

| Parameter                 | Description                                         | Default                           |
|---------------------------|-----------------------------------------------------|-----------------------------------|
| `name`                    | container name                                      | bzcms                         |
| `image`                   | docker image                                        | kplm/bz-web           |
| `imageTag`                | docker image tag                                    | latest                            |
| `replicas`                | number of replicas to run                           | 1                                 |                               |
| `labels`                  | label selector to filter pods by                    | "" (matches everything)           |
| `annotations`             | annotation selector to filter pods by               | "" (matches everything)           |
| `namespaces`              | namespace selector to filter pods by                | "" (all namespaces)               |                            |
| `resources.cpu`           | cpu resource requests and limits                    | 10m                               |
| `resources.memory`        | memory resource requests and limits                 | 16Mi                              |

Setting label and namespaces selectors from the shell can be tricky but is possible (example with zsh):

```console
$ helm install \
  --set labels='app=bzcms\,stage!=prod',namespaces='!kube-system\,!production' \
  bzcms --debug | grep -A4 args
```
