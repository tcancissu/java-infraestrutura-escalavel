
Arquitetura Java - Criando uma infraestrutura escalável. 


# Comandos Maven 

Compilar o pacote, rodando no terminal na pasta do projeto.
./mvnw package


# Comandos Docker

Criar uma imagem da aplicação
docker build -t tcancissu/codechella:1.0 .

Criar um container baseado nessa imagem
docker run tcancissu/codechella:1.0


# Comandos SSH

Copie os arquivos para o servidor via SCP
scp -i key-rsa.pem -r docker-compose.yml env/ ec2-user@IP_EC2:/home/ec2-user 

Acessar via SSH
ssh -i key-pair.pem ec2-user@IP_EC2 >> 

Instalar e configurar o Docker e o Docker Compose:
sudo yum update -y && sudo yum install docker -y && sudo usermod -a -G docker ec2-user && sudo service docker start && newgrp docker && sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose

Inicializar o Docker Compose
docker-compose up -d