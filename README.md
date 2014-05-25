## syncomm's Dockerfiles ##

These are a collection of my dockerfiles. Most are X based for now,
as that is the area which is giving me the most interest. 

# X11 and Docker #
To forward X11 through docker efficiently, all you need to do is set
the DISPLAY environment to unix:(your host DISPLAY) and share the 
host filesystem socket (ex. /tmp/.X11-unix/X0). This can be done in
most cases with:

```
sudo docker run -rm _-v /tmp/.X11-unix/:/tmp/.X11-unix/_ -i -t fedora /bin/bash
```

Sound can also be forwarded this way through sharing `/dev/snd/`
