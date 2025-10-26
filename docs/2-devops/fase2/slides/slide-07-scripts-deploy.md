# Slide 7 - Scripts de Deploy

---

## SCRIPTS DE DEPLOY AUTOMATIZADO

---

### Estrutura dos Scripts

```
system/
├── .github/workflows/
│   ├── ci.yml                # Build + Test
│   ├── deploy-backend.yml    # Deploy backend
│   └── deploy-frontend.yml   # Deploy frontend
├── docker-compose.yml        # Orquestração
└── scripts/
    └── deploy.sh             # Script auxiliar (opcional)
```

---

### Script de Deploy SSH

**Dentro do GitHub Actions:**

```bash
#!/bin/bash
# Deploy script executado no EC2

# Navegarpara projeto
cd ~/system || exit 1

# Atualizar código
git fetch origin
git reset --hard origin/main

# Deploy do serviço
docker-compose pull backend
docker-compose up -d --build --no-deps backend

# Aguardar inicialização
sleep 10

# Verificar saúde
docker-compose ps backend
curl -f http://localhost:8001/ || {
  echo "Health check failed!"
  docker-compose logs backend
  exit 1
}

echo "Deploy completed successfully!"
```

---

### Características

✅ **Idempotente** - Pode executar múltiplas vezes  
✅ **Rollback** - Git reset para versão anterior  
✅ **Health Check** - Valida antes de finalizar  
✅ **Logs** - Captura erros automaticamente  
✅ **Zero Downtime** - Deploy sem parar outros serviços

