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
Você pode está olhando a configuração completa do docker em: [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)

Rode o seguintes comando:

```bash
sudo apt install ca-certificates curl gnupg lsb-release
```

```bash
sudo mkdir -p /etc/apt/keyrings
```

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
