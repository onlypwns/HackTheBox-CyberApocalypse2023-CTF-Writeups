# pwn - Getting Started

So we get to overflow the first 32 bytes implementing what we have learned in the previous challenges

![Untitled](pwn%20-%20Getting%20Started%20af23091ea3904779b5b866c1e7eb84a8/Untitled.png)

So lets’ give it a go

We use the command from before to create a payload and overflow the requested buffer

`printf 'A%.0s' {1..48}`

We send the request and we get the flag back

![Untitled](pwn%20-%20Getting%20Started%20af23091ea3904779b5b866c1e7eb84a8/Untitled%201.png)

### flag: HTB{b0f_s33m5_3z_r1ght?}