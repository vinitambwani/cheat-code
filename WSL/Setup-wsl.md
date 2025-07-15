# Steps to install docker in WSL:

1. Open your WSL2 terminal (e.g., Ubuntu) 
2. Update the package lists: ```sudo apt update``` 
3. Install dependencies: ```sudo apt install -y apt-transport-https ca-certificates curl software-properties-common``` 
4. Add the Docker GPG key: ```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg``` 
5. Add the Docker repository: ```echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null``` 
6. Update package lists again: ```sudo apt update``` 
7. Install Docker: ```sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin``` 
8. Add your user to the docker group: ```sudo usermod -aG docker $USER``` 
9. Log out and back in (or restart WSL) for group changes to take effect 

# Steps to install kubectl in WSL:

1. Download kubectl:


```$> curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"```

2. Make is executable and move it:

```$> chmod +x ./kubectl```

```$> sudo mv ./kubectl /usr/local/bin/kubectl```

3. Verify installation:

```$> kubectl version --client```

# Steps to install minikube:

1. Download the Minkube binary:

```$> curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64```

2. Install Minkube:

```$> sudo install minikube-linux-amd64 /usr/local/bin/minikube```

3. Configure Minikube to use Docker

```$> minikube config set driver docker```

4. To start minikube

```$> minikube start```