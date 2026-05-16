# Registro de Bugs

# 🔹 Informações Gerais

* **Projeto:** Sistema SysColaborador
* **Data do Teste:** 15/05/2026
* **Testador:** Miguel Luis
* **Tipo de Teste:** Testes Funcionais, Exploratórios, UX, Segurança e Validação de Dados

---

# 🔹 Ambiente de Teste

| Item                   | Descrição                      |
| ---------------------- | ------------------------------ |
| Aplicação              | Sistema SysColaborador         |
| Ambiente               | Produção                       |
| Navegador              | Firefox 148 64 bits            |
| Sistema Operacional    | Windows 11                     |
| Ferramentas utilizadas | DevTools, Console do navegador |

---

# Observação baseada nos princípios de teste (CTFL)

De acordo com os princípios de teste definidos no **ISTQB Certified Tester Foundation Level (CTFL)**, é importante destacar 3 conceitos relevantes para a análise dos resultados obtidos:

### 1. Testes mostram a presença de defeitos, não a sua ausência

Durante a execução dos testes foram identificados diversos bugs no sistema. Entretanto, isso não significa que todos os defeitos existentes foram encontrados. Os testes apenas evidenciam problemas que foram detectados nos cenários executados.

### 2. Teste exaustivo é impossível

Não é possível testar todas as combinações de entradas, estados e fluxos de um sistema. Por isso, mesmo após a execução dos testes documentados neste relatório, ainda podem existir defeitos não identificados.

### 3. Falácia da ausência de erros

Mesmo que todos os bugs encontrados sejam corrigidos, isso não garante automaticamente que o sistema esteja completamente livre de problemas ou que atenda perfeitamente às necessidades do usuário. A qualidade também depende da adequação do sistema aos requisitos e às regras de negócio.

Além disso, durante a análise foram identificados potenciais riscos relacionados a **duplicação de dados**, inconsistência de informações, vulnerabilidades de segurança e registros inválidos. Em alguns casos, esses problemas estão diretamente relacionados à ausência de validações no frontend e no backend.

Por exemplo, a implementação correta de validações de campos obrigatórios, validação numérica, validação de datas e tratamento correto de autenticação tende a corrigir múltiplos problemas simultaneamente. Ao impedir o envio de dados inválidos e proteger corretamente as rotas do sistema, reduz-se a possibilidade de inconsistências, acessos indevidos e falhas críticas de integridade.

Dessa forma, a correção de determinadas validações pode resolver não apenas um bug isolado, mas também evitar efeitos colaterais como duplicação de dados, inconsistência de registros, falhas de segurança e problemas futuros em relatórios e regras de negócio.

---

# 🐞 Bug 1 — CPF inválido é aceito no cadastro

### Severidade

🔴 Alta

### Passos para reproduzir

1. Acessar o formulário de cadastro/edição
2. Informar um CPF inválido
3. Salvar o formulário

### Resultado atual

O sistema aceita o CPF inválido sem qualquer validação.

### Resultado esperado

O sistema deve validar CPF inválido e impedir o envio.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1-swHGI2332vbwv9HmPyoUktE9FuN0ZJz/view?usp=sharing)*

### Possíveis melhorias no sistema

* Implementar validação de CPF
* Aplicar máscara no campo
* Exibir mensagens de erro claras

---

# 🐞 Bug 2 — Campo CPF aceita letras

### Severidade

🔴 Alta

### Passos para reproduzir

1. Acessar o formulário
2. Inserir letras no campo CPF
3. Salvar o cadastro

### Resultado atual

O sistema aceita caracteres alfabéticos no CPF.

### Resultado esperado

O campo deve aceitar apenas números válidos.

### Evidências

