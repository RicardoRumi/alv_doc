# Slide 6 - Orquestração com Docker Compose

---

## DOCKER COMPOSE - ORQUESTRAÇÃO

---

### Arquivo docker-compose.yml

**Arquivo:** `system/docker-compose.yml`

```yaml
version: '3.8'

services:
  frontend:
    build: ./frontend
    ports:
      - "80:80"
    depends_on:
      - backend
    networks:
      - medidas-network

  backend:
    build: ./backend
    ports:
      - "8001:8001"
    environment:
      - DATABASE_URL=postgresql://medidas:senha123@database:5432/medidas_db
    depends_on:
      - database
    networks:
      - medidas-network

  database:
    image: postgres:15-alpine
    environment:
      - POSTGRES_USER=medidas
      - POSTGRES_PASSWORD=senha123
      - POSTGRES_DB=medidas_db
    volumes:
      - postgres-data:/var/lib/postgresql/data
    networks:
      - medidas-network

volumes:
  postgres-data:

networks:
  medidas-network:
```

---

### Gerenciamento

**Comandos:**
```bash
# Subir todos os containers
docker-compose up -d

# Ver status
docker-compose ps

# Ver logs
docker-compose logs -f backend

# Restart específico
docker-compose restart frontend

# Parar tudo
docker-compose down
```

---

### Benefícios

✅ Multi-container com 1 comando  
✅ Rede isolada entre containers  
✅ Variáveis de ambiente centralizadas  
✅ Volumes persistentes  
✅ Dependências gerenciadas

