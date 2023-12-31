### Scope

#### Features
- [ ] Easy retention period configuration support.
- [x] Log based Alerting
- [x] Integration with Grafana for Loki Dashboards and easy alerting management.
- [x] Integration with AlertManager.
- [ ] High Available Loki Stack.
- [ ] PVC Backup and Recovery for Disaster Management
- [ ] Performance Testing for Components.
- [ ] Chaos Testing for components.
- [ ] Observability support for Loki Stack Components.
- [x] Different storageclass support based on cloud provider storage class.
- [ ] LogQL ChatGpt Assistant for easy query curation and testing.
- [x] Full Local Developer Experience with Super Charged App templates.
- [ ] Cloud Native Cost Monitoring
- [ ] IAM Support
- [ ] Externalised through Emissary for Easy Access
- [ ] Enable Automatic PVC resizing when goes beyond user threshold
  
#### DevSecOps
  - [ ] Container Security Powered by Trivy (refer -> https://aquasecurity.github.io/trivy/v0.48/ to understand what is covered in those scans)
  - [x] Helm Chart Security Scan powered by Kubescape (refer -> https://github.com/kubescape/kubescape to understand what is convered in those scans)
  - [x] Automatic Changelog Management
  - [x] Hosted Helm Charts for Different Environments.
  - [ ] Automatic progression of charts across different kubernetes envs.
  - [ ] Directly patch container image vulnerabilities based on Trivy Results



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


