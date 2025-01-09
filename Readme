# Roteiro para o Vídeo
# 1. Introdução (30-60 segundos)
Apresente o vídeo e explique o objetivo.
Exemplo:
"Olá, pessoal! Hoje vou ensinar vocês a instalar o Alfresco Community, uma poderosa ferramenta de gestão de documentos, no Linux. Vamos configurar tudo do zero, incluindo dependências, banco de dados e o próprio Alfresco. Vamos nessa!"

2. Preparativos (1-2 minutos)
- Mostre o ambiente de trabalho, como o terminal Linux (Ubuntu, Debian, ou CentOS).
- Liste os pré-requisitos:
-- Máquina com Linux (mínimo 4GB RAM, 40GB disco).
-- Acesso root ou sudo.
-- Conexão com a internet.
-- Explique o software usado para gravação, como VirtualBox, VMware ou Proxmox, se estiver em uma VM.
Comandos mostrados:
```
bash
Copiar código
sudo apt update && sudo apt upgrade -y
```
3. Instalação das Dependências (2-3 minutos)
Explique por que instalar as dependências, como Java e PostgreSQL.
Mostre os comandos:
bash
Copiar código
sudo apt install -y openjdk-11-jdk wget unzip postgresql libfontconfig1
Confirme a instalação do Java:
bash
Copiar código
java -version
4. Baixar o Instalador do Alfresco (2 minutos)
Acesse o site oficial do Alfresco e mostre como baixar o instalador.
Alternativamente, explique o comando wget:
bash
Copiar código
wget https://download.alfresco.com/release/community/7.4/alfresco-content-services-community-7.4-installer-linux-x64.bin
chmod +x alfresco-content-services-community-7.4-installer-linux-x64.bin
Destaque que você está preparando o instalador para execução.
5. Configurar o Banco de Dados PostgreSQL (3-4 minutos)
Explique que o Alfresco precisa de um banco de dados.
Mostre os comandos para criar o banco e o usuário:
bash
Copiar código
sudo -u postgres psql
CREATE DATABASE alfresco;
CREATE USER alfresco WITH PASSWORD 'alfresco';
GRANT ALL PRIVILEGES ON DATABASE alfresco TO alfresco;
\q
Enfatize a importância de substituir a senha padrão.
6. Executar o Instalador do Alfresco (5-6 minutos)
Execute o instalador no terminal. Mostre como executar em modo gráfico ou silencioso:
bash
Copiar código
sudo ./alfresco-content-services-community-7.4-installer-linux-x64.bin
Passe pelas telas de configuração (idioma, diretório de instalação, etc.).
Mostre que o Alfresco será instalado no diretório /opt/alfresco.
7. Ajustar Permissões e Iniciar o Serviço (2-3 minutos)
Explique que o Alfresco precisa de permissões corretas.
Mostre os comandos:
bash
Copiar código
sudo chown -R alfresco:alfresco /opt/alfresco
cd /opt/alfresco
sudo -u alfresco ./alfresco.sh start
Mostre o comando para verificar o status do serviço.
8. Testar a Instalação (2-3 minutos)
Abra o navegador e acesse o Alfresco na URL http://<seu_ip>:8080/share.
Mostre como fazer login com o usuário padrão (admin/admin).
9. Dicas Finais e Configurações Adicionais (1-2 minutos)
Recomende alterar a senha padrão e configurar o firewall:
bash
Copiar código
sudo ufw allow 8080
sudo ufw enable
Sugira consultar a documentação oficial para configurações avançadas, como SSL ou clusters.
10. Encerramento (30-60 segundos)
Conclua o vídeo agradecendo os espectadores e incentivando comentários.
Exemplo:
"Pronto! Agora você tem o Alfresco Community rodando no Linux. Se você gostou do vídeo, deixe seu like e se inscreva no canal. Até a próxima!"
