# Load-Balancer-using-nginx-with-JMeter-Testing
Create three virtual machines ( some machines can sit on local, and some can be on cloud platform, at least one virtual machine has to be on cloud platform), say Machine A, B and C.    Run two server instances on machine A and machine B. Deploy the Load Balancer on machine C. A client instance sends the request to the server through C. C monitors the load on A and B and appropriately redirects the incoming requests between A and B. 
