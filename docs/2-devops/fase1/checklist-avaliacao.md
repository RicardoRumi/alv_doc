# CHECKLIST DE AVALIAÇÃO - DevOps FASE 1

---

## ✅ Verifique TUDO Antes de Entregar!

**Nota Total:** 3.0 pontos  
**Prazo:** 10/11/2025

---

## 📊 ITEM 1: Documentação de Planejamento (1.0 ponto)

### Para Conseguir 1.0 pt (Nota Máxima):
- [ ] **Descrição do projeto** clara e completa ✅
- [ ] **Objetivos** bem definidos ✅
- [ ] **Requisitos** detalhados ✅
- [ ] **Plano de integração contínua** consistente ✅
- [ ] **Especificação de infraestrutura** precisa ✅
- [ ] **Link para repositório GitHub** funcionando 🚨

### O que Incluir:

#### 📝 Descrição do Projeto:
- [ ] Nome do projeto
- [ ] Propósito e escopo
- [ ] Tecnologias utilizadas
- [ ] Arquitetura geral
- [ ] Contexto de negócio

#### 🎯 Objetivos:
- [ ] Objetivos principais (3-5 itens)
- [ ] Resultados esperados
- [ ] Métricas de sucesso
- [ ] Benefícios do projeto

#### 📋 Requisitos:
- [ ] Requisitos funcionais (mínimo 5)
- [ ] Requisitos não-funcionais (mínimo 3)
- [ ] Requisitos de infraestrutura
- [ ] Requisitos de segurança

#### 🔄 Plano de Integração Contínua:
- [ ] Fluxo do pipeline CI
- [ ] Ferramentas utilizadas (GitHub Actions)
- [ ] Etapas do processo (build, test, validate)
- [ ] Triggers (quando executar)
- [ ] Estratégia de branches

#### 🏗️ Especificação de Infraestrutura:
- [ ] Recursos necessários (servidores, DB, storage)
- [ ] Ambiente de desenvolvimento
- [ ] Ambiente de staging/produção
- [ ] Ferramentas IaC (Terraform/CloudFormation)
- [ ] Diagrama de infraestrutura

### ⚠️ Cuidado:
- ❌ Falta clareza e detalhes em 1+ itens = máximo 0.6 pts
- ❌ Falta 1-2 aspectos essenciais = máximo 0.3 pts
- ❌ Não apresenta documentação = 0 pontos
- ❌ **Link do repositório quebrado = PERDE PONTOS!**

### ✅ SEU STATUS:
- ⚠️ **AÇÃO:** Escrever documentação completa
- ⚠️ **AÇÃO:** Criar diagrama de infraestrutura
- ⚠️ **AÇÃO:** Validar link do repositório

**Nota esperada:** 1.0 / 1.0 ✓ (após documentar)

---

## 📊 ITEM 2: Pipeline de Integração Contínua (1.0 ponto)

### Para Conseguir 1.0 pt (Nota Máxima):
- [ ] **Repositório GitHub** configurado corretamente ✅
- [ ] **Pipeline de CI funcional** com GitHub Actions ✅
- [ ] **Integração clara** no GitHub Actions ✅
- [ ] **Scripts de build** automatizados ✅
- [ ] **Testados sem erros** ✅

### Estrutura do Repositório:

#### 📁 Organização de Pastas:
- [ ] `.github/workflows/` com arquivo CI
- [ ] `src/` ou código fonte organizado
- [ ] `tests/` com testes automatizados
- [ ] `docs/` com documentação
- [ ] `.gitignore` configurado
- [ ] `README.md` completo

#### 🔧 GitHub Actions (`.github/workflows/ci.yml`):
```yaml
# Exemplo de estrutura esperada:
name: CI Pipeline
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup
      - name: Build
      - name: Test
      - name: Validate
```

### Componentes do Pipeline:

#### 1️⃣ Checkout do Código:
- [ ] Usa `actions/checkout@v3`
- [ ] Configurado corretamente

#### 2️⃣ Setup do Ambiente:
- [ ] Instala dependências
- [ ] Configura linguagem/runtime
- [ ] Usa cache (opcional mas recomendado)

#### 3️⃣ Build:
- [ ] Compila código (se aplicável)
- [ ] Gera artefatos
- [ ] Script automatizado

#### 4️⃣ Testes:
- [ ] Executa testes unitários
- [ ] Executa testes de integração
- [ ] Gera relatório de cobertura

#### 5️⃣ Validações:
- [ ] Linter / Code quality
- [ ] Security scan (opcional)
- [ ] Análise estática

### Funcionalidades Obrigatórias:
- [ ] Pipeline executa automaticamente em push
- [ ] Pipeline executa em pull requests
- [ ] Falha se testes não passam
- [ ] Logs claros e informativos
- [ ] Badge de status no README

### ⚠️ Cuidado:
- ❌ Configurou repositório e pipeline MAS SEM scripts = máximo 0.5 pts
- ❌ Pipeline não funciona ou com erros = máximo 0.5 pts
- ❌ Não apresenta = 0 pontos
- ❌ **Pipeline sem testes automatizados = PERDE PONTOS!**

