# SLIDE 17 - Modelagem do Banco de Dados

---

## ⚠️ IMPORTANTE

**Este slide deve conter o DIAGRAMA ER do banco de dados**

### Como criar o diagrama:

1. Acesse: **https://dbdiagram.io** ou **Draw.io**
2. Crie 2 tabelas: `usuarios` e `medidas`
3. Configure relacionamento 1:0..1
4. Exporte como **PNG** (alta resolução)
5. Insira a imagem neste slide do PowerPoint

---

## Estrutura do Banco

### Tabela: usuarios
- `id` (UUID, PK)
- `email` (VARCHAR, UNIQUE, NOT NULL)
- `senha_hash` (VARCHAR, NOT NULL)
- `data_criacao` (TIMESTAMP)
- `data_atualizacao` (TIMESTAMP)

### Tabela: medidas
- `id` (UUID, PK)
- `usuario_id` (UUID, FK, UNIQUE)
- `busto, torax, cintura, quadril, coxa` (DECIMAL)
- `calcado` (INTEGER)
- `codigo_acesso` (VARCHAR, UNIQUE, INDEX)
- `data_criacao, data_atualizacao` (TIMESTAMP)

---

**Relacionamento:** usuarios (1) ─── (0..1) medidas

---

📄 **Referência:** `5-modelagem-banco.md` com SQL completo

---

*Insira a IMAGEM do diagrama ER neste slide do PowerPoint*

