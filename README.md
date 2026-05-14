# 📋 Desafio QA – Bee Vale & Rambly (2026)

## 🔗 Aplicação analisada

**URL do sistema:**
[https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/](https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/)

---

# 1. Análise inicial da aplicação

## 🎯 Objetivo da aplicação

A aplicação analisada tem como objetivo permitir o **gerenciamento de colaboradores (CRUD)** por meio de uma interface web simples.

O sistema disponibiliza funcionalidades para:

* Visualização de colaboradores cadastrados
* Cadastro de novos colaboradores
* Edição de informações de colaboradores
* Exclusão de registros existentes
* Exibição de um dashboard com indicadores do sistema

Esse tipo de sistema representa um módulo típico de **gestão interna (RH / administrativo)**, utilizado em aplicações reais para controle de dados de funcionários.

---

## 📌 Visão geral da aplicação

A partir da exploração inicial, foi possível identificar que o sistema permite ao usuário:

* Gerenciar uma lista de colaboradores
* Inserir novos registros através de formulários
* Editar dados já existentes
* Remover colaboradores da base
* Visualizar indicadores no dashboard

Apesar de ser uma aplicação simples, ela simula um sistema real de gestão interna, contendo operações críticas de manipulação de dados.

---

## 📄 Plano de Testes

Foi elaborado um **Plano de Testes** contendo estratégia, abordagem, escopo, técnicas e organização da execução.

