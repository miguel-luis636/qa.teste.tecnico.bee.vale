# 📝 Relatório de Testes Exploratórios – Sistema de Gestão de Colaboradores (Bee Vale)

---

# 🔹 Informações Gerais

* **Projeto:** Sistema de Gestão de Colaboradores – Bee Vale
* **Empresa:** Bee Vale
* **Data do Teste:** 15/05/2026
* **Testador:** Miguel Luis
* **Tipo de Teste:** Testes Funcionais, Exploratórios, UX, Validação de Dados e Tratamento de Erros

---

# 🔹 Ambiente de Teste

| Item                   | Descrição                                                                                                           |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Aplicação              | Sistema de Gestão de Colaboradores                                                                                  |
| Ambiente               | Produção                                                                                                            |
| URL da aplicação       | [Sistema Bee Vale](https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/?utm_source=chatgpt.com)      |
| Repositório            | [Repositório GitHub do Projeto](https://github.com/miguel-luis636/qa.teste.tecnico.bee.vale?utm_source=chatgpt.com) |
| Navegador              | Firefox 148 64 bits                                                                                                 |
| Sistema Operacional    | Windows 11                                                                                                          |
| Ferramentas utilizadas | DevTools, Console do navegador, Network, Inspeção de elementos                                                      |

---

# 🔹 Escopo dos Testes

Os testes exploratórios consideraram principalmente os seguintes fluxos:

* Cadastro de colaboradores
* Edição de colaboradores
* Exclusão de colaboradores
* Listagem de colaboradores
* Validações de formulário
* Cenários negativos
* Tratamento de erros
* Comportamentos inesperados
* Usabilidade e responsividade

---

# 🔹 Resultados da Execução dos Testes

Durante a execução dos testes manuais foram avaliados **33 cenários de teste** relacionados aos fluxos principais do sistema.

Os cenários cobriram principalmente:

* Cadastro de colaboradores
* Edição de colaboradores
* Exclusão de colaboradores
* Atualização da listagem
* Validações de formulário
* Tratamento de erros
* Responsividade
* Comportamentos inesperados

---

# 📊 Resumo da Execução

| Métrica                             | Quantidade | Percentual |
| ----------------------------------- | ---------- | ---------- |
| **Total de Cenários**               | 33         | 100%       |
| **Cenários OK**                     | 20         | 60,61%     |
| **Cenários NOK**                    | 10         | 30,30%     |
| **Cenários Parcialmente Validados** | 3          | 9,09%      |
| **Cenários não testados**           | 0          | 0%         |

---

# 📈 Interpretação dos Resultados

Os resultados demonstram que o sistema apresenta funcionamento parcial dos fluxos principais, porém ainda possui falhas importantes relacionadas principalmente à:

* validação de dados
* tratamento de estados inconsistentes
* feedback ao usuário
* responsividade
* robustez do frontend

Dos **33 cenários executados**:

* **20 cenários passaram com sucesso**
* **10 cenários apresentaram falhas**
* **3 cenários ficaram parcialmente validados**

Os problemas encontrados impactam principalmente a confiabilidade dos dados e a estabilidade da aplicação.

---

# 📉 Distribuição dos Resultados

* 🟢 **Cenários OK:** 60,61%
* 🔴 **Cenários NOK:** 30,30%
* 🟡 **Parcialmente Validados:** 9,09%

A maior concentração de falhas está relacionada principalmente a:

* validação insuficiente de formulário
* tratamento inadequado de erros
* inconsistências de estado da aplicação
* problemas de responsividade
* ausência de sanitização de dados

---

# 🔎 Análise dos Resultados

Os cenários que falharam estão diretamente relacionados aos seguintes tipos de problemas:

---

# 🔹 Validação de dados

Foram identificadas falhas como:

* CPF inválido sendo aceito
* caracteres especiais sendo aceitos indevidamente
* ausência de limite de caracteres
* inconsistência na sanitização de entradas

Esses problemas indicam ausência de validação adequada tanto no frontend quanto possivelmente nas regras de negócio.

---

# 🔹 Tratamento de erros

Durante os testes foram identificados erros críticos de runtime no console.

### Erro de timeout

```javascript
Uncaught (in promise) Error: Timeout de comunicação com o servidor.
```

### Impacto

* possível quebra parcial do fluxo
* promessa rejeitada sem tratamento adequado
* experiência ruim para o usuário

### Possível causa

* ausência de tratamento robusto para promises rejeitadas
* timeout sem fallback visual

---

### Erro de objeto undefined

```javascript
Uncaught TypeError: can't access property "name", employees[idx] is undefined
```

### Impacto

* quebra de execução do JavaScript
* inconsistência na exclusão
* possível corrupção de estado da aplicação

### Possível causa

* tentativa de acessar item inexistente após alteração do array
* ausência de validação antes da exclusão

---

### Logs inconsistentes no console

Também foi identificado comportamento inconsistente durante exclusão:

```javascript
Colaborador não encontrado para exclusão. ID: 7
Excluído: Elisa Rodrigues
```

### Impacto

* inconsistência de estado
* logs conflitantes
* baixa confiabilidade operacional

---

# 🔹 Problemas de UX / Usabilidade

Foram identificados problemas relacionados à experiência do usuário:

* ausência de modal de confirmação na exclusão
* falta de mensagens claras em alguns cenários
* interface quebrando em telas menores
* inconsistências visuais na listagem

Esses problemas impactam diretamente a experiência de navegação e utilização da aplicação.

---

# 📊 Conclusão da Execução dos Testes

Os resultados obtidos indicam que o sistema apresenta funcionalidades principais operacionais, porém ainda possui problemas importantes relacionados à:

* robustez da aplicação
* integridade dos dados
* tratamento de erros
* experiência do usuário

As principais áreas que necessitam de correção são:

* validação de formulário
* sanitização de entradas
* tratamento de exceções JavaScript
* controle de estado da aplicação
* responsividade da interface

---

# 🔹 Observações por Sistema

---

# 1️⃣ Frontend – Sistema de Gestão de Colaboradores

### URL

[Sistema Bee Vale](https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/?utm_source=chatgpt.com)

---

# ⚠️ Problemas Encontrados

---

# 1. Sistema aceita CPF inválido

### Descrição

O sistema permite cadastro e edição utilizando CPF inválido.

### Exemplo

```txt
111
123
```

### Impacto

* dados inconsistentes
* baixa confiabilidade cadastral

### Recomendação

Implementar validação real de CPF.

---

# 2. Campos aceitam caracteres especiais inválidos

### Descrição

Campos de nome aceitam entradas como:

```txt
@@@###$$$
```

### Impacto

* dados inválidos
* possível quebra visual
* inconsistência de dados

### Recomendação

Adicionar sanitização e regex de validação.

---

# 3. Campos sem limite de caracteres

### Descrição

Os campos aceitam textos excessivamente longos.

### Impacto

* possível quebra de layout
* problemas futuros de armazenamento

### Recomendação

Definir limites máximos de caracteres.

---

# 4. Erro de timeout não tratado corretamente

### Descrição

Durante operações assíncronas foi identificado:

```javascript
Uncaught (in promise) Error: Timeout de comunicação com o servidor.
```

### Impacto

* fluxo interrompido
* promessa rejeitada sem tratamento

### Recomendação

Implementar tratamento global de promises rejeitadas.

---

# 5. Erro crítico durante exclusão

### Descrição

Erro identificado:

```javascript
employees[idx] is undefined
```

### Impacto

* quebra do JavaScript
* inconsistência na exclusão
* risco de corrupção do estado da aplicação

### Recomendação

Validar existência do item antes de acessar propriedades.

---

# 6. Logs inconsistentes durante exclusão

### Descrição

O sistema exibe simultaneamente:

```javascript
Colaborador não encontrado para exclusão
```

e logo após:

```javascript
Excluído: Elisa Rodrigues
```

### Impacto

* inconsistência operacional
* comportamento não confiável

### Recomendação

Revisar fluxo de exclusão e sincronização de estado.

---

# 7. Ausência de modal de confirmação na exclusão

### Descrição

A exclusão ocorre sem confirmação visual adequada.

### Impacto

* risco de exclusões acidentais
* UX inadequada

### Recomendação

Adicionar modal de confirmação antes da exclusão.

---

# 8. Responsividade quebrando em dispositivos móveis

### Descrição

A listagem apresenta quebra visual em resoluções menores.

### Impacto

* dificuldade de navegação mobile
* perda de usabilidade

### Recomendação

Ajustar layout responsivo da tabela/listagem.

---

# 9. Inconsistência visual e organizacional

### Descrição

Foram identificadas inconsistências de idioma e alinhamento visual.

### Impacto

* aparência pouco padronizada
* experiência inconsistente

### Recomendação

Padronizar UI e textos do sistema.

---

# 🔹 Problemas Técnicos Observados

Durante os testes também foram observados problemas relacionados ao gerenciamento de estado e tratamento de erros JavaScript.

Principais pontos identificados:

* promises rejeitadas sem tratamento
* inconsistência de arrays durante exclusão
* ausência de validação defensiva
* possíveis race conditions em operações rápidas

---

# 📊 Tabela de Prioridade de Correção e Severidade

| ID | Bug                                                            | Severidade | Prioridade | Impacto no Sistema                              | Possível Causa Raiz                         |
| -- | -------------------------------------------------------------- | ---------- | ---------- | ----------------------------------------------- | ------------------------------------------- |
| 1  | CPF inválido aceito                                            | 🔴 Alta    | 🔥 P1      | Dados inconsistentes                            | Ausência de validação                       |
| 2  | Caracteres especiais inválidos                                 | 🟠 Média   | P2         | Dados incorretos                                | Falta de sanitização                        |
| 3  | Campos sem limite de caracteres                                | 🟠 Média   | P2         | Quebra visual e inconsistência                  | Falta de limite nos inputs                  |
| 4  | Timeout sem tratamento                                         | 🔴 Crítica | 🔥 P1      | Fluxo quebrado                                  | Falta de tratamento async                   |
| 5  | `employees[idx]` undefined                                     | 🔴 Crítica | 🔥 P1      | Erro de runtime                                 | Controle inadequado de estado               |
| 6  | Logs inconsistentes na exclusão                                | 🟠 Média   | P2         | Baixa confiabilidade                            | Fluxo assíncrono inconsistente              |
| 7  | Ausência de modal de confirmação                               | 🟡 Baixa   | P3         | UX ruim                                         | Funcionalidade não implementada             |
| 8  | Responsividade quebrada                                        | 🟠 Média   | P2         | Problemas mobile                                | CSS responsivo insuficiente                 |
| 9  | Inconsistência visual                                          | 🟡 Baixa   | P3         | UX inconsistente                                | Falta de padronização UI                    |
| 10 | Nome excessivamente longo quebra layout                        | 🟠 Média   | P2         | Quebra visual da tela de edição                 | Falta de truncamento e controle CSS         |
| 11 | Campo CPF aceita letras                                        | 🔴 Alta    | 🔥 P1      | Integridade dos dados comprometida              | Ausência de máscara e validação numérica    |
| 12 | Campo telefone aceita caracteres inválidos                     | 🔴 Alta    | 🔥 P1      | Dados inconsistentes                            | Falta de validação e sanitização            |
| 13 | Campo salário aceita texto                                     | 🔴 Alta    | 🔥 P1      | Possíveis falhas em cálculos e relatórios       | Campo sem validação numérica                |
| 14 | Sidebar/menu lateral desalinhado em telas menores              | 🟠 Média   | P2         | Problemas de navegação e responsividade         | CSS responsivo inadequado                   |
| 15 | Header desalinhado com menu hamburguer                         | 🟡 Baixa   | P3         | Inconsistência visual                           | Problema de alinhamento/layout              |
| 16 | Ícones desalinhados na seção “Atividades Recentes”             | 🟡 Baixa   | P3         | Aparência não profissional                      | Falta de padronização visual                |
| 17 | Inputs permitem texto extremamente longo                       | 🟠 Média   | P2         | Quebra visual e possível impacto de performance | Ausência de limite de caracteres            |
| 18 | Falta de validação visual em campos inválidos                  | 🟠 Média   | P2         | Usuário não entende erros corretamente          | Feedback visual insuficiente                |
| 19 | Exclusão permite estado inconsistente após múltiplos cliques   | 🔴 Alta    | 🔥 P1      | Inconsistência da listagem e runtime errors     | Controle inadequado de concorrência         |
| 20 | Login permite autenticação apenas com “admin” e senha vazia    | 🔴 Crítica | 🔥 P1      | Falha grave de autenticação                     | Validação de login inadequada               |
| 21 | Credenciais expostas na tela inicial (`admin/admin123`)        | 🔴 Alta    | 🔥 P1      | Exposição de credenciais e falha de segurança   | Uso de credenciais hardcoded na interface   |
| 22 | Dashboard acessível sem autenticação adequada                  | 🔴 Crítica | 🔥 P1      | Acesso não autorizado ao sistema                | Falta de proteção de rotas/autenticação     |
| 23 | Possível acesso direto via URL sem login                       | 🔴 Crítica | 🔥 P1      | Vulnerabilidade de segurança                    | Middleware/guardas de rota ausentes         |
| 24 | Mistura de idiomas na interface (“Professional Info”)          | 🟡 Baixa   | P3         | UX inconsistente                                | Falta de padronização de i18n               |
| 25 | Ausência de confirmação antes de excluir usuário               | 🟠 Média   | P2         | Exclusões acidentais                            | Fluxo de confirmação não implementado       |
| 26 | Textarea sem limite quebra o layout do formulário              | 🟠 Média   | P2         | Quebra visual da UI                             | CSS e limite de caracteres ausentes         |
| 27 | Exclusão em cascata remove usuários indevidamente              | 🔴 Crítica | 🔥 P1      | Perda incorreta de dados                        | Controle incorreto de índice/estado         |
| 28 | Exclusão múltipla ocorre de forma inconsistente                | 🔴 Alta    | 🔥 P1      | Integridade da listagem comprometida            | Race condition / estado assíncrono          |
| 29 | Sistema exibe conteúdo parcialmente autenticado antes do login | 🔴 Alta    | 🔥 P1      | Exposição indevida de informações               | Renderização sem validação de sessão        |
| 30 | Campo de data aceita datas absurdas (ex: 2174)                 | 🟠 Média   | P2         | Dados incoerentes e inconsistentes              | Ausência de validação de intervalo de datas |
| 31 | Atualizar página realiza logout completo do usuário            | 🟠 Média   | P2         | Má experiência do usuário e perda de sessão     | Persistência de autenticação inadequada     |
| 32 | Dados sensíveis armazenados diretamente no Local Storage       | 🔴 Alta    | 🔥 P1      | Risco de exposição de informações               | Armazenamento inseguro no frontend          |


---

# 🔎 Principais Causas Raiz Identificadas

---

## 1️⃣ Falta de validação de dados

Problemas relacionados:

* CPF inválido
* caracteres especiais
* campos sem limite

### Possível causa

* ausência de validação frontend/backend
* regras de negócio insuficientes

---

## 2️⃣ Problemas de tratamento assíncrono

Problemas relacionados:

* timeout
* promises rejeitadas
* exclusão inconsistente

### Possível causa

* ausência de try/catch
* falta de tratamento defensivo
* gerenciamento incorreto de estado

---

## 3️⃣ Problemas de UX / Usabilidade

Problemas relacionados:

* ausência de modal
* responsividade
* feedback inconsistente

### Possível causa

* ausência de validação UX
* falta de testes responsivos

---

## 4️⃣ Problemas de UI / CSS

Problemas relacionados:

* quebra no mobile
* inconsistência visual

### Possível causa

* CSS não responsivo
* ausência de padronização visual

---

# 🎯 Conclusão Técnica

Os bugs identificados indicam necessidade de melhorias principalmente em:

---

## 🔧 Frontend

* validação de formulários
* sanitização de entradas
* tratamento de erros JavaScript
* gerenciamento de estado
* responsividade

---

## 💻 Tratamento de Erros

* promises rejeitadas
* validações defensivas
* mensagens consistentes
* tratamento de timeout

---

## 🎨 UX/UI

* modal de confirmação
* feedback visual
* consistência visual
* adaptação mobile

---

# 🔹 Conclusão

Os testes manuais identificaram diversos problemas importantes relacionados à:

* estabilidade da aplicação
* integridade dos dados
* tratamento de erros
* experiência do usuário

Embora os fluxos principais estejam parcialmente funcionais, o sistema ainda necessita de melhorias para atingir maior confiabilidade e robustez.

As principais prioridades de correção devem focar em:

* validação de dados
* tratamento de exceções
* controle de estado
* melhorias de UX/UI

---

### Observação final

> “Qualidade não é apenas encontrar bugs.
> É garantir confiabilidade, previsibilidade e boa experiência para o usuário final.”

