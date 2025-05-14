---
title: "Instalando Docker"
date: 2025-05-14T00:42:53-03:00
draft: false
description: "Instação e configuração do Docker no Ubuntu/WSL"
tags: ["tutorial", "docker"]
categories: ["tutorial", "docker"]
---

---
Se você usa o WSL, provavelmente já precisou usar o Docker. A alternativa mais comum era o Docker Desktop, porém essa aplicação é pesada e pode travar até mesmo um notebook com processador Core i7 (experiência própria).

A melhor opção, portanto, é usar o Docker direto no terminal: é mais leve e prático. No entanto, você perde a interface gráfica do Docker Desktop, que ajuda bastante, mas que também deixa a máquina mais lenta.

A boa notícia é que você pode usar ferramentas como o dockerly ou lazydocker (eu ensino como instalar neste **[tutorial aqui](/posts/instalando-docker/)**), que oferecem interfaces gráficas no terminal, muito mais leves e práticas. Também há a opção de usar o Portainer.

Enfim, vamos ao tutorial!

---

### **1. Atualize o sistema**

```bash
sudo apt update
sudo apt upgrade -y
```

### **2. Instale dependências necessárias**

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

### **3. Adicione a chave GPG oficial do Docker**

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### **4. Adicione o repositório do Docker**

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### **5. Atualize o índice de pacotes novamente**

```bash
sudo apt update
```

### **6. Instale o Docker**
> <small>Finalmente 😅</small>
```bash
sudo apt install docker-ce -y
```

### **7. Verifique se o Docker está funcionando**

```bash
sudo systemctl status docker
```
> <small>Se aparecer “active (running)”, está tudo certo!</small>

### **8. (Opcional) Adicione seu usuário ao grupo docker**

Assim você pode rodar comandos Docker sem sudo:
```bash
sudo usermod -aG docker $USER
```
> Depois disso, faça logout e login novamente, ou rode `newgrp docker`.

---

Pronto, se ocorreu tudo certo até aqui, agora é só usar o docker. 