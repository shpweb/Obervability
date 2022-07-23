**This is for Obervability and Monitoring Workshop. **

**Plan**: 
Take a complex multi-container application and prepare it with the setup and used case so that the candidate (workshop attendee) can hands-on all the tools like EFK stack, prometheus, grafana, Istio, etc. 

**Reference Application**: 
Online Boutique App on Google Cloud with GKE - a project from GitHub (https://github.com/GoogleCloudPlatform/microservices-demo)

This GitHub project implement the Microservice based application (Online Boutique) on GKE (Google). We have to prepare it for setting up with tools like EFK stack, prometheus, grafana, Istio, etc.

**Steps for Prometheus & Monitoring Setup on above app:**
1. Create a Project in Google Cloud Platform. 
2. Create a VPC network named 'default' and with automatic subnet / IP allocation (for testing) 
3. As per the GitHub repo, implement steps to create online boutique app. 
4. It will create a 4 Node GKE Cluster with 11 microservices. (however we can modify to differenct instance type and also number of nodes to 3 as GCP has limitations with quota - 8 vCPU per zone and 4 Public IPs only allowed.)
5. Test online boutique URL with external frontend IP (as per the above GitHub repo step)
6. Prometheus & Grafana Setup  
   ***Beginner: Create a separate new VM for Prometheus & Grafana.***
      - [Install and configure prometheus server as per the requirement](./prometheus.md) // Test prometheus URL with that node's public IP:9090
      - [Install and configure grafana service on the same node as preometheus](./grafana.md) // Test Grafana URL with that node's public IP:3300
      - Configure Prom. and Grafana dashboard
      - Have some sample monitor and sample dashboard  
      - Install node_exporter and cAdvisor on k8s nodes (to get metrics from the k8s noded and respective pods) 
      - configure /etc/prometheus/prometheus.yaml file to add new job_name and statics_config for node_exporter, cAdvisor, alert_manager, etc (whichever applicable)
   
   ***Advanced: Run Prometheus & Grafana on K8S cluster created on above nodes (with separate namespace)***
          *Reference: [GITHUB: prometheus_operator/kube_prometheus](https://github.com/prometheus-operator/kube-prometheus)*  
      - The same cluster (k8s nodes) to be used for deploying prometheus and grafana manifest as cluster deployment. (Ref: https://computingforgeeks.com/setup-prometheus-and-grafana-on-kubernetes/)
      - open google cloudshell editor and clone the repo 'kube-prometheus'
      - For publishing Prometheus dashboard on external, we have to add NodePort in prometheus_service.yaml [refer](./prometheus_NodePort_append.yaml)
      - for grafana publish as NodePort - 
      - Once NodePort updated in prometheus and grafana, their respective dashboards can be available on all the nodes with published port.
      - Configure Prom. and Grafana dashboard
      - Have real time monitor metric from the online boutique app
 7.Setup with Istio
 8. Tracing Setup (Jeager) 
 9. Hands-on lab demo
 
 ### Reference

- [GitHub: helm-chart for Kube_Prometheus_Grafna Stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack)
- [acloudguru course: DevOps Monitoring DeepDive](https://learn.acloud.guru/course/852a204f-8dff-4196-bcf8-922a25cc5a64/learn/2e97da96-371f-4e14-ac2a-3ef64c5db272/b214237b-8d34-445f-b8f1-a6e2c2189d15/watch)
