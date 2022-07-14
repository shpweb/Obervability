# Obervability
## Grafana 

### Visualization tools
Observability, especially at cloud scale, can generate huge volumes of data that become difficult for humans to parse. Visualization tools help to quickly make sense of data by correlating observability data into intuitive graphic displays.  
Grafana is a popular open source analytics platform that enables you to query, visualize, alert on and understand your metrics no matter where they are stored.[^1]

## Grafana with Prometheus[^2]  
Grafana is a popular open source data visualization tool. It has a web interface to create custom dashboards that pull data from Prometheus (using the full power of the Prometheus query API to perform statistical transformations), display multiple metrics using graphical dashboards and can also generate alerts.

Grafana provides powerful and flexible facilities to create graphs of any metric available to Prometheus. 

**Why we are using Grafana when we have Prometheus Web UI?**
* We're going to be using Grafana and not just the native web UI with Prometheus because you'll see that, as you expand out your monitoring platform, you're often not just pulling in data from Prometheus itself. Maybe you have EC2 CloudWatch going on because you're using AWS or maybe you simply have an ELK Stack to process your logs and you want to include that in your visualizations. 
  - #### Grafana Install
  - #### Add a Data Source
  * Data Source in Grafana is a place that is essentially receiving whatever metrics that has already have. There are multiple plug-ins available for Grafana to be used as a data source however for our demo, we will be using prometheus as a data source.
  
  - #### Add a Dashboard

* Course Reference End goal:

![End State Goals](https://user-images.githubusercontent.com/92606493/178727627-6a557f25-129d-4b7c-92d6-e3d8399dfe7b.png)

## Other study docs

1. [Refer Grafana's Official Document for](GrafanaOffSite/README.md) [Hands-on tutorial](https://grafana.com/tutorials/grafana-fundamentals/)
2. GitHub Microservices page - [Refer this](https://microservices-demo.github.io/docs/quickstart.html) Or [[GitHub Repo]](https://github.com/microservices-demo/microservices-demo.github.io)
3. Article- Grafana Setup with MySql and JVM [Hands-on-tutorial](https://pexea12.github.io/posts/05-setup-prometheus-and-grafana-for-mysql-and-jvm/)
4. ![This is an image](https://docs.microfocus.com/mediawiki/images/f/f7/SMA_2019.05_monitoring.png) (Ref:https://docs.microfocus.com/doc/Service_Management_Automation_-_SM/2021.05/SMAMonitoring)
5. GitHub repo - [Srinisbook](https://github.com/srinisbook/Prometheus-grafana)
6. Other Courses on [Udemy](https://thoughtworks.udemy.com/organization/search/?src=ukw&q=grafana) or acloudguru (e.g. Prometheus DeepDive)

### FAQs
1. 
Ans - 

### Reference

[^1]: [AWS Observability](https://aws.amazon.com/products/management-and-governance/use-cases/monitoring-and-observability/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc&blog-posts-cards.sort-by=item.additionalFields.createdDate&blog-posts-cards.sort-order=desc)
[^2]: [acloudguru course: DevOps Monitoring DeepDive](https://learn.acloud.guru/course/852a204f-8dff-4196-bcf8-922a25cc5a64/learn/2e97da96-371f-4e14-ac2a-3ef64c5db272/b214237b-8d34-445f-b8f1-a6e2c2189d15/watch)
