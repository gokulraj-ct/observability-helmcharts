## One-Click Observability 

One-Click Observability is a simplified approach to setting up monitoring, logging, and tracing for applications with minimal manual configuration. It typically involves automated instrumentation, pre-configured dashboards, and seamless integration with observability tools like Grafana, Prometheus, Loki, and OpenTelemetry.

For more details about the tools and configuration, [Refer](./Observability/README.md)

To deploy monitoring tools, 

prerequisites,

- [ ] helm installed
- [ ] EKS Cluster 

**Install helm**

```
sudo apt update && sudo apt upgrade
sudo apt install wget -y
wget -O helm.tar.gz https://get.helm.sh/helm-v3.13.0-linux-amd64.tar.gz
sudo tar -zxvf helm.tar.gz
sudo mv linux-amd64/helm /usr/local/bin/helm
```


**Install using helm charts**

Below the command for install monitoring tools using helm charts,

1. Run the command,
```
helm init
helm dependency update
helm install <Release_name> </path/to/helm_chart> --values /path/to/grafana_values.yaml --values /path/to/alloy_values.yaml --values /pathto/tempo_values.yaml --values /path/to/prometheus_values.yaml --values /path/to/fluentbit_values.yaml --values /path/toloki-distributed_values.yaml --values /path/to/prometheus-msteams-values.yaml --values /path/to/alertmanager_values.yaml --values /path/tokubescape_values.yaml --values /path/to/custom_install.yaml
```
__Note:__ Adjust the path of values files.
    
**Install via helmfile**

1. Run the following command
```
helm plugin add https://github.com/databus23/helm-diff
helmfile apply
```

