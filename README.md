# 🧪 Projeto de QA Testing

## 📋 Sobre o Projeto
Este repositório contém a implementação do **Teste Prático de QA**, dividido em duas partes principais:
- **UI Testing - Sauce Demo**
- **API Testing - Restful-Booker**

O objetivo é validar funcionalidades críticas, documentar cenários de teste e apresentar evidências claras de execução.

---

## 🛠️ Ferramentas Utilizadas
- **UI Testing:** Cypress / Playwright / Selenium  
- **API Testing:** Postman + Newman  
- **Documentação:** Markdown  
- **Controle de versão:** GitHub  

---

## 🎯 Escopo dos Testes

### UI Testing (Sauce Demo)
**Nível 1 (Obrigatório):**
- Login com diferentes tipos de usuários  
- Ordenação e filtragem de produtos  
- Fluxo completo de compra  
- Remoção de itens do carrinho  
- Navegação entre páginas  
- Logout  

**Nível 2 (Diferencial):**
- Testes de responsividade  
- Testes de acessibilidade  
- Testes automatizados  

---

### API Testing (Restful-Booker)
**Nível 1 (Obrigatório):**
- Autenticação básica  
- CRUD de reservas  
- Validação de campos obrigatórios  

**Nível 2 (Diferencial):**
- Testes de performance  
- Testes de segurança  
- Automação via scripts  

---

## 📑 Estrutura da Documentação

### UI Testing

#### Plano de Testes
- Validar login com diferentes tipos de usuários (válido, inválido, bloqueado)
- Testar ordenação e filtragem de produtos
- Garantir fluxo completo de compra (adicionar → checkout → finalizar)
- Validar remoção de itens do carrinho
- Testar navegação entre páginas
- Validar logout

#### Casos de Teste com Resultados
- **UI-001**: Login com usuário válido → **Passou**
- **UI-002**: Login com usuário bloqueado → **Falhou** (mensagem de erro exibida corretamente)
- **UI-003**: Ordenação por preço → **Passou**
- **UI-004**: Fluxo de compra completo → **Passou**
- (Adicionar evidências com screenshots)

#### Análise de Bugs
- Bug encontrado: ao tentar login com usuário inválido, mensagem de erro pouco clara.  
  - **Severidade:** Média  
  - **Passos para reproduzir:** Inserir credenciais inválidas e tentar login  
  - **Sugestão:** Melhorar feedback ao usuário com mensagem mais descritiva.

#### Sugestões de Melhorias
- Adicionar filtros avançados de produtos
- Melhorar responsividade em dispositivos móveis
- Implementar acessibilidade (labels, contraste)

#### Análise de Riscos
- Risco de falha no checkout em alta carga
- Risco de inconsistência em diferentes navegadores

---

### API Testing

#### Collection de Requests
- Incluída no arquivo `collection.json` (Postman)

#### Documentação dos Cenários
- **API-001**: Autenticação básica → **Passou**
- **API-002**: Criar reserva com campos obrigatórios → **Passou**
- **API-003**: Atualizar reserva existente → **Passou**
- **API-004**: Deletar reserva → **Passou**
- **API-005**: Criar reserva sem campos obrigatórios → **Falhou** (erro retornado corretamente)

#### Resultados dos Testes
- Todos os cenários obrigatórios foram validados
- Evidências em prints das respostas no Postman

#### Análise de Bugs
- Bug encontrado: endpoint `/booking` aceita valores inválidos em `totalprice`  
  - **Severidade:** Alta  
  - **Passos para reproduzir:** Enviar payload com `totalprice: "abc"`  
  - **Sugestão:** Implementar validação de tipos nos campos

#### Variáveis de Ambiente
- `baseURL`: https://restful-booker.herokuapp.com  
- `token`: gerado via autenticação  
- `bookingId`: variável dinâmica para CRUD  

---

## 📤 Evidências
- Screenshots dos testes de UI (login, checkout, carrinho)
- Prints das respostas da API no Postman
- Logs de execução automatizada via Newman

---

## 🚀 Como Executar os Testes

### UI Testing
1. Instale dependências:
   ```bash
   npm install
