# **Instalação do Docker e Docker Compose no Debian e derivados**

>> **Última atualização: 05 de junho de 2023**

Este guia fornece instruções passo a passo para instalar o Docker e o Docker Compose no Debian e derivados.

## **Instalação do Docker no Debian**

1. Atualize o sistema operacional:
```bash
sudo apt update
sudo apt upgrade
```

2. Remova versões antigas do Docker (se existirem):
```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

3. Adicione o repositório oficial do Docker GPG:
```bash
sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/docker-archive-keyring.gpg >/dev/null
```

4. Adicione o repositório do Docker:
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian/ $(lsb_release -cs) stable"
```

5. Atualize novamente o sistema operacional:
```bash
sudo apt update
```

6. Instale o Docker:
```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

7. Verifique se o Docker foi instalado corretamente executando o comando:
```bash
sudo docker run hello-world
```
Você verá uma mensagem indicando que o Docker foi instalado corretamente se tudo estiver configurado corretamente.

## **Instalação do Docker Compose no Debian**

1. Certifique-se de ter o `curl` instalado no seu sistema. Caso não tenha, você pode instalá-lo executando o seguinte comando:
```bash
sudo apt update
sudo apt install curl
```

2. Baixe a versão mais recente do Docker Compose:
```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

3. Dê permissão de execução ao binário do Docker Compose:
```bash
sudo chmod +x /usr/local/bin/docker-compose
```

4. Verifique se a instalação foi bem-sucedida executando o comando:
```bash
docker-compose --version
```
ou
```bash
docker compose version
```

<br>

Você verá a versão mais recente do Docker Compose instalada sendo exibida.

Agora você tem o Docker e a versão mais atualizada do Docker Compose instalados no seu sistema Debian. Certifique-se de substituir "docker-compose" por "docker compose" ao executar comandos relacionados ao Docker Compose.

Lembre-se de que o método de gerenciamento de chave `apt-key` está obsoleto e foi substituído pelo novo método usando o diretório `trusted.gpg.d`. As instruções foram atualizadas para refletir essa alteração.
