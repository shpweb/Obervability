# Obervability
## Grafana 

### Visualization tools
Observability, especially at cloud scale, can generate huge volumes of data that become difficult for humans to parse. Visualization tools help to quickly make sense of data by correlating observability data into intuitive graphic displays.  
Grafana is a popular open source analytics platform that enables you to query, visualize, alert on and understand your metrics no matter where they are stored.[^1]

**Grafana with Prometheus**  
Grafana is a popular open source data visualization tool. It has a web interface to create custom dashboards that pull data from Prometheus (using the full power of the Prometheus query API to perform statistical transformations), display multiple metrics using graphical dashboards and can also generate alerts.

Grafana provides powerful and flexible facilities to create graphs of any metric available to Prometheus. 

* [Ref: acloudguru course](acloudguru/README.md)
Note: Grafana can use serveral different data source however for our case, we will be using Prometheus as our data source. 
Data Source in Grafana is a place that is essentially receiving whatever metrics that has already have. 

[DevOps Monitoring DeepDive] (https://learn.acloud.guru/course/852a204f-8dff-4196-bcf8-922a25cc5a64/learn/2e97da96-371f-4e14-ac2a-3ef64c5db272/b214237b-8d34-445f-b8f1-a6e2c2189d15/watch)

* [Refer Grafana's Official Document for](GrafanaOffSite/README.md) [Hands-on tutorial](https://grafana.com/tutorials/grafana-fundamentals/)
* Grafana Setup with MySql and JVM [Hands-on-tutorial](https://pexea12.github.io/posts/05-setup-prometheus-and-grafana-for-mysql-and-jvm/)


* ![This is an image](https://docs.microfocus.com/mediawiki/images/f/f7/SMA_2019.05_monitoring.png) (Ref:https://docs.microfocus.com/doc/Service_Management_Automation_-_SM/2021.05/SMAMonitoring)


### Reference

[^1]: [AWS Observability](https://aws.amazon.com/products/management-and-governance/use-cases/monitoring-and-observability/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc&blog-posts-cards.sort-by=item.additionalFields.createdDate&blog-posts-cards.sort-order=desc)
