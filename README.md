# devops
wget https://releases.hashicorp.com/terraform/1.8.0/terraform_1.8.0_linux_amd64.zip
unzip terraform_1.8.0_linux_amd64.zip
sudo mv terraform /usr/local/bin/

echo Building Docker Image...

docker rm --force container1

docker build -t nginx-image1 .

docker run -d -p 8081:80 --name=container1 nginx-image1

echo ✅ Docker Container Deployed Successfully on http://localhost:8081
