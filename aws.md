# AWS

Date: August 16, 2022 1:31 PM

1 - Vamos criar uma conta na AmazonAws para subir a aplicação:

> [https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation&language=pt_br#/start/email](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation&language=pt_br#/start/email)
> 

2 - Após criar a conta procure o serviço **Lightsail**

> [https://lightsail.aws.amazon.com/ls/webapp/home/instances](https://lightsail.aws.amazon.com/ls/webapp/home/instances)
> 

3 - Crie uma nova instância

![https://user-images.githubusercontent.com/49401569/184731202-325a9263-1854-4f89-990f-c9badf7c0e4b.png](https://user-images.githubusercontent.com/49401569/184731202-325a9263-1854-4f89-990f-c9badf7c0e4b.png)

4 - Escolha o sistema operacional que será instalado. De preferência LINUX.
OBS: Por ser um sistema relativamente novo só tem servidor no EUA porém mesmo estando lá a velocidade é muito boa.

![https://user-images.githubusercontent.com/49401569/184731565-dadfe7f4-6b8d-46d7-94d4-d069fcc7000f.png](https://user-images.githubusercontent.com/49401569/184731565-dadfe7f4-6b8d-46d7-94d4-d069fcc7000f.png)

5 - O Lightsail nos dá várias facilidades na hora de escolher como o sistema irá se comportar, veja que ele nos da várias opções de SO com aplicações pré instaladas
<br>

![https://user-images.githubusercontent.com/49401569/184732131-8e714160-e6c2-43af-b995-7a015e62c5a6.png](https://user-images.githubusercontent.com/49401569/184732131-8e714160-e6c2-43af-b995-7a015e62c5a6.png)

Porém para nossa aplicação usaremos o docker, então precisaremos apenas do SO. Escolha a opção de Somente SO e o sistema Ubuntu 20.04 LTS<br>

![https://user-images.githubusercontent.com/49401569/184731933-0bddef6c-ae42-4e4a-8fcc-c7665cc2b547.png](https://user-images.githubusercontent.com/49401569/184731933-0bddef6c-ae42-4e4a-8fcc-c7665cc2b547.png)

Para nossa aplicação usaremos o plano de 2gb, que já é mais que o suficiente para rodar várias aplicações.

![https://user-images.githubusercontent.com/49401569/184732442-61e9bfd8-cdca-43d3-88c3-0d83f72928ac.png](https://user-images.githubusercontent.com/49401569/184732442-61e9bfd8-cdca-43d3-88c3-0d83f72928ac.png)

Aqui vamos nomear nossa máquina virtual, porém podemos deixar o nome padrão, agora só clicar em Criar Instância

![https://user-images.githubusercontent.com/49401569/184732630-596b33bb-cb5d-42ca-9b7f-00104c591b38.png](https://user-images.githubusercontent.com/49401569/184732630-596b33bb-cb5d-42ca-9b7f-00104c591b38.png)

Agora só clicar na máquina que foi escolhida

![https://user-images.githubusercontent.com/49401569/184732729-6977365a-f15a-4c96-b36c-429e16133c09.png](https://user-images.githubusercontent.com/49401569/184732729-6977365a-f15a-4c96-b36c-429e16133c09.png)

Temos algumas informações importantes nesta tela:
Primeiro aqui conseguimos ver o ip público que é por onde será acessado da internet

![https://user-images.githubusercontent.com/49401569/184733023-ac10c3b0-4de2-4314-b032-3f8503010865.png](https://user-images.githubusercontent.com/49401569/184733023-ac10c3b0-4de2-4314-b032-3f8503010865.png)

Em métricas conseguimos ver o tráfego da rede, acesso e picos

![https://user-images.githubusercontent.com/49401569/184733742-a6f9b518-cd91-49b0-9e3c-2ed2e63f9814.png](https://user-images.githubusercontent.com/49401569/184733742-a6f9b518-cd91-49b0-9e3c-2ed2e63f9814.png)

Em redes verificamos as portas liberadas de acesso. OBS: NÃO LIBERE A PORTA DO SEU BANCO DE DADOS

![https://user-images.githubusercontent.com/49401569/184733929-41d0f5e1-a91d-49f3-a1cd-9c682b8ca74f.png](https://user-images.githubusercontent.com/49401569/184733929-41d0f5e1-a91d-49f3-a1cd-9c682b8ca74f.png)

Adidione a porta 443Em SnapShot é onde pode ser configurados backups

![https://user-images.githubusercontent.com/49401569/184734073-85ad9fee-57f0-4c0a-82ec-a870c17c58dc.png](https://user-images.githubusercontent.com/49401569/184734073-85ad9fee-57f0-4c0a-82ec-a870c17c58dc.png)

Agora vamos acessar nossa máquina virtual, primeiro baixe sua chave da amazon:

![https://user-images.githubusercontent.com/49401569/184734167-faf6c38a-5f09-4e98-a515-b5359a23e00e.png](https://user-images.githubusercontent.com/49401569/184734167-faf6c38a-5f09-4e98-a515-b5359a23e00e.png)

Agora abra seu terminal e acesse a pasta onde está a chave (provavelmente em Downloads)
para acessar a sua máquina use o seguinte comando
**ssh** *{NOME_DA_MAQUINA}***@***{SEU_IP_PUBLICO}* **-i** *{CHAVE}*

![https://user-images.githubusercontent.com/49401569/184734574-ac1df896-77a9-405c-8506-5f08b6226567.png](https://user-images.githubusercontent.com/49401569/184734574-ac1df896-77a9-405c-8506-5f08b6226567.png)

Confirme com **yes**
Você verá uma tela parecida com essa:

![https://user-images.githubusercontent.com/49401569/184734851-41ab6a4b-39ae-440b-a85b-bec199057f08.png](https://user-images.githubusercontent.com/49401569/184734851-41ab6a4b-39ae-440b-a85b-bec199057f08.png)

Próximo passo será instalar o docker em nossa máquina.
Aqui reproduziremos os comandos, mas saiba que eles poderão ficar desatualizados. A documentação oficial é sempre a melhor fonte. [Documentação Oficial](https://docs.docker.com/engine/install/ubuntu/)

Execute os comandos abaixo exatamente na mesma ordem (apenas para Ubuntu e alguns derivados do Debian):

1 - Desistale possíveis instalações antigas do Docker:

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

2 - Atualize as listas do apt: 

```bash
  sudo apt-get update
```

3 - Adicione os certificados e dependências para instalação do Docker:

```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

4 - Adicione a chave oficial do Docker:

```bash
sudo mkdir -p /etc/apt/keyrings
```

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

5 - Adicione a lista de instalação do Docker:

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

6 - Atualize novamente as listas do apt:
 
 ```bash
 sudo apt-get update
 ```
 
 7 - Instale de fato o Docker: 
 
 ```bash
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
 ```
 
8 - Valide a instalação do Docker, rodar o seguinte comando para certificar-se que não ocorreu erro:

```bash
 sudo docker run hello-world
```

A mensagem esperada deve ser similar ao exemplo a seguir:

```bash
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 ```


# Instalação do Docker-Flex

É indicado a criaçao de uma pasta padrão chamada `document_root`

1 - Clonar o projeto dentro da pasta padrão `document_root`:

```bash
git clone https://github.com/flexpeak/docker-flex.git
```
Exemplo: 
![image](https://user-images.githubusercontent.com/74742097/185010924-3bf8389c-34b9-48d7-a3ce-be0a6ce11bea.png)

2 - Entre na pasta do projeto e copiar o arquivo `.env-example` para um novo arquivo chamado `.env`.

```bash
cp .env.example .env
```

agora vamos ver o conteúdo do arquivo .env e caso necessário alterá-lo
```bash
nano .env
```
![image](https://user-images.githubusercontent.com/49401569/185249602-ca351d79-a82a-4f0d-8543-66d201117a6c.png)


3 - Faça o build dos containers do Caddy, node, workspace e mysql (o comando up também fará o build na primeira vez - este comando poderá demorar horas, dependendo da configuração da máquina):

```bash
sudo docker compose build node caddy workspace mysql
```
![image](https://user-images.githubusercontent.com/74742097/185012415-47e9fc4e-f167-43cf-a0c4-22e27dc8f2ee.png)

4 - Faça o up  dos containers node caddy workspace mysql (o comando up também fará o build na primeira vez - este comando poderá demorar horas, dependendo da configuração da máquina):

```bash
sudo docker compose up -d node caddy workspace mysql
```
![image](https://user-images.githubusercontent.com/74742097/185012556-b10b1529-42e4-447d-a8e3-31b1cd903793.png)

Agora vamos verificar os se os containers estão ok
```bash
sudo docker compose ps
```
![image](https://user-images.githubusercontent.com/49401569/185250721-66f7fc17-c81f-45e4-81b0-b1977c9dbdc5.png)

Note que o container do node está com o status de Restarting, isso porque ainda não configuramos o PM2 para enxergar a configuração do nosso projeto backend.
Podemos ver o erro com o comando
```bash
sudo docker logs -f flex-node
```
![image](https://user-images.githubusercontent.com/49401569/185251359-8419746a-891c-4d3f-8944-a511d34babad.png)

# Configurando aplicação BackEnd

Para a aplicação BackEnd, segue as consigurações: 

1 - Na pasta `document_root` fazer o clone dos projetos BackEnd e FrontEnd: 
 - BackEnd
```bash
git clone https://github.com/flexpeak/agenda.git
```

- FrontEnd
```bash
https://github.com/flexpeak/agenda-front.git
```

2 - Agora, é necessário fazer a cópia do arquivo `.env-example` que contém no projeto e renomear para `.env`;

- Entrar na pasta do projeto `agenda` e utilize o seguinte comando para copiar  `.env-example` e criar o arquivo `.env`, lembrando que o arquivo `.env` está definido no arquivo `.gitignore` portanto toda vez que for buildar o projeto é preciso criar manualmente o arquivo `.env`: 

```bash
cp .env-example .env
```

3 - Agora é preciso instalar todas as dependências do projeto em **`node`**, premeiro é preciso estar na pasta do `docker-flex` e entrar no container do workspace com o sguinte comando: 

```bash
sudo docker compose exec --user=flexdock workspace
```

4 - Entrar na pasta do projeto backend `agenda` e rodar o comando: 
```bash
npm install
```

5 - Configurar o backend dentro do projeto docker-flex, entrar editar o arquivo `ecosystem.config.js` dentro da pasta node, para editar o arquivo via terminal rodar o comando: 
```bash
nano ecosystem.config.js
```
![image](https://user-images.githubusercontent.com/74742097/185274030-001a2c4b-38d2-45f2-a9ef-add9970218ed.png)

Em seguida editar o arquivo: 
![image](https://user-images.githubusercontent.com/74742097/185274272-777811ab-e50c-44ac-9086-c761896bd531.png)


- Após essa configuração é preciso restartar o docker novamente com o comando: 
```bash
sudo docker compose restart
```

7 - Após realizar a configuração e restartar o docker, rodar o camdo para verificar se a aplicação em node foi configurada com sucesso: 
```bash
sudo docker compose ps
```
![image](https://user-images.githubusercontent.com/74742097/185274753-54a5717c-cdb8-4aec-86cb-f0e05363d159.png)

# Configurando aplicação FrontEnd

1 - Na pasta **`document_root`** fazer o clone dos projetos BackEnd:
```bash
git clone https://github.com/flexpeak/agenda-front.git
```
2 - Agora, é necessário fazer a cópia do arquivo `.env-example` que contém no projeto e renomear para `.env`;
•	Entrar na pasta do projeto **agenda-front** e utilize o seguinte comando para copiar `.env-example` e criar o arquivo `.env`, lembrando que o arquivo `.env` está definido no arquivo `.gitignore` portanto toda vez que for buildar o projeto é preciso criar manualmente o arquivo `.env`:
```bash
cp .env-example .env
```
3 - Agora é preciso instalar todas as dependências do projeto frontend em **react**, primeiro é preciso estar na pasta do `docker-flex` e entrar no container do workspace com o seguinte comando:
```bash
sudo docker compose exec --user=flexdock workspace
```
4 - Entrar na pasta do projeto backend **agenda-front** e rodar o comando:
```bash
npm install
```
5 - Agora é necessário retirar o projeto frontend do ambiente de desenvolvimento e transformar em ambiente de produção, para isso entrar no container do workspace e rodar o comando na pasta do projeto react
```bash
npm run build
```

Com os projetos todos configurados e buildados, vamos configurar o [Caddy]([https://docs.docker.com/engine/install/ubuntu/](https://caddyserver.com/)), ele será responsável por dar acesso aos nossos projetos utilizando protocolo HTTPS 
Vamos acessar o arquivo de configuração dele que estará em ~/document_root/docker-flex/caddy/caddy
```bash
sudo nano Caddyfile
```
![image](https://user-images.githubusercontent.com/49401569/185714660-63d8531b-9d02-47da-adef-8def8c9ff31b.png)

vamos configurar nosso servidor node
```bash
https://api.gabrielomena.com.br {
    reverse_proxy node:8080
}
```
a porta é a mesma que configuramos em nosso projeto node
Agora vamos configurar o nosso projeto em React

```bash
https://gabrielomena.com.br {
    root * /var/www/agenda-front/build
    try_files {path} /index.html
    file_server
}
```
**Lembre-se que após editar as configurações, você deve restartar o docker***
****Lembre-se de configurar no .env do front o mesmo endereço que está na configuração do node no Caddy, neste exemplo: https://api.gabrielomena.com.br****

Após finalizar as configurações do nosso servidor vamos configurar nosso domínio para redirecionar para ele.
Nesse exemplo usaremos o [Registro.br](https://registro.br)
Após adquirir um domínio vamos descer a página até a área de DNS
![image](https://user-images.githubusercontent.com/49401569/185716994-e81a172f-4cc6-4c19-8215-ef53675ca6fd.png)
Aqui vamos informar para onde nosso domínio irá ser direcionado
![image](https://user-images.githubusercontent.com/49401569/185717031-9f26b387-0a30-4063-84e1-b7ff9fe7c99e.png)

Após realizar as configurações temos que esperar o DNS se propagar e assim poderemos acessar nosso sistema já em produção.
Para verificar você pode acessar o site [whatsmydns](https://www.whatsmydns.net/)

![image](https://user-images.githubusercontent.com/49401569/185717379-5ccd72c6-a933-40d8-8105-7260e8da39b9.png)
![image](https://user-images.githubusercontent.com/49401569/185717396-7bb6cc38-686b-4fcc-b7f9-8697dd83b684.png)





