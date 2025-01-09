# Roteiro para o Vídeo
## Script para instalar o Alfresco Community
```
#!/bin/bash

# Atualiza os pacotes e instala dependências
echo "Atualizando pacotes e instalando dependências..."
sudo apt update && sudo apt upgrade -y
sudo apt install -y openjdk-11-jdk wget unzip postgresql libfontconfig1

# Define variáveis
ALFRESCO_VERSION="7.4"
ALFRESCO_INSTALLER="alfresco-content-services-community-${ALFRESCO_VERSION}-installer-linux-x64.bin"
INSTALL_DIR="/opt/alfresco"

# Cria usuário alfresco
echo "Criando usuário alfresco..."
sudo useradd -r -m -d /opt/alfresco -s /bin/bash alfresco
sudo mkdir -p $INSTALL_DIR
sudo chown alfresco:alfresco $INSTALL_DIR

# Baixa o instalador do Alfresco
echo "Baixando o instalador do Alfresco..."
cd /tmp
wget "https://download.alfresco.com/release/community/${ALFRESCO_VERSION}/${ALFRESCO_INSTALLER}" -O $ALFRESCO_INSTALLER
chmod +x $ALFRESCO_INSTALLER

# Instalação do Alfresco
echo "Iniciando a instalação do Alfresco..."
sudo -u alfresco ./alfresco-content-services-community-${ALFRESCO_VERSION}-installer-linux-x64.bin --mode unattended --prefix $INSTALL_DIR

# Configuração do PostgreSQL
echo "Configurando o banco de dados PostgreSQL..."
sudo -u postgres psql -c "CREATE DATABASE alfresco;"
sudo -u postgres psql -c "CREATE USER alfresco WITH PASSWORD 'alfresco';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE alfresco TO alfresco;"

# Ajusta permissões
echo "Ajustando permissões..."
sudo chown -R alfresco:alfresco $INSTALL_DIR

# Inicia o serviço do Alfresco
echo "Iniciando o Alfresco..."
sudo -u alfresco bash -c "cd $INSTALL_DIR && ./alfresco.sh start"

# Finalização
echo "Instalação concluída. Acesse o Alfresco em http://localhost:8080/share"

```
# 1. Introdução (30-60 segundos)
Apresente o vídeo e explique o objetivo.
Exemplo:
"Olá, pessoal! Hoje vou ensinar vocês a instalar o Alfresco Community, uma poderosa ferramenta de gestão de documentos, no Linux. Vamos configurar tudo do zero, incluindo dependências, banco de dados e o próprio Alfresco. Vamos nessa!"

sudo apt update && sudo apt upgrade -y

sudo apt install -y openjdk-11-jdk wget unzip postgresql libfontconfig1