### ✅ SEU STATUS:
- ⚠️ **AÇÃO:** Criar repositório GitHub
- ⚠️ **AÇÃO:** Configurar GitHub Actions
- ⚠️ **AÇÃO:** Implementar scripts de build
- ⚠️ **AÇÃO:** Adicionar testes automatizados
- ⚠️ **AÇÃO:** Testar pipeline end-to-end

**Nota esperada:** 1.0 / 1.0 ✓ (após implementar)

---

## 📊 ITEM 3: Scripts de Infraestrutura como Código (1.0 ponto)

### Para Conseguir 1.0 pt (Nota Máxima):
- [ ] **Scripts completos** e funcionais ✅
- [ ] **Bem organizados** e estruturados ✅
- [ ] **Uso eficaz** de Terraform ou CloudFormation ✅
- [ ] **Documentação** dos scripts ✅
- [ ] **Testados e validados** ✅

### Opção 1: Terraform

#### 📁 Estrutura de Arquivos:
```
terraform/
├── main.tf           # Recursos principais
├── variables.tf      # Variáveis de entrada
├── outputs.tf        # Outputs
├── provider.tf       # Configuração do provider
├── terraform.tfvars  # Valores das variáveis
└── README.md         # Documentação
```

#### 🔧 Componentes Obrigatórios:
- [ ] **Provider configurado** (AWS, Azure, GCP)
- [ ] **Variáveis definidas** (region, instance_type, etc.)
- [ ] **Recursos provisionados:**
  - [ ] Compute (EC2, VM, Container)
  - [ ] Network (VPC, Subnet, Security Group)
  - [ ] Storage (S3, Blob Storage)
  - [ ] Database (RDS, SQL Database) - opcional
- [ ] **Outputs definidos** (IPs, URLs, DNS)
- [ ] **Backend configurado** (state storage)

#### 📝 Boas Práticas:
- [ ] Usa módulos (se aplicável)
- [ ] Variáveis com descrições
- [ ] Outputs com descrições
- [ ] Comentários explicativos
- [ ] `.gitignore` para arquivos sensíveis

### Opção 2: AWS CloudFormation

#### 📁 Estrutura de Arquivos:
```
cloudformation/
├── template.yaml     # Template principal
├── parameters.json   # Parâmetros
└── README.md         # Documentação
```

#### 🔧 Componentes Obrigatórios:
- [ ] **Template YAML/JSON** bem estruturado
- [ ] **Parameters** definidos
- [ ] **Resources** provisionados:
  - [ ] EC2 Instance ou ECS/Lambda
  - [ ] VPC e Networking
  - [ ] Security Groups
  - [ ] S3 Bucket
  - [ ] RDS Database - opcional
- [ ] **Outputs** definidos
- [ ] **Metadata** e descrições

### Recursos Mínimos a Provisionar:

#### 🖥️ Compute:
- [ ] Servidor/Instância para aplicação
- [ ] Tamanho/tipo especificado
- [ ] AMI ou imagem definida

#### 🌐 Networking:
- [ ] VPC ou Virtual Network
- [ ] Subnet pública/privada
- [ ] Internet Gateway
- [ ] Route Tables
- [ ] Security Groups com regras

#### 💾 Storage:
- [ ] Bucket S3 ou equivalente
- [ ] Configurações de acesso
- [ ] Versionamento (opcional)

#### 🔒 Segurança:
- [ ] Security Groups
- [ ] IAM Roles (se aplicável)
- [ ] Regras de firewall
- [ ] Criptografia configurada

### Documentação dos Scripts:

#### 📄 README.md deve conter:
- [ ] Pré-requisitos (Terraform/AWS CLI instalado)
- [ ] Como inicializar (`terraform init` / CloudFormation setup)
- [ ] Como validar (`terraform validate` / `cfn-lint`)
- [ ] Como aplicar (`terraform apply` / `aws cloudformation deploy`)
- [ ] Como destruir (`terraform destroy`)
- [ ] Variáveis necessárias
- [ ] Outputs esperados
- [ ] Troubleshooting

### Validação:

#### ✅ Checklist de Qualidade:
- [ ] Scripts executam sem erros
- [ ] Infraestrutura é provisionada corretamente
- [ ] Recursos são acessíveis
- [ ] Destruição funciona (cleanup)
- [ ] Idempotente (pode executar múltiplas vezes)
- [ ] Código limpo e organizado
- [ ] Comentários onde necessário

### ⚠️ Cuidado:
- ❌ Scripts funcionais MAS falta clareza/organização = máximo 0.5 pts
- ❌ Scripts incompletos ou com erros = máximo 0.5 pts
- ❌ Não usa Terraform nem CloudFormation = máximo 0.3 pts
- ❌ Não apresenta = 0 pontos
- ❌ **Scripts sem documentação = PERDE PONTOS!**

