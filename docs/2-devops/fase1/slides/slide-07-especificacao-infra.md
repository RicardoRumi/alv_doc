# Slide 7 - Especificação da Infraestrutura

---

## ESPECIFICAÇÃO DA INFRAESTRUTURA

---

### Arquitetura AWS

```
┌─────────────────────────────────────┐
│           AWS Cloud (us-east-1)     │
│                                     │
│  ┌───────────────────────────────┐ │
│  │  VPC (10.0.0.0/16)            │ │
│  │                               │ │
│  │  ┌─────────────────────────┐ │ │
│  │  │ Public Subnet           │ │ │
│  │  │ (10.0.1.0/24)           │ │ │
│  │  │                         │ │ │
│  │  │  ┌──────────────────┐  │ │ │
│  │  │  │ EC2 t2.micro     │  │ │ │
│  │  │  │ Ubuntu 22.04     │  │ │ │
│  │  │  │ Docker + App     │  │ │ │
│  │  │  └──────────────────┘  │ │ │
│  │  │                         │ │ │
│  │  └─────────────────────────┘ │ │
│  │           │                   │ │
│  │  ┌────────▼────────┐         │ │
│  │  │ Internet Gateway│         │ │
│  │  └─────────────────┘         │ │
│  └───────────────────────────────┘ │
└─────────────────────────────────────┘
```

---

### Recursos Provisionados

**Rede:**
- 1x VPC (10.0.0.0/16)
- 1x Subnet pública (10.0.1.0/24)
- 1x Internet Gateway
- 1x Route Table

**Computação:**
- 1x EC2 t2.micro (Ubuntu 22.04)
- 1x Security Group (22, 80, 443, 8001)
- 1x Key Pair (para SSH)

**Armazenamento:**
- 20 GB EBS gp3

---

### Custos Estimados

**Free Tier:** $0/mês  
**Pós Free Tier:** ~$10-15/mês

