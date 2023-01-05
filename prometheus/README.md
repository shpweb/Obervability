### Prometheus Reference Architecture:[^3] 
<img src="https://user-images.githubusercontent.com/92606493/178771795-264ccfcc-904b-44c2-90b8-f7d2d7c8d4c3.png" Width="750" Height="450">

**Monitoring Setup**
  - Collector (Self/ Exporter)  
  - Reporter/ Shipper (Prometheus through scraping)  
  - Time Series Storage (Prometheus, PromQL)  
  - Visualizer (Grafana)  
  - Alerting (Prometheus, AlertManager)  
       
**Types of Metrics** 
  - Business Metrics  
    - Orders placed
    - User logged in
- Application Performance Metrics  
  - Application throughput (Requests/min)
  - Application latencies
- System Metrics
  - CPU Usage
  - Memory Usage
  - Disk I/O

**Prometheus Metric Types**
  - COUNTER, how many times X happended? 
    - Cumulative metric
  - GAUGE, what is current value of X now? 
    - Up or Down 
  - HISTOGRAM, low long & how big?

**Prometheus Exporter**[^1]

****What Is a Prometheus Exporter?****[^2]  
A Prometheus exporter aggregates and imports data from a non-Prometheus to a Prometheus system. An exporter is considered essential in any cloud-native ecosystem that includes applications that don’t expose Prometheus-supported metrics by default. A Prometheus exporter acts as a proxy between such an applications and the Prometheus server. Exporters use a simple, text-based, key-value format to scrape and expose metrics over time, via HTTP, for aggregation and decision-making.

- ****How Prometheus Exporters Work****  
  Prometheus implements the HTTP pull model to gather metrics from client components. For event-based monitoring, the Prometheus client relies on an exporter that acts as an abstraction layer between the application and the Prometheus server.

  A Prometheus exporter’s working mechanism typically involves the following:
  - Providing a target endpoint that the Prometheus server periodically queries for metrics.
  - Extracting metrics data from a non-Prometheus application.
  - Transforming captured data into a Prometheus ingestible format by leveraging client libraries.
  - Initiating a web server to display metrics through a URL.

#### References:
[^1]:[Prometheus Docs: Exporter](https://prometheus.io/docs/instrumenting/exporters/)  
[^2]:[Prometheus Exporter](https://www.containiq.com/post/prometheus-exporters)
[^3]:[Prometheus GitHub Repo](https://github.com/prometheus) 
