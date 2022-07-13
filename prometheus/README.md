### Prometheus Reference Architecture: 
<img src="https://user-images.githubusercontent.com/92606493/178771795-264ccfcc-904b-44c2-90b8-f7d2d7c8d4c3.png" Width="100" Height="100">

###### Monitoring Setup
       - Collector (Self/ Exporter)
       - Reporter/ Shipper (Prometheus through scraping)
       - Time Series Storage (Prometheus, PromQL)
       - Visualizer (Grafana)
       - Alerting (Prometheus, AlertManager)
       
###### Types of Metrics
       - Business Metrics
       - Application Performance Metrics
         - Application throughput (Requests/min)
         - 
       - System Metrics
         - CPU Usage
         - Memory Usage
         - Disk I/O
