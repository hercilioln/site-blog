---
title: "Otimizando o uso do Terminal (Ubuntu/WSL)"
date: 2025-05-09T11:12:46-03:00
draft: false
tags: ["tutorial", "zsh", "terminal"]
categories: ["tutorial"]
---

---
Se você usa o WSL ou alguma distro Linux e quer turbinar seu terminal com ferramentas que facilitam seu dia-a-dia, este tutorial é para você! Aqui vou mostrar como instalar e usar ferramentas que ajudam na produtividade do meu trabalho. Todas essas ferramentas são leves, práticas e vão deixar seu workflow muito mais produtivo.

---

### 1. **lazydocker** – Gerencie seus containers Docker com interface TUI

> <small>Dica: nunca use o Docker Deskto no Windows quando for usar no WSL, instale direto no Ubuntu pelo terminal e use essa ferramenta para gerenciar os contêineres, o Docker Desktop pode facilitar a visualização e tal, mas consume muita memória e processamento. </small>

**Instalação:**
```bash
curl https://raw.githubusercontent.com/jesseduffield/lazydocker/master/scripts/install_update_linux.sh | bash
```
Se preferir, baixe o binário mais recente do [repositório oficial](https://github.com/jesseduffield/lazydocker/releases).

**Como usar:**

Basta rodar:
```bash
lazydocker
```
Você verá uma interface interativa para visualizar, iniciar, parar e inspecionar contêineres, volumes, imagens e mais.

---

### 2. **dockerly** – Gerenciador de containers Docker via terminal

> <small>Esse também tem uma interface bem legal, igual o lazydocker, eu uso ambos porque algumas funcionalidades tem nesse que não tem no outro, então eu acabo usando ambos quando necessário.</small>

**Instalação**
 
```bash
pip install dockerly
```

Se não tiver o pip instalado, rode:

```bash
sudo apt update && sudo apt install python3-pip
```
**Como usar:**

Execute:
```bash
dockerly
```

Você terá uma interface amigável para gerenciar contêineres, imagens e volumes.

---

### 3. **nnn** – Gerenciador de arquivos ultra rápido

**Instalação:**

```bash
sudo apt update
sudo apt install nnn
```

**Como usar:**

No terminal, digite:

```bash
nnn
```

Use as setas para navegar, Enter para abrir diretórios/arquivos, `q` para sair. Explore os atalhos pressionando `?` dentro do nnn.

---

### 4. **ncdu** – Analise o uso de espaço em disco

**Instalação:**

```bash
sudo apt update
sudo apt install ncdu
```

**Como usar:**

Para analisar o uso de espaço do diretório atual:
```bash
ncdu
```
Ou de um diretório específico:
```bash
ncdu /caminho/do/diretorio
```
Navegue com as setas, pressione `d` para deletar arquivos/pastas e `q` para sair.

---

### 5. **z** – Navegação rápida entre diretórios

**Instalação:**

```bash
git clone https://github.com/rupa/z.git ~/z
echo '. ~/z/z.sh' >> ~/.zshrc
source ~/.zshrc
```

**Como usar:**

O `z` aprende os diretórios que você mais acessa. Depois de navegar normalmente por alguns diretórios. Primeiro você precisa navegar normalmente entre as pastas com o `cd`. Exemplo:

```bash
cd Pasta1/Projetos/Projeto1
```

Depois basta digitar: 

```bash
z Projeto1
```
Independente de onde você estiver com esse comando ele vai direto para pasta selecionada.

> <small>Dica: quanto mais você usa, mais inteligente ele fica!</small>

---

### 6. **git-open** – Abra o repositório remoto do git no navegador

**Instalação:**
```bash
npm install --global git-open
```

Se não tiver o npm:
```bash
sudo apt install nodejs npm
```

**Como usar:**

Dentro de um repositório git, digite:
```bash
git open
```
O navegador padrão abrirá a página do repositório remoto (GitHub, GitLab, Bitbucket, etc).
<br>
<br>

## Plugins para o ZSH 🔌
---

### 7. **zsh-autosuggestions** – Sugestões automáticas de comandos no Zsh

**Instalação:**

> Se ainda não usa o Zsh: (Tem tutorial [aqui](/posts/configurando-zsh/) de instalação)
Depois, instale o plugin:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
echo 'source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh' >> ~/.zshrc
source ~/.zshrc
```

**Como usar:**
Ao digitar comandos, sugestões baseadas no histórico aparecerão em cinza. Pressione a seta para a direita `(→)` para aceitar a sugestão.

---

### 8. **zsh-syntax-highlighting** – Realce de sintaxe para comandos no Zsh

**Instalação**:

Primeiro, clone o repositório do plugin:
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.zsh/zsh-syntax-highlighting
```
Depois, adicione a seguinte linha ao final do seu `~/.zshrc` (depois de carregar outros plugins):
```bash
source ~/.zsh/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

Recarregue o Zsh:
```bash
source ~/.zshrc
```

**Como usar:**
Agora, ao digitar comandos no terminal, eles aparecerão em verde se forem válidos e em vermelho se houver algum erro de sintaxe ou se o comando não existir. Isso ajuda a evitar erros antes mesmo de executar o comando!

---
Se gostou, compartilhe este tutorial e deixe seu terminal ainda mais poderoso 🚀