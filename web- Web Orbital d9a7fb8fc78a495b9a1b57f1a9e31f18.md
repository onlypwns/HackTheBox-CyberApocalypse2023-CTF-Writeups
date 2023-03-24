# web- Web Orbital

used sqlmap to get a sql injection attack, which found us a password for the site:

![Untitled](web-%20Web%20Orbital%20d9a7fb8fc78a495b9a1b57f1a9e31f18/Untitled.png)

login as 

## admin: ichliebedich

## 1692b753c031f2905b89e7258dbc49bb

send POST request to /api/export

}

“name”: “../etc/passwd”

}

![Untitled](web-%20Web%20Orbital%20d9a7fb8fc78a495b9a1b57f1a9e31f18/Untitled%201.png)

Directory traversal!

From the docker file noticed that the flag was called differently than the usual flag.txt

### flag: HTB{T1m3_b4$3d_$ql1_4r3_fun!!!}