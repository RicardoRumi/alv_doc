# SLIDE 11 - EAP (Estrutura Analítica do Projeto)

---

## 📊 Diagrama EAP - Formato Compacto e Legível

**O diagrama abaixo renderiza automaticamente no MkDocs!**

```mermaid
mindmap
  root((Sistema de<br/>Medidas Pessoais))
    1. PLANEJAMENTO
      1.1 Levantamento
        US01 Cadastro
        US02 Login
        US03 Logout
        US10 Recuperação
      1.2 Modelagem
        Modelagem BD
        Arquitetura
      1.3 Prototipação
        Figma
        UX/UI Design
    2. AUTENTICAÇÃO
      2.1 Backend Auth
        US01 Cadastro
        US02 Login
        US03 Logout
        US10 Recuperação
      2.2 Frontend Auth
        Telas Auth
        Validações
    3. GESTÃO MEDIDAS
      3.1 Backend Medidas
        US04 Cadastrar
        US05 Gerar Código
        US08 Deletar
        US09 Validação
      3.2 Frontend Medidas
        Formulário
        Dashboard
        Exibir Código
    4. CONSULTA PÚBLICA
      4.1 Backend API
        US06 Visualizar
        US07 API REST
      4.2 Frontend Público
        Página Consulta
        Exibir Resultados
    5. TESTES
      5.1 Unitários
        Backend
        Frontend
      5.2 Integração
        API
        Fluxos
    6. IMPLANTAÇÃO
      6.1 Backend
        Servidor
        CI/CD
      6.2 Frontend
        Deploy
        DNS
```

---

## 📋 Estrutura da EAP (4 Níveis)

### Nível 1: Projeto Completo
- Sistema de Medidas Pessoais

### Nível 2: 6 Módulos Principais
1. Planejamento
2. Autenticação
3. Gestão de Medidas
4. Consulta Pública
5. Testes
6. Implantação

### Nível 3: Sub-módulos
- Cada módulo dividido em componentes Backend/Frontend ou sub-áreas

### Nível 4: Pacotes de Trabalho
- User Stories (US01-US10)
- Tarefas específicas
- Entregas concretas

---

## ✅ User Stories Incluídas

| US | Descrição | Módulo |
|----|-----------|--------|
| US01 | Cadastro de Usuário | Planejamento / Autenticação |
| US02 | Login de Usuário | Planejamento / Autenticação |
| US03 | Logout de Usuário | Planejamento / Autenticação |
| US04 | Cadastrar Medidas | Gestão de Medidas |
| US05 | Gerar Código de Acesso | Gestão de Medidas |
| US06 | Visualizar por Código | Consulta Pública |
| US07 | API de Consulta | Consulta Pública |
| US08 | Deletar Conta | Gestão de Medidas |
| US09 | Validação de Dados | Gestão de Medidas |
| US10 | Recuperação de Senha | Planejamento / Autenticação |

---

## 📸 Como Exportar para o PowerPoint

### Opção 1: Screenshot Direto (Recomendado)
1. Visualize este slide no MkDocs
2. Zoom no diagrama para tamanho adequado
3. Use ferramenta de screenshot (Print Screen)
4. Cole no PowerPoint Slide 11

### Opção 2: Mermaid Live (Alta Resolução)
1. Copie o código Mermaid acima
2. Acesse: https://mermaid.live/
3. Cole e renderize
4. Download PNG/SVG em alta resolução
5. Insira no PowerPoint

---

## 💡 Por que Mindmap é Melhor?

✅ **Mais legível** - estrutura radial clara  
✅ **Mais compacto** - usa menos espaço  
✅ **Hierarquia visual** - níveis fáceis de identificar  
✅ **Profissional** - formato usado em gestão de projetos  
✅ **Todas as US incluídas** - atende 100% dos requisitos  

---

*Este formato mindmap é muito mais limpo e fácil de ler no PowerPoint!*
