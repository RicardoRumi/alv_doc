# Slide 5 - Banco de Dados

---

## BANCO DE DADOS - PostgreSQL

---

### Modelagem Implementada

**Tabela: usuarios**
```
- id (PK, SERIAL)
- nome (VARCHAR)
- email (VARCHAR UNIQUE)
- senha (VARCHAR - hash)
- codigo_acesso (VARCHAR UNIQUE)
- criado_em (TIMESTAMP)
```

**Tabela: medidas**
```
- id (PK, SERIAL)
- usuario_id (FK → usuarios.id)
- busto (DECIMAL)
- torax (DECIMAL)
- cintura (DECIMAL)
- quadril (DECIMAL)
- coxa (DECIMAL)
- calcado (DECIMAL)
- criado_em (TIMESTAMP)
```

---

### Características

✅ **Normalização:** 3FN aplicada  
✅ **Integridade Referencial:** FK com CASCADE  
✅ **Índices:** email, codigo_acesso  
✅ **Constraints:** UNIQUE, NOT NULL  
✅ **Timestamps:** Auditoria automática

---

### Deploy

**Desenvolvimento:** SQLite (local)  
**Produção:** PostgreSQL (AWS RDS / Neon / Supabase)  
**Backup:** Automático / Manual

