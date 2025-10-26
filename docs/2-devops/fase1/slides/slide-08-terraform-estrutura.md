# Slide 8 - Terraform - Estrutura

---

## SCRIPTS DE INFRAESTRUTURA COMO CÓDIGO

---

### Estrutura do Projeto Terraform

```
system/infra/
├── modules/
│   └── ec2/
│       ├── main.tf        # Recursos EC2 + SG
│       ├── variables.tf   # Inputs
│       └── outputs.tf     # Outputs
└── environments/
    └── dev/
        ├── main.tf        # VPC + Subnet + Module
        ├── variables.tf   # Variáveis
        ├── outputs.tf     # Outputs
        └── terraform.tfvars  # Valores
```

---

### Organização Modular

**Vantagens:**
- ✅ Reutilização de código
- ✅ Separação de ambientes (dev/prod)
- ✅ Manutenção facilitada
- ✅ Testes isolados

---

### Provider Configurado

```hcl
terraform {
  required_version = ">= 1.0"
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
```

