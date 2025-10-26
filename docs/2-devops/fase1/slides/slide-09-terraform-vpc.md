# Slide 9 - Terraform - VPC

---

## PROVISIONAMENTO DE VPC

---

### Código Terraform - VPC

**Arquivo:** `environments/dev/main.tf`

```hcl
# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true

  tags = {
    Name        = "dev-medidas-vpc"
    Environment = "dev"
    Project     = "medidas-pessoais"
  }
}

# Internet Gateway
resource "aws_internet_gateway" "main" {
  vpc_id = aws_vpc.main.id

  tags = {
    Name = "dev-medidas-igw"
  }
}
```

---

### Public Subnet

```hcl
resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  availability_zone       = "us-east-1a"
  map_public_ip_on_launch = true

  tags = {
    Name = "dev-medidas-public-subnet"
  }
}
```

---

### Características

✅ DNS habilitado  
✅ IP público automático  
✅ Route Table configurada  
✅ Tags organizadas

