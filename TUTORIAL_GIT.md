# Configurando Git e clonando um projeto

## 1. Instalar o Git

No Linux (Mint/Ubuntu):

```bash
sudo apt update
sudo apt install git
```

Verificar instalação:

```bash
git --version
```

---

## 2. Configurar usuário (obrigatório)

Defina seu nome e email (usados nos commits):

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@email.com"
```

Verificar:

```bash
git config --list
```

---

## 3. Gerar chave SSH (recomendado)

Evita precisar digitar senha sempre.

```bash
ssh-keygen -t ed25519 -C "seuemail@email.com"
```

Pressione Enter para aceitar os padrões.

---

## 4. Adicionar chave SSH ao agente

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

## 5. Copiar chave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie o conteúdo.

---

## 6. Adicionar no GitHub

Vá em: Settings → SSH and GPG Keys → New SSH Key

Cole a chave.

---

## 7. Testar conexão

```bash
ssh -T git@github.com
```

Saída esperada:

```
Hi username! You've successfully authenticated...
```

---

## 8. Clonar um projeto

### Via SSH (recomendado):

```bash
git clone git@github.com:usuario/repositorio.git
```

### Via HTTPS:

```bash
git clone https://github.com/usuario/repositorio.git
```

---

## 9. Acessar o projeto

```bash
cd repositorio
```

---

## 10. Fluxo básico (primeiro uso)

```bash
git status
git pull
```

---

# Conceitos rápidos

* **clone** → baixa o repositório
* **pull** → atualiza com mudanças remotas
* **commit** → salva mudanças locais
* **push** → envia mudanças para o repositório

---

# Problemas comuns

## Permissão negada (SSH)

```bash
Permission denied (publickey)
```

Verifique:

```bash
ssh-add -l
```

---

## Repositório não encontrado

* URL errada
* Sem permissão de acesso

---

# Checklist final

* `git --version` funcionando
* usuário configurado
* SSH funcionando
* repositório clonado

---

## Próximos passos

### Criar uma branch

```bash
git checkout -b minha-feature
```

---

### Fazer commits

Adicionar arquivos modificados:

```bash
git add .
```

Criar commit:

```bash
git commit -m "feat: adiciona nova funcionalidade"
```

---

### Enviar para o repositório remoto

```bash
git push origin minha-feature
```

---

### Abrir Pull Request

1. Acesse o repositório no GitHub
2. Clique em **Compare & pull request**
3. Adicione uma descrição clara das alterações
4. Clique em **Create pull request**

---

### Boas práticas

* Use nomes descritivos para branches (ex: `feature/upload-csv`)
* Faça commits pequenos e objetivos
* Escreva mensagens de commit padronizadas (ex: `feat`, `fix`, `chore`)
