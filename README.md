# ansible-shop
#this project is defined to create sprint-boot-docker.
******
ansible-version:2.5.2

******
#vars  
group_vars/

  #define guest's port you can access  
  guest_port: 8080  

  #expose container's port  
  host_port: 80  

  #Amount of time and number of times to wait when connecting to web after startup, to verify that web is running. Total time to wait = delay * retries, so by default this role will wait up to 50 seconds before timing out.    
  web_connection_retries: 5  
  web_connection_delay: 10  
