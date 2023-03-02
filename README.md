# JasonContainerSandbox
Jason's container sandboxes

### Prerequisites:
- [minikube installed](https://datadoghq.atlassian.net/wiki/spaces/TS/pages/1248530082/How+to+test+Kubernetes+yourself)
- Datadog agent installed 

### Objective
For this Sandbox, we will setup a Promethues integration with autodiscovery.

### Steps
For enabling prometheus scraping, first download the -[prometheus.yaml](https://docs.datadoghq.com/resources/yaml/prometheus.yaml) as an example confiugration file which already has autodiscovery enabled. 

Use the command `kubectl create -f prometheus.yaml` to create the prometheus pod 

Configure the `values.yaml` file to set `enabled: true` for prometheusScrape and serviceEndpoints. 

```
datadog:
  # (...)
  prometheusScrape:
    enabled: true
    serviceEndpoints: true
  # (...)
  ```
  
  
