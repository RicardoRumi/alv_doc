# Slide 4 - CD Pipeline Detalhado

---

## IMPLEMENTAÇÃO DO CD

---

### Workflow Deploy Backend

**Arquivo:** `.github/workflows/deploy-backend.yml`

```yaml
name: Deploy Backend

on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment'
        required: true
        default: 'dev'

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Deploy via SSH
        uses: appleboy/ssh-action@master
        with:
          host: ${{ secrets.EC2_HOST }}
          username: ${{ secrets.SSH_USER }}
          key: ${{ secrets.SSH_PRIVATE_KEY }}
          script: |
            cd ~/system
            git pull origin main
            docker-compose up -d --build backend
            docker-compose ps backend
```

---

### Secrets Configurados

**GitHub Secrets:**
- `EC2_HOST` - IP público do EC2
- `SSH_USER` - ubuntu
- `SSH_PRIVATE_KEY` - Chave privada .pem

---

### Processo de Deploy

1. **Trigger Manual** - Dev clica "Run workflow"
2. **SSH Connection** - GitHub Actions conecta ao EC2
3. **Pull Code** - Atualiza código do repositório
4. **Build Image** - Docker build da nova versão
5. **Deploy** - `docker-compose up -d`
6. **Health Check** - Valida se está rodando
7. **Summary** - Exibe resultado

---

### Exemplo de Uso

✅ Desenvolvedor faz commit  
✅ CI valida o código  
✅ Se OK, trigger deploy manual  
✅ Aplicação atualizada em < 2min

