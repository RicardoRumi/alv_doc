# SLIDE 5 - Requisitos Não Funcionais

---

## 2 Requisitos Não Funcionais (RNF)

### RNF01 - Segurança
**Descrição:** As senhas devem ser armazenadas com hash (bcrypt ou similar) e os dados devem trafegar por HTTPS.

**Justificativa:** Proteger dados sensíveis dos usuários contra acessos não autorizados e ataques.

**Implementação:**
- Hash de senhas com bcrypt
- Comunicação HTTPS obrigatória
- JWT para autenticação

---

### RNF02 - Performance
**Descrição:** As consultas à API devem responder em menos de 500ms para 95% das requisições.

**Justificativa:** Garantir boa experiência do usuário e viabilizar integração com e-commerces.

**Implementação:**
- Índices no banco de dados
- Cache de consultas frequentes
- Otimização de queries

---

*Copie e cole este conteúdo no slide 5 do seu PowerPoint*

