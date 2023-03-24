# forensics - Plaintext Treasure

We are given a pcap file so lets look for some flags in i assume plaintext

filter as 

`tcp contains HTB`

Follow the HTTP stream boom, we have a flag:

![Untitled](https://user-images.githubusercontent.com/88723154/227419609-40ab414c-af81-4990-b63f-6d9bf9b17c2c.png)


### flag: HTB{th3s3_4l13ns_st1ll_us3_HTTP}