### ✅ SEU STATUS:
- ⚠️ **AÇÃO:** Escolher Terraform ou CloudFormation
- ⚠️ **AÇÃO:** Criar estrutura de arquivos
- ⚠️ **AÇÃO:** Implementar provisionamento de recursos
- ⚠️ **AÇÃO:** Documentar uso dos scripts
- ⚠️ **AÇÃO:** Testar provisionamento e destruição

**Nota esperada:** 1.0 / 1.0 ✓ (após implementar)

---

## 🎯 RESUMO FINAL

| Item | Pontos | Status | Ação Necessária |
|------|--------|--------|-----------------|
| **1. Documentação** | 1.0 | ❌ Falta | Escrever doc completa + diagrama |
| **2. Pipeline CI** | 1.0 | ❌ Falta | GitHub Actions + scripts + testes |
| **3. Scripts IaC** | 1.0 | ❌ Falta | Terraform/CloudFormation + docs |
| **TOTAL** | **3.0** | | |

---

## ✅ CHECKLIST FINAL ANTES DE ENTREGAR

### Documentação (Item 1):
- [ ] Descrição do projeto completa
- [ ] Objetivos bem definidos (3-5 itens)
- [ ] Requisitos detalhados (5+ funcionais, 3+ não-funcionais)
- [ ] Plano de CI documentado
- [ ] Especificação de infraestrutura com diagrama
- [ ] Link do repositório funcionando
- [ ] Documento no formato PPT do template

### GitHub e CI (Item 2):
- [ ] Repositório criado e público/privado
- [ ] README.md completo
- [ ] `.github/workflows/ci.yml` configurado
- [ ] Pipeline executa em push/PR
- [ ] Build automatizado funciona
- [ ] Testes implementados e passando
- [ ] Badge de status no README
- [ ] Link do repositório no documento

### Infraestrutura como Código (Item 3):
- [ ] Terraform ou CloudFormation escolhido
- [ ] Scripts completos e organizados
- [ ] Provisiona compute + network + storage
- [ ] Variables/Parameters definidos
- [ ] Outputs configurados
- [ ] README com instruções de uso
- [ ] Scripts testados (apply + destroy)
- [ ] Código limpo e comentado

### Qualidade Geral:
- [ ] Sem erros de ortografia
- [ ] Links funcionando
- [ ] Código bem formatado
- [ ] Documentação clara
- [ ] Screenshots/evidências incluídas
- [ ] Organização profissional

---

## 🎉 SE TODOS OS ITENS ESTIVEREM ✅ = 3.0 PONTOS!

---

## ⚠️ ERROS COMUNS QUE TIRAM PONTOS

1. ❌ **Link do repositório quebrado** → Perde pontos no item 1
2. ❌ **Pipeline sem scripts de build** → Máximo 0.5 pts no item 2
3. ❌ **Scripts IaC mal organizados** → Máximo 0.5 pts no item 3
4. ❌ **Falta documentação de IaC** → Perde pontos no item 3
5. ❌ **Pipeline não funcional** → Máximo 0.5 pts no item 2
6. ❌ **Requisitos incompletos** → Máximo 0.6 pts no item 1
7. ❌ **Sem testes automatizados** → Perde pontos no item 2
8. ❌ **Infraestrutura não provisiona** → Máximo 0.5 pts no item 3

---

## 💡 DICAS FINAIS

### Documentação:
- Use diagramas visuais (draw.io, Lucidchart)
- Seja específico e técnico
- Inclua exemplos concretos
- Revise ortografia e gramática

### Pipeline CI:
- Comece com exemplo simples
- Adicione complexidade gradualmente
- Teste cada step separadamente
- Use caching para velocidade
- Adicione badge de status

### Infraestrutura como Código:
- **Terraform recomendado** (mais usado)
- Comece com recursos básicos
- Use variáveis para flexibilidade
- Teste em conta/subscription de teste
- **CUIDADO COM CUSTOS** na cloud!
- Configure alertas de billing

### GitHub:
- Use branches (main, develop)
- Commits descritivos
- README.md profissional
- `.gitignore` configurado
- Licença (MIT recomendada)

---

## 📚 Aulas Essenciais:

1. **Aula 1:** Introdução ao DevOps
2. **Aula 2:** Integração Contínua (CI)
3. **Aula 3:** Entrega Contínua (CD)
4. **Aula 4:** Infraestrutura como Código (IaC)

---

## 🔗 Recursos Úteis:

### Terraform:
- [Documentação Oficial](https://www.terraform.io/docs)
- [Tutorial AWS](https://learn.hashicorp.com/terraform/aws/intro)
- [Best Practices](https://www.terraform-best-practices.com/)

### GitHub Actions:
- [Documentação](https://docs.github.com/en/actions)
- [Marketplace](https://github.com/marketplace?type=actions)
- [Exemplos](https://github.com/actions/starter-workflows)

### CloudFormation:
- [Documentação AWS](https://docs.aws.amazon.com/cloudformation/)
- [Template Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-reference.html)

---

Revise este checklist **ANTES** de enviar o trabalho!  
**Cada ✅ é um ponto garantido!**

Boa sorte na Fase 1 de DevOps! 🚀

