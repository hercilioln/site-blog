---
title: "Instalação e Configuração do Zsh"
date: 2025-04-09T00:49:08-03:00
draft: false
description: "Guia rápido de instalação do Zsh, configuração do Oh My Zsh e criação de aliases úteis."
tags: ["tutorial", "zsh"]
categories: ["tutorial"]
---


---

Sempre que utilizo o Linux, prefiro o terminal Zsh em vez do Bash. Acho ele mais prático, limpo e fácil de usar. Com o Zsh, ao dar o comando `cd` para navegar entre diretórios, você pode simplesmente usar a tecla **Tab** para autocompletar ou explorar pastas com muito mais agilidade.

---

### 🛠️ Pré-requisitos

Certifique-se de que o `git` está instalado, pois vamos precisar dele mais adiante. Se não estiver, basta rodar:

```bash
sudo apt install git
```

---

### ⚙️ Instalando o Zsh

Para instalar o Zsh, execute:

```bash
sudo apt install zsh
```

---

### 🚀 Instalando o Oh My Zsh

Agora, clone o repositório oficial do [Oh My Zsh](https://ohmyz.sh):

```bash
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

Com o repositório clonado, precisamos criar o arquivo `.zshrc`, que é onde ficarão as configurações do Zsh, como tema, plugins e aliases.

Crie o arquivo com:

```bash
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

---

### 🖥️ Tornando o Zsh o shell padrão

Altere o shell padrão para o Zsh:

```bash
chsh -s $(which zsh)
```

Se estiver usando o WSL, basta fechar o terminal e abrir novamente. Em outras distros, reinicie o sistema para aplicar a mudança.

---

### 🎨 Mudando o tema (opcional)

Se quiser mudar o tema do seu terminal, confira os disponíveis no [repositório oficial de temas](https://github.com/ohmyzsh/ohmyzsh/wiki/themes).

> Eu costumo usar o tema padrão mesmo, que já me atende bem.

---

### ✨ Criando Aliases

Para facilitar o uso do terminal no dia a dia, você pode criar aliases — que são atalhos para comandos maiores.

Abra o arquivo `.zshrc` (normalmente na sua pasta `~`) com seu editor de texto favorito. No final do arquivo, você verá algo como:

```bash
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"
```

A estrutura de um alias é simples:
```bash
alias nome-do-atalho="comando real"
```

Exemplo: ao invés de digitar `docker-compose run --rm` toda vez, eu uso o atalho `d-run`:

```bash
alias d-run="docker-compose run --rm"
```

#### Meus aliases favoritos

```bash
alias d-up="docker-compose up -d"
alias d-down="docker-compose down"
alias d-run="docker-compose run --rm"
alias ..="cd .."
alias d-build="docker-compose up -d --build"
alias update-upgrade="sudo apt update && sudo apt upgrade -y"
alias update="sudo apt update"
alias gtadd="git add ."
alias gtm="git commit -m"
alias gtpm="git push origin master"
alias gtp="git push"
```

> **Lembre-se:** depois de adicionar seus aliases, salve o arquivo `.zshrc` e reinicie o terminal para aplicar as mudanças.

---

### 🔌 Plugin: Autosuggestions

Esse plugin é ótimo para autocompletar comandos com base no histórico. Para instalar:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
echo 'source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh' >> ~/.zshrc
```

---

### 🔧 Personalização

O Zsh tem centenas de plugins e temas. É altamente personalizável. Basta uma busca rápida para encontrar várias ideias. No meu caso, deixo o básico mesmo — o que já me atende muito bem.

---
