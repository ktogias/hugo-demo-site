# Hugo Demo Site

This is an experimental site built with hugo (https://gohugo.io) just for my learning of Hugo

## Installation for Fedora 33

On fedora 33 I run

```
sudo dnf install hugo
```

Then followed the instructions in https://gohugo.io/getting-started/quick-start/

### Increase inotify max user watchers

In case the web page is not automaticaly updated when running the Hugo server (hugo server -D) 
this is because the default value for inotify max user watchers is too low (this was my case). 

To increase max user watchers you will have to create a conf file in /etc/sysctl.d/ and then reload system configuration:

```
echo fs.inotify.max_user_watches=524288 | sudo tee /etc/sysctl.d/40-inotify-max-user-watches.conf && sudo sysctl --system
```

You can check the current setting with

```
cat /proc/sys/fs/inotify/max_user_watches
```

That's all folks for now!

