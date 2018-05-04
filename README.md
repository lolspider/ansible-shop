ansible-shop  
this project is defined to create sprint-boot-docker.
******
ansible-version:2.5.2

******
### Variables  
    group_vars/  

define guest's port you can access  
   >guest_port: 8080  

expose container's port  
   >host_port: 80  

Amount of time and number of times to wait when connecting to web after startup, to verify that web is running. Total time to wait = delay * retries, so by default this role will wait up to 50 seconds before timing out.    
   >web_connection_retries: 5  
   >web_connection_delay: 10  

### Dependencies  
   >geerlingguy.docker  
   >geerlingguy.pip      

## How To Use  
First  
   >git clone https://github.com/lolspider/ansible-shop.git  

Then  
   >cd ansible-shop  
   >ansible-galaxy install -r requirements.yml --roles-path=./plugins  

Finally  
   >run ansible-playbook in your way  
