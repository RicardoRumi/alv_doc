# Slide 5 - Containerização

---

## CONTAINERIZAÇÃO COM DOCKER

---

### Aplicação Containerizada

**3 containers:**

1. **Backend** (FastAPI)
2. **Frontend** (Nginx)
3. **Database** (PostgreSQL)

---

### Dockerfile - Backend

**Arquivo:** `system/backend/Dockerfile`

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8001

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8001"]
```

---

### Dockerfile - Frontend

**Arquivo:** `system/frontend/Dockerfile`

```dockerfile
FROM nginx:alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY index.html style.css app.js /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

### Vantagens da Containerização

✅ **Portabilidade** - Roda em qualquer ambiente  
✅ **Isolamento** - Dependências separadas  
✅ **Reprodutibilidade** - Mesmo comportamento  
✅ **Escalabilidade** - Fácil replicar  
✅ **Versionamento** - Imagens tagueadas

