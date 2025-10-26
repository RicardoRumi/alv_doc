# Slide 9 - Demonstração Prática

---

## DEMONSTRAÇÃO DO FLUXO COMPLETO

---

### Cenário: Deploy de Nova Feature

**Passo 1: Desenvolvimento Local**
```bash
# Criar feature branch
git checkout -b feature/nova-funcionalidade

# Desenvolver código
vim backend/main.py

# Testar localmente
docker-compose up -d
```

---

**Passo 2: Commit e Push**
```bash
git add .
git commit -m "feat: adiciona nova funcionalidade"
git push origin feature/nova-funcionalidade
```

---

**Passo 3: Pull Request + CI**
- Criar PR no GitHub
- CI executa automaticamente:
  - ✅ Build backend
  - ✅ Build frontend
  - ✅ Testes passam
  - ✅ Lint OK

---

**Passo 4: Merge para Main**
```bash
git checkout main
git merge feature/nova-funcionalidade
git push origin main
```

---

**Passo 5: Deploy Manual (CD)**
- Acessar GitHub Actions
- Workflow: "Deploy Backend"
- Click: "Run workflow"
- Selecionar: environment = "dev"
- Aguardar: 1-2 minutos
- ✅ Deploy concluído

---

**Passo 6: Validação em Produção**
```bash
# Testar no navegador
curl https://SEU-EC2-IP:8001/

# Verificar logs
ssh ubuntu@EC2-IP
docker-compose logs -f backend
```

---

### Evidências

📸 Screenshots de cada etapa  
📹 Vídeo opcional demonstrando fluxo  
📊 Logs de sucesso do deploy

