# web - Didactic Octo Paddles

We are presented with a login page

![Untitled](https://user-images.githubusercontent.com/88723154/227418621-8b24d1ae-5424-45f7-9128-116a9d5f7da3.png)


we can register a user and see where does that take us

we visit the /register directory

Ok, now with the registered user we can see what is going on the server

There is a JWT lets see if we can manipulate that and access the /admin panel that is restricted 

![Untitled 1](https://user-images.githubusercontent.com/88723154/227418686-d8c63a5f-e463-473c-ad97-513a50d913d0.png)


### From burp i loaded an extension that gets us to work with attacking JWT , we send a GET request to the /admin directory and modify the JWT with the none algorithm attack, and setting the id to 1

![Untitled 2](https://user-images.githubusercontent.com/88723154/227418703-28c0b6a3-6b81-4aa9-b956-6c1151f49b50.png)


### Sending the request give us access to the admin dashboard

![Untitled 3](https://user-images.githubusercontent.com/88723154/227418733-c67356c4-1775-4271-b99d-3578f8cf1ebf.png)


Not much to see from the admin dashboard so lets see if we can find another way to get access to the flag

![Untitled 4](https://user-images.githubusercontent.com/88723154/227418772-4eee19f0-68fe-4197-9db1-2747a9cfc933.png)


Going back to reviewing the files for the challenge we notice an interesting thing, as from below the username is being rendered with a js template, looks like SSTI so let’s try to craft a payload and see if it can work!


![Untitled 5](https://user-images.githubusercontent.com/88723154/227418795-23df5bc1-685e-4b36-a40a-aeefc8ce8aca.png)

Found this one from HackTricks let’s see if it can work when we register a new user!

Looks like our command got through successfully!

### Payload used:

```powershell
"{{:\"pwnd\".toString.constructor.call({},\"return global.process.mainModule.constructor._load('child_process').execSync('cat /etc/passwd').toString()\") ()}}"
```

![Untitled 6](https://user-images.githubusercontent.com/88723154/227418819-800f40b4-342c-481f-bcc2-a356e4c559c5.png)


If we call back to the /admin we get the content of the /flag.txt in the response
