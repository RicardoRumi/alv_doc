# Slide 3 - Backend Desenvolvido

---

## BACKEND - FastAPI

---

### Tecnologias Utilizadas

- **Framework:** FastAPI (Python 3.11)
- **Servidor:** Uvicorn
- **Banco de Dados:** PostgreSQL
- **ORM:** SQLAlchemy (se usado)
- **Autenticação:** JWT / Hash SHA-256
- **Documentação:** Swagger (automática)

---

### Endpoints Implementados

**Autenticação:**
- `POST /api/cadastro` - Cadastro de usuário
- `POST /api/login` - Login

**Medidas:**
- `POST /api/medidas/{usuario_id}` - Adicionar
- `GET /api/medidas/{usuario_id}` - Listar
- `DELETE /api/medidas/{medida_id}` - Deletar

**Consulta Pública:**
- `GET /api/consulta/{codigo}` - Busca por código

**Usuário:**
- `DELETE /api/usuario/{usuario_id}` - Deletar conta

---

### Características

✅ API REST com padrão JSON  
✅ Validação de dados (Pydantic)  
✅ Tratamento de erros  
✅ CORS configurado  
✅ Documentação interativa (/docs)