[*(evidência aqui)*](https://drive.google.com/file/d/1-swHGI2332vbwv9HmPyoUktE9FuN0ZJz/view?usp=sharing)

### Possíveis melhorias no sistema

* Implementar máscara numérica
* Sanitizar entrada do usuário
* Validar caracteres permitidos

---

# 🐞 Bug 3 — Campo telefone aceita caracteres inválidos

### Severidade

🔴 Alta

### Passos para reproduzir

1. Acessar o formulário
2. Inserir letras e símbolos no telefone
3. Salvar cadastro

### Resultado atual

O sistema aceita valores inválidos no telefone.

### Resultado esperado

O sistema deve aceitar apenas números válidos de telefone.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1-swHGI2332vbwv9HmPyoUktE9FuN0ZJz/view?usp=sharing)*

### Possíveis melhorias no sistema

* Aplicar máscara telefônica
* Validar formato do telefone
* Sanitizar caracteres especiais

---

# 🐞 Bug 4 — Campo salário aceita texto

### Severidade

🔴 Alta

### Passos para reproduzir

1. Acessar o formulário
2. Inserir texto no campo salário
3. Salvar formulário

### Resultado atual

O sistema aceita valores textuais no salário.

### Resultado esperado

O campo deve aceitar apenas valores numéricos válidos.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1-swHGI2332vbwv9HmPyoUktE9FuN0ZJz/view?usp=sharing)*

### Possíveis melhorias no sistema

* Implementar validação numérica
* Definir tipo numérico no input
* Aplicar máscara monetária

---

# 🐞 Bug 5 — Inputs permitem texto extremamente longo

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir texto extremamente longo nos campos
2. Salvar formulário

### Resultado atual

O sistema aceita textos excessivos e quebra o layout.

### Resultado esperado

Os campos devem possuir limite de caracteres.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1JRf0TTFwn73rbdgW3hmW7tsg87FKgxFX/view?usp=sharing)*

### Possíveis melhorias no sistema

* Definir limite máximo de caracteres
* Implementar truncamento visual
* Adicionar contador de caracteres

---

# 🐞 Bug 6 — Nome excessivamente longo quebra layout

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir nome extremamente longo
2. Abrir tela de edição

### Resultado atual

O layout da tela quebra visualmente.

### Resultado esperado

O sistema deve manter responsividade e truncamento visual.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1JRf0TTFwn73rbdgW3hmW7tsg87FKgxFX/view?usp=sharing)*

### Possíveis melhorias no sistema

* Utilizar ellipsis/text-overflow
* Limitar caracteres
* Melhorar CSS responsivo

---

# 🐞 Bug 7 — Textarea sem limite quebra o layout

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir texto muito grande no textarea
2. Observar a tela

### Resultado atual

O textarea cresce excessivamente e quebra o formulário.

### Resultado esperado

O componente deve possuir limite visual e scroll interno.


### Possíveis melhorias no sistema

* Definir altura máxima
* Adicionar scroll interno
* Limitar quantidade de caracteres

---

# 🐞 Bug 8 — Campo de data aceita datas absurdas (ex: 2174)

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir data muito distante no futuro
2. Salvar formulário

### Resultado atual

O sistema aceita datas incoerentes.

### Resultado esperado

O sistema deve validar intervalos aceitáveis de datas.

### Evidências

