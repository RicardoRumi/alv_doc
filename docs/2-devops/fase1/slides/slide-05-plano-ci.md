# Slide 5 - Plano de Integração Contínua

---

## PLANO DE INTEGRAÇÃO CONTÍNUA (CI)

---

### Estratégia de CI

**Ferramenta:** GitHub Actions

**Gatilhos:**
- Push em branches `main` e `develop`
- Pull Requests
- Workflow manual (workflow_dispatch)

---

### Workflow: CI Pipeline

**Etapas:**

1. **Checkout Code**
   - Clone do repositório
   - Configuração do ambiente

2. **Build Backend**
   - Setup Python 3.11
   - Instalar dependências (`pip install -r requirements.txt`)
   - Validar sintaxe

3. **Build Frontend**
   - Build da imagem Docker
   - Validar Dockerfile

4. **Tests**
   - Executar testes unitários (pytest)
   - Validar cobertura mínima

5. **Linting**
   - Flake8 (Python)
   - ESLint (JavaScript)

6. **Security Scan** (opcional)
   - Bandit (Python security)
   - Dependências vulneráveis

---

### Arquivos de Configuração

```
.github/workflows/
├── ci.yml          # Pipeline principal
├── deploy-backend.yml
└── deploy-frontend.yml
```

