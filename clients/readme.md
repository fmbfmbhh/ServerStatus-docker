```
apt-get update \
  &&  apt-get install python-dev  \
     build-essential libssl-dev libffi-dev \
     libxml2-dev libxslt1-dev zlib1g-dev \
     python-pip gawk vnstat \
  && apt-get install -y python python-pip gawk vnstat \
  && pip install psutil \
  && wget https://github.com/drice82/ServerStatus-docker/raw/master/clients/client-psutil.py \
  && nano client-psutil.py
```
###自启动
systemctl start rc-local <br />
chmod +x rc.local <br />
rc.local <br />
```
#!/bin/sh -e
nohup python /root/client-psutil.py &> /dev/null &
exit 0
```