*[( evidência aqui)](https://drive.google.com/file/d/1m0C-Xqeq4xJhCSNw9a-Wg1xdFnVhBHSF/view?usp=sharing)*

### Possíveis melhorias no sistema

* Validar intervalo de datas
* Definir datas máximas e mínimas
* Aplicar regras de negócio

---

# 🐞 Bug 9 — Falta de validação visual em campos inválidos

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir dados inválidos
2. Tentar salvar formulário

### Resultado atual

O sistema não informa claramente os erros.

### Resultado esperado

Campos inválidos devem possuir feedback visual e mensagens claras.

### Possíveis melhorias no sistema

* Destacar campos inválidos
* Adicionar mensagens de erro
* Melhorar UX de validação

---

# 🐞 Bug 10 — Login permite autenticação apenas com “admin” e senha vazia

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Acessar tela de login
2. Inserir apenas “admin”
3. Deixar senha vazia
4. Realizar login

### Resultado atual

O sistema autentica o usuário mesmo sem senha.

### Resultado esperado

O sistema deve bloquear autenticação sem senha válida.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Validar credenciais obrigatórias
* Impedir autenticação com campos vazios
* Implementar autenticação segura

---

# 🐞 Bug 11 — Credenciais expostas na tela inicial (`admin/admin123`)

### Severidade

🔴 Alta

### Passos para reproduzir

1. Abrir tela inicial/login
2. Observar informações exibidas

### Resultado atual

O sistema expõe credenciais diretamente na interface.

### Resultado esperado

Credenciais não devem ser exibidas ao usuário.

### Possíveis melhorias no sistema

* Remover credenciais hardcoded
* Utilizar documentação separada para ambiente de testes
* Implementar variáveis de ambiente

---

# 🐞 Bug 12 — Dashboard acessível sem autenticação adequada

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Tentar acessar URL protegida diretamente
2. Abrir `/dashboard`

### Resultado atual

O sistema permite acesso parcial/total sem login válido.

### Resultado esperado

Rotas protegidas devem exigir autenticação.

### Possíveis melhorias no sistema

* Implementar guards de rota
* Validar sessão/token
* Redirecionar usuário não autenticado

---

# 🐞 Bug 13 — Sistema exibe conteúdo parcialmente autenticado antes do login

### Severidade

🔴 Alta

### Passos para reproduzir

1. Abrir aplicação
2. Observar carregamento inicial

### Resultado atual

Elementos internos do sistema aparecem antes da validação de sessão.

### Resultado esperado

O conteúdo protegido deve ser renderizado apenas após autenticação válida.

### Possíveis melhorias no sistema

* Validar autenticação antes da renderização
* Implementar loading seguro
* Melhorar proteção de sessão

---

# 🐞 Bug 14 — Atualizar página realiza logout completo do usuário

### Severidade

🟠 Média

### Passos para reproduzir

1. Realizar login
2. Atualizar página (F5)

### Resultado atual

O usuário perde sessão e é deslogado.

### Resultado esperado

A sessão deve permanecer ativa após refresh.

### Possíveis melhorias no sistema

* Persistir autenticação corretamente
* Implementar refresh de sessão
* Melhorar gerenciamento de estado

---

# 🐞 Bug 15 — Dados sensíveis armazenados diretamente no Local Storage

### Severidade

🔴 Alta

### Passos para reproduzir

1. Abrir DevTools
2. Acessar Local Storage
3. Verificar dados armazenados

### Resultado atual

Informações sensíveis ficam expostas no navegador.

### Resultado esperado

Dados críticos não devem ficar armazenados diretamente no Local Storage.

### Possíveis melhorias no sistema

* Evitar armazenamento sensível no frontend
* Utilizar tokens seguros
* Aplicar melhores práticas de autenticação

---

# 🐞 Bug 16 — Exclusão em cascata remove usuários indevidamente

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Acessar listagem de usuários
2. Excluir um usuário
3. Observar listagem

### Resultado atual

Outros usuários também são removidos indevidamente.

### Resultado esperado

Somente o usuário selecionado deve ser excluído.

### Evidências

*[(evidência aqui)](https://drive.google.com/file/d/1IAs6CCidworCc8wISB9MrVyRhXFVrrnN/view?usp=sharing)*

### Possíveis melhorias no sistema

* Corrigir controle de índice/estado
* Validar operações assíncronas
* Implementar testes de regressão

---

# 🐞 Bug 17 — `employees[idx]` undefined ao excluir registros

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Excluir usuários rapidamente
2. Observar console

### Resultado atual

Erro de runtime ocorre durante exclusão.

### Resultado esperado

O sistema deve tratar corretamente estados inexistentes.

### Possíveis melhorias no sistema

* Validar índice antes de acessar array
* Melhorar controle de estado
* Implementar tratamento de exceções

---

# 🐞 Bug 18 — Exclusão múltipla ocorre de forma inconsistente

### Severidade

🔴 Alta

### Passos para reproduzir

1. Clicar múltiplas vezes em excluir
2. Observar comportamento da lista

### Resultado atual

A lista entra em estado inconsistente.

### Resultado esperado

A exclusão deve ocorrer apenas uma vez por ação.

### Evidências

*[ evidência aqui)](https://drive.google.com/file/d/1IAs6CCidworCc8wISB9MrVyRhXFVrrnN/view?usp=sharing)*

### Possíveis melhorias no sistema

* Bloquear ações concorrentes
* Debounce/throttle em botões
* Melhorar sincronização de estado

---

# 🐞 Bug 19 — Ausência de confirmação antes de excluir usuário

### Severidade

🟠 Média

### Passos para reproduzir

1. Clicar em excluir usuário

### Resultado atual

A exclusão ocorre imediatamente.

### Resultado esperado

O sistema deve solicitar confirmação antes da exclusão

### Possíveis melhorias no sistema

* Implementar modal de confirmação
* Melhorar UX de ações destrutivas
* Exibir alertas preventivos

---

# 🐞 Bug 20 — Responsividade quebrada em telas menores

### Severidade

🟠 Média

### Passos para reproduzir

1. Reduzir tamanho da tela
2. Navegar pelo sistema

### Resultado atual

Componentes ficam desalinhados e quebram layout.

### Resultado esperado

O sistema deve adaptar corretamente em diferentes resoluções.

### Possíveis melhorias no sistema

* Melhorar media queries
* Revisar grid/layout responsivo
* Ajustar componentes mobile

---

# 🐞 Bug 21 — Mistura de idiomas na interface (“Professional Info”)

### Severidade

🟡 Baixa

### Passos para reproduzir

1. Navegar pela aplicação
2. Observar títulos e labels

### Resultado atual

Existem elementos em português e inglês misturados.

### Resultado esperado

O sistema deve possuir padronização de idioma.

### Possíveis melhorias no sistema

* Padronizar i18n
* Revisar textos da interface
* Implementar internacionalização consistente

---
# 🐞 Bug 22 — Dashboard acessível sem autenticação adequada

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Abrir a aplicação
2. Tentar acessar diretamente a rota `/dashboard`
3. Não realizar login

### Resultado atual

O sistema permite acesso ao dashboard sem autenticação válida.

### Resultado esperado

O sistema deve bloquear acesso a rotas protegidas sem autenticação.

### Possíveis melhorias no sistema

* Implementar proteção de rotas
* Validar autenticação antes da renderização
* Redirecionar usuários não autenticados

---

# 🐞 Bug 23 — Possível acesso direto via URL sem login

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Copiar URL de páginas internas
2. Abrir diretamente no navegador sem login
3. Observar comportamento da aplicação

### Resultado atual

O sistema permite acesso direto a páginas protegidas.

### Resultado esperado

As rotas devem validar sessão/token antes do carregamento.

### Possíveis melhorias no sistema

* Implementar middleware/guards de rota
* Validar token de autenticação
* Bloquear acesso não autorizado

---

# 🐞 Bug 24 — Mistura de idiomas na interface (“Professional Info”)

### Severidade

🟡 Baixa

### Passos para reproduzir

1. Navegar pelo sistema
2. Observar títulos, labels e seções

### Resultado atual

O sistema apresenta mistura de português e inglês na interface.

### Resultado esperado

Toda a interface deve seguir um padrão único de idioma.

### Possíveis melhorias no sistema

* Padronizar internacionalização (i18n)
* Revisar labels e componentes
* Centralizar textos da aplicação

---

# 🐞 Bug 25 — Ausência de confirmação antes de excluir usuário

### Severidade

🟠 Média

### Passos para reproduzir

1. Acessar listagem de usuários
2. Clicar em excluir

### Resultado atual

O usuário é excluído imediatamente sem confirmação.

### Resultado esperado

O sistema deve solicitar confirmação antes da exclusão.

### Possíveis melhorias no sistema

* Implementar modal de confirmação
* Adicionar alerta para ações destrutivas
* Melhorar UX de exclusão

---

# 🐞 Bug 26 — Textarea sem limite quebra o layout do formulário

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir texto extremamente grande no textarea
2. Observar o comportamento da interface

### Resultado atual

O textarea cresce indefinidamente e quebra o layout da tela.

### Resultado esperado

O campo deve possuir limite visual e controle de tamanho.

### Possíveis melhorias no sistema

* Definir altura máxima
* Adicionar scroll interno
* Limitar quantidade de caracteres

---

# 🐞 Bug 27 — Exclusão em cascata remove usuários indevidamente

### Severidade

🔴 Crítica

### Passos para reproduzir

1. Acessar listagem de usuários
2. Excluir um usuário
3. Verificar lista após exclusão

### Resultado atual

Múltiplos usuários são removidos indevidamente.

### Resultado esperado

Somente o usuário selecionado deve ser excluído.
### Possíveis melhorias no sistema

* Revisar controle de índices
* Corrigir gerenciamento de estado
* Implementar testes de regressão

---

# 🐞 Bug 28 — Exclusão múltipla ocorre de forma inconsistente

### Severidade

🔴 Alta

### Passos para reproduzir

1. Clicar rapidamente várias vezes no botão excluir
2. Observar comportamento da listagem

### Resultado atual

A listagem entra em estado inconsistente.

### Resultado esperado

A exclusão deve ocorrer apenas uma vez por ação.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Implementar debounce/throttle
* Bloquear botão durante operação
* Melhorar controle assíncrono

---

# 🐞 Bug 29 — Sistema exibe conteúdo parcialmente autenticado antes do login

### Severidade

🔴 Alta

### Passos para reproduzir

1. Abrir aplicação
2. Observar carregamento inicial da interface

### Resultado atual

Partes internas do sistema aparecem antes da autenticação.

### Resultado esperado

Conteúdo protegido deve aparecer apenas após validação da sessão.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Validar sessão antes da renderização
* Implementar loading seguro
* Melhorar proteção de autenticação

---

# 🐞 Bug 30 — Campo de data aceita datas absurdas (ex: 2174)

### Severidade

🟠 Média

### Passos para reproduzir

1. Inserir data muito distante no futuro
2. Salvar formulário

### Resultado atual

O sistema aceita datas incoerentes.

### Resultado esperado

O sistema deve validar intervalo permitido de datas.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Definir limite mínimo/máximo de datas
* Aplicar validação de regra de negócio
* Exibir mensagens de erro

---

# 🐞 Bug 31 — Atualizar página realiza logout completo do usuário

### Severidade

🟠 Média

### Passos para reproduzir

1. Realizar login
2. Atualizar página (F5)

### Resultado atual

O usuário perde a sessão e precisa autenticar novamente.

### Resultado esperado

A sessão deve persistir após atualização da página.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Persistir autenticação corretamente
* Implementar refresh token/sessão
* Melhorar gerenciamento de estado

---

# 🐞 Bug 32 — Dados sensíveis armazenados diretamente no Local Storage

### Severidade

🔴 Alta

### Passos para reproduzir

1. Abrir DevTools do navegador
2. Acessar aba Application/Local Storage
3. Verificar dados armazenados

### Resultado atual

Dados sensíveis ficam expostos no Local Storage.

### Resultado esperado

Informações críticas não devem ficar expostas no frontend.

### Evidências

*(Adicionar evidência aqui)*

### Possíveis melhorias no sistema

* Evitar armazenamento sensível no Local Storage
* Utilizar cookies HttpOnly/token seguro
* Aplicar boas práticas de autenticação


---

# 📊 Tabela de Prioridade de Correção e Severidade

| ID | Bug                                                                     | Severidade | Prioridade | Impacto no Sistema                              | Possível Causa Raiz                         |
| -- | ----------------------------------------------------------------------- | ---------- | ---------- | ----------------------------------------------- | ------------------------------------------- |
| 1  | CPF inválido aceito                                                     | 🔴 Alta    | 🔥 P1      | Dados inconsistentes                            | Ausência de validação                       |
| 2  | Campo CPF aceita letras                                                 | 🔴 Alta    | 🔥 P1      | Integridade dos dados comprometida              | Ausência de máscara e validação numérica    |
| 3  | Campo telefone aceita caracteres inválidos                              | 🔴 Alta    | 🔥 P1      | Dados inconsistentes                            | Falta de validação e sanitização            |
| 4  | Campo salário aceita texto                                              | 🔴 Alta    | 🔥 P1      | Possíveis falhas em cálculos e relatórios       | Campo sem validação numérica                |
| 5  | Inputs permitem texto extremamente longo                                | 🟠 Média   | P2         | Quebra visual e possível impacto de performance | Ausência de limite de caracteres            |
| 6  | Nome excessivamente longo quebra layout                                 | 🟠 Média   | P2         | Quebra visual da tela de edição                 | Falta de truncamento e controle CSS         |
| 7  | Textarea sem limite quebra layout                                       | 🟠 Média   | P2         | Quebra visual da UI                             | CSS e limite de caracteres ausentes         |
| 8  | Campo de data aceita datas absurdas (ex: 2174)                          | 🟠 Média   | P2         | Dados incoerentes e inconsistentes              | Ausência de validação de intervalo de datas |
| 9  | Falta de validação visual em campos inválidos                           | 🟠 Média   | P2         | Usuário não entende erros corretamente          | Feedback visual insuficiente                |
| 10 | Login permite autenticação apenas com “admin” e senha vazia             | 🔴 Crítica | 🔥 P1      | Falha grave de autenticação                     | Validação de login inadequada               |
| 11 | Credenciais expostas na tela inicial (`admin/admin123`)                 | 🔴 Alta    | 🔥 P1      | Exposição de credenciais e falha de segurança   | Uso de credenciais hardcoded na interface   |
| 12 | Dashboard acessível sem autenticação adequada                           | 🔴 Crítica | 🔥 P1      | Acesso não autorizado ao sistema                | Falta de proteção de rotas/autenticação     |
| 13 | Sistema exibe conteúdo parcialmente autenticado antes do login          | 🔴 Alta    | 🔥 P1      | Exposição indevida de informações               | Renderização sem validação de sessão        |
| 14 | Atualizar página realiza logout completo do usuário                     | 🟠 Média   | P2         | Má experiência do usuário e perda de sessão     | Persistência de autenticação inadequada     |
| 15 | Dados sensíveis armazenados diretamente no Local Storage                | 🔴 Alta    | 🔥 P1      | Risco de exposição de informações               | Armazenamento inseguro no frontend          |
| 16 | Exclusão em cascata remove usuários indevidamente                       | 🔴 Crítica | 🔥 P1      | Perda incorreta de dados                        | Controle incorreto de índice/estado         |
| 17 | `employees[idx]` undefined                                              | 🔴 Crítica | 🔥 P1      | Erro de runtime                                 | Controle inadequado de estado               |
| 18 | Exclusão múltipla ocorre de forma inconsistente                         | 🔴 Alta    | 🔥 P1      | Integridade da listagem comprometida            | Race condition / estado assíncrono          |
| 19 | Ausência de confirmação antes de excluir usuário                        | 🟠 Média   | P2         | Exclusões acidentais                            | Fluxo de confirmação não implementado       |
| 20 | Responsividade quebrada em telas menores                                | 🟠 Média   | P2         | Problemas mobile e quebra de layout             | CSS responsivo insuficiente                 |
| 21 | Mistura de idiomas na interface (“Professional Info”)                   | 🟡 Baixa   | P3         | UX inconsistente                                | Falta de padronização de i18n               |
| 22 | Possível acesso direto via URL sem login                                | 🔴 Crítica | 🔥 P1      | Vulnerabilidade de segurança                    | Middleware/guardas de rota ausentes         |
| 23 | Logs inconsistentes na exclusão                                         | 🟠 Média   | P2         | Baixa confiabilidade                            | Fluxo assíncrono inconsistente              |
| 24 | Timeout sem tratamento                                                  | 🔴 Crítica | 🔥 P1      | Fluxo quebrado                                  | Falta de tratamento async                   |
| 25 | Caracteres especiais inválidos são aceitos                              | 🟠 Média   | P2         | Dados incorretos                                | Falta de sanitização                        |
| 26 | Sidebar/menu lateral desalinhado em telas menores                       | 🟠 Média   | P2         | Problemas de navegação e responsividade         | CSS responsivo inadequado                   |
| 27 | Header desalinhado com menu hamburguer                                  | 🟡 Baixa   | P3         | Inconsistência visual                           | Problema de alinhamento/layout              |
| 28 | Ícones desalinhados na seção “Atividades Recentes”                      | 🟡 Baixa   | P3         | Aparência não profissional                      | Falta de padronização visual                |
| 29 | Ausência de modal de confirmação                                        | 🟡 Baixa   | P3         | UX ruim                                         | Funcionalidade não implementada             |
| 30 | Campos sem limite de caracteres                                         | 🟠 Média   | P2         | Quebra visual e inconsistência                  | Falta de limite nos inputs                  |
| 31 | Inconsistência visual geral                                             | 🟡 Baixa   | P3         | UX inconsistente                                | Falta de padronização UI                    |
| 32 | Sistema permite estado inconsistente após múltiplos cliques em exclusão | 🔴 Alta    | 🔥 P1      | Runtime errors e inconsistência da listagem     | Controle inadequado de concorrência         |

---

# 📊 Resumo Geral por Severidade

| Severidade | Quantidade |
| ---------- | ---------- |
| 🔴 Crítica | 6          |
| 🔴 Alta    | 10         |
| 🟠 Média   | 12         |
| 🟡 Baixa   | 4          |

---

# 📌 Principais Pontos Críticos Encontrados

### 🔐 Segurança

Os problemas mais críticos identificados estão relacionados à autenticação e proteção de sessão:

* Login sem senha válida
* Dashboard acessível sem autenticação
* Acesso direto via URL
* Credenciais expostas na interface
* Dados sensíveis no Local Storage

Esses problemas representam riscos reais de acesso indevido e exposição de informações.

---

### 🗂️ Integridade de Dados

Foram encontrados diversos problemas relacionados à ausência de validações:

* CPF inválido
* Telefone inválido
* Campo salário aceitando texto
* Datas incoerentes
* Campos sem limite de caracteres

Esses problemas podem gerar inconsistência de dados e impactar regras futuras do sistema.

---

### ⚠️ Exclusão de Usuários

A funcionalidade de exclusão apresentou múltiplos comportamentos críticos:

* Exclusão em cascata
* Exclusão inconsistente
* Runtime errors (`employees[idx]`)
* Falta de confirmação

Esses bugs representam alto risco de perda incorreta de dados.

---

### 🎨 UX e Responsividade

Também foram identificados problemas relacionados à experiência do usuário:

* Layout quebrando em telas menores
* Mistura de idiomas
* Falta de feedback visual
* Problemas visuais em componentes

Embora menos críticos tecnicamente, impactam diretamente a usabilidade e percepção de qualidade do sistema.
