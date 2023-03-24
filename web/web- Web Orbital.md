# web- Web Orbital

used sqlmap to get a sql injection attack, which found us a password for the site:

And we can login as 

## admin: ichliebedich

What we see is that there is no flag, so I start looking around. I notice an endpoint from the source code and try to send a request to /api/export with a directory traversal inside the name parameter as seen in the shared files for the challenge

send POST request to /api/export

}
“name”: “../etc/passwd”
}

![Untitled](https://user-images.githubusercontent.com/88723154/227417421-e6f551a6-fe97-4af5-aa86-7069f7373383.png)


Directory traversal inside of the name parameter, nice!

![Untitled 1](https://user-images.githubusercontent.com/88723154/227417525-ccbc45b4-52c1-4687-b838-0f4067091973.png)


From the docker file I have also noticed that the flag was called differently than the usual flag.txt

### flag: HTB{T1m3_b4$3d_$ql1_4r3_fun!!!}