📎 Acesse aqui:
[Plano de Testes – Bee Vale & Rambly](https://github.com/miguel-luis636/DESAFIO-QA-BEEDOO-2026/blob/main/Plano%20de%20Testes%20%E2%80%93%20Sistema%20de%20Cadastro%20de%20Cursos%20%28Beedoo%29.md)

---

# 2. Principais fluxos da aplicação

## 2.1 Fluxo de autenticação / acesso

O sistema permite acesso inicial à aplicação com possível comportamento de login simplificado.

Fluxo:

* Acessar sistema
* Validar acesso (quando aplicável)
* Redirecionamento para dashboard

📌 Observação: há indícios de ausência de proteção de rotas consistente.

---

## 2.2 Fluxo de cadastro de colaboradores

Fluxo principal da aplicação.

Etapas:

1. Acessar formulário de cadastro
2. Preencher dados do colaborador
3. Submeter formulário
4. Sistema processa e armazena dados
5. Colaborador é exibido na listagem

✔ Fluxo crítico do sistema

---

## 2.3 Fluxo de listagem de colaboradores

Permite visualizar colaboradores cadastrados.

Validações esperadas:

* Exibição correta dos dados
* Atualização após criação
* Consistência entre dados e interface

---

## 2.4 Fluxo de edição de colaboradores

Permite alteração de dados existentes.

Pontos avaliados:

* Abertura correta dos dados no formulário
* Persistência das alterações
* Atualização na listagem

---

## 2.5 Fluxo de exclusão de colaboradores

Fluxo crítico e sensível.

Observado comportamento de:

* Falhas de referência de ID
* Possível inconsistência de estado
* Execução duplicada de ações

---

# 3. Bugs identificados

## 🐞 3.1 Erro de timeout assíncrono não tratado

```txt
Uncaught (in promise) Error: Timeout de comunicação com o servidor.
at fakeAsyncSave (script.js:442)
```

### Problema

* Promise rejeitada sem tratamento (`catch`)
* Falta de tratamento de erro no fluxo assíncrono

### Impacto

* UX ruim
* Possível perda de dados
* Console expõe erro técnico

### Severidade: 🔴 Alta

---

## 🐞 3.2 Erro de acesso a objeto undefined

```txt
Uncaught TypeError: can't access property "name", employees[idx] is undefined
```

### Problema

* Uso de índice inválido
* Estado do array inconsistente

### Impacto

* Crash de execução no delete
* Falha no fluxo de exclusão

### Severidade: 🔴 Alta

---

## 🐞 3.3 Inconsistência de exclusão de colaboradores

```txt
Colaborador não encontrado para exclusão. ID: 7
Excluído: Elisa Rodrigues
```

### Problema

* Inconsistência entre ID e estado do array
* Possível dupla execução de função

### Impacto

* Exclusão incorreta ou duplicada
* Inconsistência de dados

### Severidade: 🔴 Alta

---

## 🐞 3.4 Falta de validação de campos

* Campos aceitam dados inválidos
* Possível ausência de máscaras (CPF, salário, email)

### Impacto

* Dados inconsistentes
* Risco de corrupção de informação

### Severidade: 🟠 Média

---

## 🐞 3.5 Problemas de UX e feedback

* Falta de loading states
* Falta de mensagens claras de erro/sucesso
* Confirmações genéricas

---

## 🐞 3.6 Problemas de responsividade

* Tabela com muitas colunas
* Possível overflow em telas menores
* UX prejudicada em mobile

---

# 4. Pontos críticos para teste

## 4.1 Fluxo de cadastro

* Validação de campos obrigatórios
* Persistência de dados
* Evitar duplicidade

---

## 4.2 Fluxo de exclusão

* Validação de existência do ID
* Prevenção de execução dupla
* Confirmação clara da ação

---

## 4.3 Integridade de dados

* Consistência entre UI e estado interno
* Atualização correta da listagem

---

## 4.4 Tratamento de erros

* Promises rejeitadas tratadas corretamente
* Mensagens amigáveis ao usuário

---

# 5. Estratégia de testes

A abordagem utilizada foi baseada em:

* 🔍 Testes exploratórios
* ⚙️ Testes funcionais
* ❌ Testes negativos
* ⚠️ Testes baseados em risco

---

## Foco principal:

* Fluxos de CRUD (criação, leitura, atualização, exclusão)
* Consistência de dados
* Tratamento de erros
* Experiência do usuário

---

# 6. Análise de Riscos dos Fluxos da Aplicação

Durante a análise da aplicação foi realizada uma avaliação de riscos com o objetivo de identificar quais funcionalidades possuem maior impacto para o negócio e quais apresentam maior probabilidade de falha.

A análise considerou:

* Criticidade do fluxo
* Impacto ao usuário
* Integridade dos dados
* Confiabilidade da aplicação
* Experiência do usuário
* Possíveis falhas técnicas identificadas durante os testes exploratórios

---

| Fluxo / Funcionalidade             | Gravidade | Probabilidade | Impacto no Sistema                                                           | Riscos Identificados                                                                          | Mitigação Recomendada                                                                                            |
| ---------------------------------- | --------- | ------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Cadastro de colaboradores          | Alta      | Alta          | Usuários não conseguem registrar novos colaboradores corretamente            | Falhas de validação, timeout assíncrono, duplicidade de cadastro, ausência de feedback visual | Implementar validações robustas, tratamento correto de Promises, loading states e prevenção de múltiplos submits |
| Exclusão de colaboradores          | Crítica   | Alta          | Possibilidade de exclusão incorreta ou inconsistência de dados               | Uso inconsistente de ID/índice, erro `employees[idx] undefined`, dupla execução de delete     | Utilizar IDs únicos, validações defensivas, controle de estado e confirmação segura                              |
| Edição de colaboradores            | Alta      | Média         | Alterações podem não persistir corretamente ou sobrescrever dados incorretos | Falta de validação de integridade e atualização inconsistente da UI                           | Validar persistência dos dados e sincronização correta da interface                                              |
| Listagem de colaboradores          | Alta      | Média         | Dados podem não refletir o estado real da aplicação                          | Atualização inconsistente após operações CRUD                                                 | Testar atualização dinâmica da listagem e sincronização de estado                                                |
| Tratamento de erros assíncronos    | Alta      | Alta          | Aplicação pode apresentar falhas silenciosas ou quebrar fluxos críticos      | `Uncaught (in promise)` e ausência de tratamento de exceções                                  | Implementar `try/catch`, mensagens amigáveis e logs controlados                                                  |
| Validação de formulário            | Alta      | Alta          | Dados inválidos podem comprometer integridade do sistema                     | Campos sem máscara ou validação adequada                                                      | Aplicar validações client-side e server-side                                                                     |
| Controle de sessão / autenticação  | Alta      | Média         | Possível acesso indevido ao sistema                                          | Indícios de ausência de proteção de rotas                                                     | Implementar autenticação e controle de acesso adequados                                                          |
| Experiência do usuário (UX)        | Média     | Alta          | Usuário pode ter dúvidas ou executar ações incorretas                        | Falta de feedback visual, mensagens genéricas e fluxo pouco intuitivo                         | Melhorar mensagens, loading states, toasts e feedbacks visuais                                                   |
| Responsividade da interface        | Média     | Média         | Dificuldade de uso em dispositivos móveis                                    | Tabelas extensas e possível overflow horizontal                                               | Implementar design responsivo e adaptação mobile                                                                 |
| Consistência visual e design       | Baixa     | Média         | Impacto na percepção de qualidade do produto                                 | Inconsistência de idioma e organização visual                                                 | Padronizar interface e textos do sistema                                                                         |
| Segurança de informações           | Alta      | Média         | Exposição indevida de credenciais e dados                                    | Credenciais exibidas na tela inicial                                                          | Remover informações sensíveis e aplicar boas práticas de segurança                                               |
| Integridade de estado da aplicação | Crítica   | Alta          | Dados podem ficar inconsistentes entre UI e memória da aplicação             | Estado inconsistente durante operações de exclusão e atualização                              | Melhor gerenciamento de estado e validações antes das operações                                                  |

---

# 📌 Considerações da análise de risco

Os fluxos mais críticos identificados durante os testes foram:

* Exclusão de colaboradores
* Cadastro de novos registros
* Tratamento de erros assíncronos
* Integridade do estado da aplicação

Esses fluxos foram priorizados por apresentarem maior impacto funcional e maior risco de comprometer a confiabilidade do sistema.

Além disso, foram identificados problemas relacionados à experiência do usuário e tratamento inadequado de exceções, fatores que podem impactar diretamente a percepção de qualidade da aplicação.



---

# 7. Limitações da análise

Não foram executados:

* Testes automatizados (Cypress / Playwright)
* Testes de performance
* Testes de segurança aprofundados
* Testes de carga

---

# 8. Conclusão da análise

A aplicação apresenta uma estrutura funcional de CRUD, porém foram identificados problemas importantes relacionados a:

* Tratamento de erros assíncronos
* Inconsistência de estado da aplicação
* Validação de dados insuficiente
* Problemas de UX
* Riscos no fluxo de exclusão

Esses pontos impactam diretamente a confiabilidade do sistema e devem ser priorizados para correção.
