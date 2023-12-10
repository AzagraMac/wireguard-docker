<p align="center">
  <img src="https://github.com/AzagraMac/WireGuardDocker/assets/571796/6afa40ef-e5de-4c8c-ae92-1608bf2ee8eb" width="450" title="logo">
</p>

### Requeriments
- Service docker running
- Open port 51820 UDP on the router

### Install Docker
    sudo update && sudo apt upgrade -y
    sudo apt install git vim wget curl net-tools ca-certificates gnupg
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    echo  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
	"$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt update
    sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
    sudo usermod -aG docker $USER
    sudo apt install docker-compose-plugin -y

### Test Docker
    $ docker version
    Client: Docker Engine - Community
     Version:           24.0.2
     API version:       1.43
     Go version:        go1.20.4
     Git commit:        cb74dfc
     Built:             Thu May 25 21:52:41 2023
     OS/Arch:           linux/arm64
     Context:           default

    $ docker compose version
    Docker Compose version v2.18.1

### Clone repo
    https://github.com/AzagraMac/WireGuardDocker.git

### Running
    docker compose up -d

### Check
    docker ps -a

### Show QR config client 1, change number for show config client 2, 3... 
    docker exec -it wireguard /app/show-peer 1

### Monitor traffic from a connected client
    docker exec -it wireguard wg show

### Download App
<a href="https://play.google.com/store/apps/details?id=com.wireguard.android"><img src="https://lh3.googleusercontent.com/q1k2l5CwMV31JdDXcpN4Ey7O43PxnjAuZBTmcHEwQxVuv_2wCE2gAAQMWxwNUC2FYEOnYgFPOpw6kmHJWuEGeIBLTj9CuxcOEeU8UXyzWJq4NJM3lg=s0" width="130px"></a>  <a href="https://apps.apple.com/es/app/wireguard/id1441195209"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Download_on_the_App_Store_Badge.svg/640px-Download_on_the_App_Store_Badge.svg.png" width="130px"></a>
