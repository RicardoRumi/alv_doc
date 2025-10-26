# Slide 11 - Execução do Terraform

---

## COMANDOS TERRAFORM

---

### Workflow de Execução

**1. Inicialização**
```bash
cd system/infra/environments/dev
terraform init
```
- Download de providers
- Inicialização do backend
- Módulos preparados

**2. Planejamento**
```bash
terraform plan
```
- Preview de mudanças
- Validação de sintaxe
- Estimativa de recursos

**3. Aplicação**
```bash
terraform apply
```
- Criação de recursos
- Confirmação manual
- Outputs exibidos

**4. Validação**
```bash
terraform output ec2_public_ip
ssh -i ~/.ssh/medidas-key.pem ubuntu@<IP>
```

---

### Estado da Infraestrutura

**State File:** `terraform.tfstate`
- Estado atual dos recursos
- Mapeamento Terraform ↔ AWS
- Versionado no Git (local backend)

---

### Evidências

✅ Screenshot do `terraform apply` executado  
✅ Outputs mostrando IP do EC2  
✅ EC2 visível no AWS Console  
✅ SSH funcionando

