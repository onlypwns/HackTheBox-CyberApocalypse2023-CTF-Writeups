# forensics - Packet Cyclone

So we have a Logs file with .evtx and Some sigma rules

For this challenge I used chainsaw, a neat utility that can help detect sigma rules on Logs

The command I run was

`./chainsaw hunt Logs/ -s sigma_rules/ --mapping /home/dam/chainsaw/mappings/sigma-event-logs-all.yml -r /home/dam/chainsaw/rules/`

And we have an output and we are able to answer the questions when we connect over netcat to the docker container

![Untitled](forensics%20-%20Packet%20Cyclone%20c420d6df240746ae8f5fe8ec1f4429dc/Untitled.png)

![Untitled](forensics%20-%20Packet%20Cyclone%20c420d6df240746ae8f5fe8ec1f4429dc/Untitled%201.png)

After answering some questions we get the flag as output!

![Untitled](forensics%20-%20Packet%20Cyclone%20c420d6df240746ae8f5fe8ec1f4429dc/Untitled%202.png)

### flag: HTB{3v3n_3xtr4t3rr3str14l_B31nGs_us3_Rcl0n3_n0w4d4ys}