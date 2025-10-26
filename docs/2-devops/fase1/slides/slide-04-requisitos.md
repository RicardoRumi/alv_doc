# Slide 4 - Requisitos

---

## REQUISITOS DO PROJETO

---

### Requisitos Funcionais

**RF01** - Pipeline CI deve executar em cada push/PR  
**RF02** - Build automatizado do backend (Python)  
**RF03** - Build automatizado do frontend (Docker)  
**RF04** - Execução de testes automatizados  
**RF05** - Validação de código (linting)  
**RF06** - Provisionamento de VPC via Terraform  
**RF07** - Provisionamento de EC2 via Terraform  
**RF08** - Scripts IaC versionados no Git

---

### Requisitos Não-Funcionais

**RNF01** - Pipeline deve executar em < 5 minutos  
**RNF02** - Scripts Terraform devem ser modulares  
**RNF03** - Documentação clara e completa  
**RNF04** - Código IaC deve seguir best practices  
**RNF05** - Secrets devem ser gerenciados com segurança

---

### Requisitos de Infraestrutura

**Componentes AWS:**
- VPC (10.0.0.0/16)
- Subnet pública
- Internet Gateway
- EC2 t2.micro (free tier)
- Security Groups (22, 80, 443, 8001)

**Ferramentas:**
- GitHub Actions (CI)
- Terraform >= 1.0 (IaC)
- Docker (containerização)

