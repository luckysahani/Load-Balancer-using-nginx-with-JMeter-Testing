# Load-Balancer-using-nginx-with-JMeter-Testing
Create three virtual machines ( some machines can sit on local, and some can be on cloud platform, at least one virtual machine has to be on cloud platform), say Machine A, B and C.    Run two server instances on machine A and machine B. Deploy the Load Balancer on machine C. A client instance sends the request to the server through C. C monitors the load on A and B and appropriately redirects the incoming requests between A and B. 

Instructions
=====================================
The three machine are as follows:
VM in local machine as server : 172.16.133.128
Local machine as load balancer: 172.17.0.1
AWS machine as server: 52.37.164.69

Please us the port 8080 for the server.

Ip
-------------
Machine A (Server) : http://52.37.164.69:8080/
Machine B (Server) : http://172.16.133.128:8080/
Machine C (Load Balancer): http://172.17.0.1/

Server
--------------
Makesure you have nodejs installed along with it's dependencies

nodejs server.js

Load balancer
--------------
The load balancer code is in default file. Update the nginx’s configuration in the following directory: /etc/nginx/sites-available/
Replace the content of default in that folder to our's
After that, run reload the nginx configuration

cd /etc/nginx/sites-available/
sudo vim default  
sudo nginx -s reload

JMeter
--------------
For JMeter testing, use sudo jmeter -n -t final_test.jmx -l log.jtl
All the configuration is saved in jmeter.

You can change ThreadGroup.num_threads=10000 to change number of threads.