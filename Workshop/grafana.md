
**Pre-requisites** for Grafana Installation: 'libfontconfig' package


1. **Install Grafana package (OSS version)** (for debian linux, run 'apt-get install grafana') 
2. ******Reference: ******  
  Download: https://grafana.com/grafana/download?edition=oss&platform=linux  
  Installation: https://grafana.com/docs/grafana/next/setup-grafana/installation/  
  Deploy Grafana on Kubernetes: https://grafana.com/docs/grafana/next/setup-grafana/installation/kubernetes/  

3. run below commands:   
  systemctl daemon-reload  
  systemctl enable grafana-server  
  systemctl start grafana-server  


