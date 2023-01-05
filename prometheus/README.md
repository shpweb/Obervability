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
  - SUMMARY
