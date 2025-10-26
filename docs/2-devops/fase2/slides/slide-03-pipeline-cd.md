# Slide 3 - Pipeline de Entrega Contínua

---

## PIPELINE CD - EXPANSÃO DO CI

---

### Arquitetura CI/CD Completa

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│   Develop   │ → │  CI Pipeline │ →  │   Staging   │
│  (código)   │    │   (build +   │    │  (testes)   │
└─────────────┘    │    test)     │    └─────────────┘
                   └──────────────┘
                          │
                          ▼
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│     Main    │ → │  CD Pipeline │ →  │  Production │
│  (release)  │    │   (deploy)   │    │   (AWS EC2) │
└─────────────┘    └──────────────┘    └─────────────┘
```

---

### Workflows Implementados

**1. CI Pipeline** (`.github/workflows/ci.yml`)
- Executa em: push/PR
- Build + Test + Lint
- Validação de código

**2. CD Backend** (`.github/workflows/deploy-backend.yml`)
- Trigger: Manual (workflow_dispatch)
- Deploy via SSH
- Restart container backend
- Health check

**3. CD Frontend** (`.github/workflows/deploy-frontend.yml`)
- Trigger: Manual (workflow_dispatch)
- Deploy via SSH
- Restart container frontend
- Health check

---

### Evidências

✅ Screenshot de deploy executado  
✅ Logs de sucesso no Actions  
✅ Sistema acessível em produção  
✅ Health checks passando

