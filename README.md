# docker_lesson
```markdown
# Docker Setup Guide for Ubuntu 20.04 LTS  
By **Oyebola**  

Welcome to my Docker setup journey! This guide covers the step-by-step installation and configuration of Docker on Ubuntu 20.04 LTS.

---

## 🚀 Initial Setup  
Ensure your package list is up to date and install the necessary packages:

```bash
sudo apt-get update  
sudo apt-get install ca-certificates curl gnupg
```

## 🔐 Setting Up Keyrings  
Create a directory for storing keyring files and download the Docker GPG key:

```bash
sudo install -m 0755 -d /etc/apt/keyrings  
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg  
sudo chmod a+r /etc/apt/keyrings/docker.gpg  
```

## 🏗 Adding Docker Repository  
Configure the APT repository for Docker:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null  
```

Update package lists again:

```bash
sudo apt-get update  
```

## 📦 Installing Docker  
Install Docker and essential plugins:

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin  
```

## ✅ Verifying Installation  
Run the `"Hello World"` container to ensure Docker is working:

```bash
sudo docker run hello-world
![image](https://github.com/user-attachments/assets/65c200c4-f609-4ad1-9152-0340e96c308e)

```

### Expected Output:
- Docker pulls the `hello-world` image.
- Runs a container that displays a greeting message.
- Confirms that installation is successful!

## 👤 Managing Docker Permissions  
Add your user (`azureuser`) to the Docker group:

```bash
sudo usermod -aG docker azureuser  
newgrp - docker  
```

If you encounter permission issues, try:

```bash
sudo chown $USER /var/run/docker.sock  
```

## 🛠 Essential Docker Commands  

| Command | Description |
|---------|------------|
| `docker images` | Show available images |
| `![image](https://github.com/user-attachments/assets/086990a2-904b-440c-8488-13b5c65e4e86)` |

| `docker ps` | List running containers |
| `docker ps -a` | List all containers (running and stopped) |
| `![image](https://github.com/user-attachments/assets/3d79e098-fa31-41d8-a1f4-9f65cc3b11df)` |

| `docker stop <container_ID>` | Stop a container |
| `docker pull <image>` | Download an image |
| `docker push <image>` | Upload an image to Docker Hub |
| `docker rmi <image_id>` | Remove an image from local system |





