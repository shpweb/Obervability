**This is for Obervability and Monitoring Workshoop. **

**Plan**: 
Take a complex multi-container application and prepare it with the setup and used case so that the candidate (workshop attendee) can hands-on all the tools like EFK stack, prometheus, grafana, Istio, etc. 

**Reference Application**: 
Online Boutique App on Google Cloud with GKE - a project from GitHub (https://github.com/GoogleCloudPlatform/microservices-demo)

This GitHub project implement the Microservice based application (Online Boutique) on GKE (Google). We have to prepare it for setting up with tools like EFK stack, prometheus, grafana, Istio, etc.

**Steps for Prometheus & Monitoring Setup on above app:**
1. Create a Project in Google Cloud Platform. 
2. Create a VPC network named 'default' and with automatic subnet / IP allocation (for testing) 
3. As per the GitHub repo, implement steps to create online boutique app. 
4. It will create a 4 Node GKE Cluster with 11 microservices. 
5. Test online boutique URL with external frontend IP (as per the above GitHub repo step)
6. Allow Firewall rule for one of the nodes for SSH allow (for testing allowed all traffic for a node) 
7. SSH via console or browser to that one node
8. Install and configure prometheus service on that node. (Refer ./prometheus.md)
9. Test prometheus URL with that node's public IP:9090
10. Install and configure grafana service on the same node (rfere ./grafana.md)
11. Test Grafana URL with that node's public IP:3300

