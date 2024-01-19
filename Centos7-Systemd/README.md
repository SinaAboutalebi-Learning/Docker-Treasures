### Build Command
```BASH
docker build --rm -t centos7:systemd .
```

### Enable Systemctl Replacement Docker 
```Docker
ENV docker_systemctl_replacement="https://raw.githubusercontent.com/gdraheim/docker-systemctl-replacement/v1.4.4147/files/docker/systemctl.py"
RUN wget "${docker_systemctl_replacement}" --output-document=/usr/bin/systemctl
```
