# ecosistema
Ecosistema de automação

---

## 🐳 Tutorial de Instalação do Docker no Ubuntu (passo a passo)

### ✅ Requisitos:

* Distribuição Ubuntu 22.04, 20.04 ou 18.04
* Acesso root ou a um usuário com permissões `sudo`

---

### 1️⃣ Atualize o sistema

```bash
sudo apt update
sudo apt upgrade -y
```

---

### 2️⃣ Remova versões antigas do Docker (se existirem)

```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

---

### 3️⃣ Instale dependências necessárias

```bash
sudo apt install -y ca-certificates curl gnupg lsb-release
```

---

### 4️⃣ Adicione a chave GPG oficial do Docker

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

---

### 5️⃣ Adicione o repositório do Docker

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

### 6️⃣ Atualize o cache dos pacotes

```bash
sudo apt update
```

---

### 7️⃣ Instale o Docker Engine

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

### 8️⃣ Verifique se o Docker está funcionando

```bash
sudo docker run hello-world
```

Se aparecer uma mensagem de boas-vindas do Docker, a instalação foi concluída com sucesso 🎉

---

### 🔁 (Opcional) Permitir rodar Docker sem `sudo`

```bash
sudo usermod -aG docker $USER
newgrp docker
```

⚠️ Você precisa **fazer logout e login novamente** (ou reiniciar o terminal) para que a mudança de grupo funcione corretamente.

---

### 🧪 Verifique a versão do Docker

```bash
docker --version
docker compose version
```

---

### 📌 Dica: Iniciar Docker com o sistema

```bash
sudo systemctl enable docker
sudo systemctl start docker
```
