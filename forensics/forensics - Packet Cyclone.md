# forensics - Packet Cyclone

So we have a Logs file with .evtx and Some sigma rules

For this challenge I used chainsaw, a neat utility that can help detect sigma rules on Logs

The command I run was

`./chainsaw hunt Logs/ -s sigma_rules/ --mapping /home/dam/chainsaw/mappings/sigma-event-logs-all.yml -r /home/dam/chainsaw/rules/`

And we have an output and we are able to answer the questions when we connect over netcat to the docker container

![Untitled](https://user-images.githubusercontent.com/88723154/227419539-3523451d-b60c-4d13-a291-d731d86c4552.png)

![Untitled 1](https://user-images.githubusercontent.com/88723154/227419556-5f27d43f-25f5-40b6-98fe-c2f2b1ccc1e9.png)


After answering some questions we get the flag as output!

![Untitled 2](https://user-images.githubusercontent.com/88723154/227419564-a1fa83c5-1c31-45b0-af53-7689d5571751.png)


### flag: HTB{3v3n_3xtr4t3rr3str14l_B31nGs_us3_Rcl0n3_n0w4d4ys}
