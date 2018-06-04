##### fluend port configuration for client and server
  >fluentd_port: 24224

#####fluentd parse expression in td-agent.conf, default:  
#####reparse record log with expression,for example:  
#####old log:  {"log":"Hello World"}  
#####new log:  {"log":"Hello World"}  
  >fluentd_parser: /^(?<log>\w+\s\w+)/

#####delay or timeout for checking tcp ports
  >fluentd_tcp_delay_time: 5  
  >fluentd_tcp_timeout: 30
