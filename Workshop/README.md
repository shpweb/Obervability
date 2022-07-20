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
6. Create a separate new VM for Prometheus & Grafana.
7. Install and configure prometheus server as per the requirement. (Refer ./prometheus.md) // Test prometheus URL with that node's public IP:9090
8. Install and configure grafana service on the same node as preometheus (rfere ./grafana.md) // Test Grafana URL with that node's public IP:3300
9. Configure Prom. and Grafana dashboard
10. Have some sample monitor and sample dashboard
11. Have real time monitor metric from the online boutique app and visualization on dashboard
12. Repeat above step 6 to 12 for cluster setup for prom. and grafana 
13. Setup with Istio
14. Tracing Setup (Jeager) 
15. Hands-on lab demo
