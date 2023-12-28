### Scope

#### Features
- Easy retention period configuration support.
- Log based Alerting
- Integration with Grafana for Loki Dashboards and easy alerting management.
- Integration with AlertManager.
- High Available Loki Stack.
- PVC Backup and Recovery for Disaster Management
- Performance Testing for Components.
- Chaos Testing for components.
- Observability support for Loki Stack Components.
- Different storageclass support based on cloud provider storage class.
- LogQL ChatGpt Assistant for easy query curation and testing.
- Full Local Developer Experience with Super Charged App templates.
- Cloud Native Cost Monitoring
- Easy User Authentication Support
  
#### DevSecOps
  - Container Security Powered by Trivy (refer -> https://aquasecurity.github.io/trivy/v0.48/ to understand what is covered in those scans)
  - Helm Chart Security Scan powered by Kubescape (refer -> https://github.com/kubescape/kubescape to understand what is convered in those scans)
  - Automatic Changelog Management
  - Hosted Helm Charts for Different Environments.
  - Automatic progression of charts across different kubernetes envs.
  - Directly patch container image vulnerabilities based on Trivy Results
 

### Current Progress

#### Features
- Alerting for Kubernetes based on https://runbooks.prometheus-operator.dev/runbooks
- All default Grafana Dashboards related  to kubernetes and observability components of kube prometheus stack.
- Civo Storage class support.
- All default Grafana Dashboards related  to kubernetes and observability components of kube prometheus stack. These dashboards are coming from upstream projecs like kubernetes-mixin, prometheus-mixin and node-exporter-mixin.
- Full Local Developer Experience with Super Charged App templates.
- 
#### DevSecOps
- Helm Chart Security Scan powered by Kubescape (refer -> https://github.com/kubescape/kubescape to understand what is convered in those scans) (Clusters not scanned currently)
- Automatic Changelog Management
- Hosted Helm Charts on gh-pages


### Installation Instructions

#### Add Helm Repo
```
helm repo add unoplat-observability-prom-stack https://unoplat.github.io/unoplat-observability-prom-stack 
helm repo update
```
#### Install on Local Kubernetes

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace --set prometheus.prometheusSpec.storageSpec.volumeClaimTemplate.spec.storageClassName=local-path --set alertmanager.alertmanagerSpec.storage.volumeClaimTemplate.spec.storageClassName=local-path
```

#### Install on Civo Cloud 

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace
```

### Q and A with unoplat observability prom stack? 

#### ChatGpt Assistant


### Credits
## Base Open Source Projects
- https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
- https://github.com/prometheus-operator/kube-prometheus


