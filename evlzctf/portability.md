# Portability - 25

>My beautiful API is finally ready! Uses Flask, Virtual Environments, and loads the config from Environment Variables!

Decompressing the file `portability.zip` we get a typical virtualenv. As we know by the challenge description, the flag is in the environment variables.

Searching in the activation file `\portability\handout\env\bin\activate` we found:

```
# export $(echo RkxBRwo= | base64 -d)=ZXZsenthbHdheXNfaWdub3JlX3RoZV91bm5lY2Nlc3Nhcnl9Y3RmCg==
```

The decoded string is the flag:

`evlz{always_ignore_the_unneccessary}ctf
`
