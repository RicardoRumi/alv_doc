# Slide 8 - Fluxograma DevOps

---

## FLUXOGRAMA COMPLETO DO PIPELINE

---

### Fluxo CI/CD End-to-End

```
┌─────────────────────────────────────────────────────────┐
│              DESENVOLVEDOR                              │
│         git commit + push                               │
└──────────────────┬──────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────┐
│         GITHUB (Version Control)                        │
│         Código versionado no repositório                │
└──────────────────┬──────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────┐
│       CI PIPELINE (GitHub Actions)                      │
│  ┌────────────┬────────────┬─────────────┬──────────┐  │
│  │  Checkout  │   Build    │    Test     │   Lint   │  │
│  │   Code     │  Backend + │  Pytest +   │  Flake8  │  │
│  │            │  Frontend  │  Coverage   │  ESLint  │  │
│  └────────────┴────────────┴─────────────┴──────────┘  │
│              ✅ APROVADO ou ❌ FALHA                     │
└──────────────────┬──────────────────────────────────────┘
                   │
                   ▼ (Se APROVADO)
┌─────────────────────────────────────────────────────────┐
│      TRIGGER MANUAL (workflow_dispatch)                 │
│      Desenvolvedor decide fazer deploy                  │
└──────────────────┬──────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────┐
│       CD PIPELINE (GitHub Actions)                      │
│  ┌──────────────────────────────────────────────────┐  │
│  │  1. SSH no EC2                                   │  │
│  │  2. Git pull (atualiza código)                   │  │
│  │  3. Docker build (novas imagens)                 │  │
│  │  4. Docker-compose up -d (restart containers)    │  │
│  │  5. Health check (valida se está OK)             │  │
│  └──────────────────────────────────────────────────┘  │
└──────────────────┬──────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────┐
│         PRODUÇÃO (AWS EC2)                              │
│  ┌────────────┬────────────┬──────────────┐            │
│  │  Frontend  │  Backend   │   Database   │            │
│  │  (Nginx)   │  (FastAPI) │ (PostgreSQL) │            │
│  │  Port 80   │  Port 8001 │  Port 5432   │            │
│  └────────────┴────────────┴──────────────┘            │
│         Aplicação rodando para usuários                 │
└─────────────────────────────────────────────────────────┘
```

---

### Legenda

🔵 **Automático** - CI executa em cada push  
🟡 **Manual** - CD requer trigger manual  
🟢 **Produção** - Sistema acessível

