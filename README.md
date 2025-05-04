# ldesk

a better version of https://codeberg.org/Mollomm1/W10-On-Github-Codespaces

> ⚠️ Use With Caution⚠️

> it also works on [gitpot](https://gitpod.io/workspaces)

# Supported Stuff

* 1080p 60fps

* Sound

* Windows apps (wine)

* Browsering (Brave and Firefox included!)

* Home Persistance (You keep your files!)

# Use

it's very simple to install.

clone the repo
```
git clone https://github.com/M4rc311n3/ldesk.git
cd ldesk
```


build the container (take long 5-10 minutes)
```
docker build -t ldesk .
```

then go back to your home directory
```
cd ..
```

initialise the default Persistance directory
```
mkdir Save
cp -r ldesk/root/config/* Save
```

and after you can do 
```
docker run --name=ldesk -e PUID=1000 -e PGID=1000 --security-opt seccomp=unconfined -e TZ=Etc/UTC -e SUBFOLDER=/ -e TITLE=ldesk -p 3000:3000 --shm-size="2gb" -v $(pwd)/Save:/config --restart unless-stopped ldesk
```

now, everytime you come back to your codespace webtop should start automaticaly
