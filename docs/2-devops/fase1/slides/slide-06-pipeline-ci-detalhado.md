# Slide 6 - Pipeline CI Detalhado

---

## PIPELINE CI - IMPLEMENTAÇÃO

---

### Estrutura do Workflow CI

**Arquivo:** `.github/workflows/ci.yml`

```yaml
name: CI Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  backend-build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      - run: pip install -r backend/requirements.txt
      - run: pytest backend/tests/
  
  frontend-build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: docker build -t frontend frontend/
```

---

### Status do Pipeline

✅ **Configurado** - Repositório conectado  
✅ **Funcional** - Builds executando  
✅ **Testado** - Validado com commits reais  
✅ **Documentado** - README com instruções

---

### Evidências

📸 Screenshot do Actions executando  
📊 Badge no README mostrando status  
🔗 Link para runs do GitHub Actions

