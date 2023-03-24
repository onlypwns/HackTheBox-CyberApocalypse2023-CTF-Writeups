# forensics - Plaintext Treasure

We are given a pcap file so lets look for some flags in i assume plaintext

filter as 

`tcp contains HTB`

Follow the HTTP stream boom, we have a flag:

![Untitled](forensics%20-%20Plaintext%20Treasure%20747bffb956ac49cb9f25a2e2816e1075/Untitled.png)

### flag: HTB{th3s3_4l13ns_st1ll_us3_HTTP}