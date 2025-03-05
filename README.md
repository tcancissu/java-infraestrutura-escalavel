# Arquitetura Java - Infraestrutura Escalável

Criando uma infraestrutura escalável para uma API REST em Java com Spring Framework.
- Utilizando os serviços EC2 e VPC da AWS para subir uma instância Linux padrão. 
- Configurando a infraestrutura do ambiente com Docker.
- Utilizando NGinx como proxy reverso.
- Implementando customizações de banco de dados.
- Utilizando Redis para cache em algumas consultas.


### Comandos para atualizar o ambiente AWS

Compilar o pacote localmente: 
./mvnw package

Criar uma imagem da aplicação: 
docker build -t tcancissu/codechella:1.4 .

Publicar essa imagem no Docker Hub: 
docker push tcancissu/codechella:1.4

Copiar os arquivos para o servidor via SCP: 
scp -i key-rsa.pem -r docker-compose.yml nginx/ env/ ec2-user@IP_EC2:/home/ec2-user

Acessar o servidor via SSH: 
ssh -i key-pair.pem ec2-user@IP_EC2 >> 

Instalar e configurar o Docker e o Docker Compose:
sudo yum update -y && sudo yum install docker -y && sudo usermod -a -G docker ec2-user && sudo service docker start && newgrp docker && sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose

Inicializar o Docker Compose: 
docker-compose up -d