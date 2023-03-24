# web - Didactic Octo Paddles

We are presented with a login page

![Untitled](https://user-images.githubusercontent.com/88723154/227416224-a10d253e-ebb6-4703-9380-9e0e3f1f34b9.png)


we can register a user and see where does that take us

we visit the /register directory

Ok, now with the registered user we can see what is going on the server

There is a JWT lets see if we can manipulate that and access the /admin panel that is restricted 

![Untitled 1](https://user-images.githubusercontent.com/88723154/227416299-cd86abd6-9496-4439-9e54-ea33e6523587.png)


### From burp i loaded an extension that gets us to work with attacking JWT , we send a GET request to the /admin directory and modify the JWT with the none algorithm attack, and setting the id to 1

![Untitled 2](https://user-images.githubusercontent.com/88723154/227416325-980a99e1-89e2-43de-a8e7-3a5b5adb7608.png)


### Sending the request give us access to the admin dashboard


![Untitled 3](https://user-images.githubusercontent.com/88723154/227416346-e56f9414-b234-4972-8cba-6162a7c8abec.png)

Not much to see from the admin dashboard so lets see if we can find another way to get access to the flag


![Untitled 4](https://user-images.githubusercontent.com/88723154/227416361-cce3167d-d3c7-4869-a42b-f95c320fe949.png)

Going back to reviewing the files for the challenge we notice an interesting thing, as from below the username is being rendered with a js template, looks like SSTI so let’s try to craft a payload and see if it can work!


![Untitled 5](https://user-images.githubusercontent.com/88723154/227416383-ba64bb60-c879-4b31-8f52-87379df788e8.png)

Found this one from HackTricks let’s see if it can work when we register a new user!

Looks like our command got through successfully!

### Payload used:

```powershell
"{{:\"pwnd\".toString.constructor.call({},\"return global.process.mainModule.constructor._load('child_process').execSync('cat /etc/passwd').toString()\") ()}}"
```

![Untitled 6](https://user-images.githubusercontent.com/88723154/227416407-3529c4bf-fd76-43d3-b190-11feb8a8eea0.png)


If we call back to the /admin we get the content of the /etc/passwd file in the response so the same method would give us the flag.
