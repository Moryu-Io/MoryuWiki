

```
    sudo apt update
    sudo apt install ca-certificates curl gnupg

    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc

    # Add the repository to Apt sources:
    echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
      $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
      sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt update

    sudo groupadd docker
    sudo usermod -aG docker <ユーザー名>
```

```
    sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


## Permission denied
```
Got permission denied while trying to connect to the Docker daemon socket at
```
が発生した場合は権限付与
```
sudo chmod 666 /var/run/docker.sock
```