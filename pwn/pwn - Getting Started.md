# pwn - Getting Started

So we get to overflow the first 32 bytes implementing what we have learned in the previous challenges

![Untitled](https://user-images.githubusercontent.com/88723154/227420230-4e8c57fb-89c5-4406-bafb-bd7565dfeedf.png)


So lets’ give it a go

We use the command from before to create a payload and overflow the requested buffer

`printf 'A%.0s' {1..48}`

We send the request and we get the flag back

![Untitled 1](https://user-images.githubusercontent.com/88723154/227420240-41413fbe-fb5c-4d12-a642-805b21e87657.png)


### flag: HTB{b0f_s33m5_3z_r1ght?}
