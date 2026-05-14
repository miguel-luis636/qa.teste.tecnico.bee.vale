# 🧪 Plano de Testes – Sistema de Gestão de Colaboradores (Bee Vale & Rambly)

## 📌 1. Identificação

* **Projeto**: Sistema de Gestão de Colaboradores – Desafio QA Bee Vale & Rambly

* **Aplicação**: Módulo de Gestão de Colaboradores

* **Ambiente de Testes**: Aplicação Web hospedada em Vercel

* **URL da aplicação**:
  [https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/](https://project-wbu6c-pjhiekqzm-rickkque-5280s-projects.vercel.app/)

* **Tipos de Teste**:

  * Testes Manuais Funcionais
  * Testes Exploratórios
  * Testes Negativos
  * Testes de CRUD
  * Testes de Validação de Formulário
  * Testes de Tratamento de Erros
  * Testes de Usabilidade
  * Testes de Interface Responsiva

* **Data de Atualização**: 14/05/2026

* **Responsável**: Miguel Luis de Ataíde Ferreira

---

# 🎯 2. Objetivo

Garantir a qualidade funcional do sistema de gestão de colaboradores, verificando se os fluxos principais da aplicação apresentam comportamento consistente, confiável e aderente ao esperado.

Os testes possuem como foco principal:

* Validar o fluxo de cadastro de colaboradores
* Verificar o comportamento da listagem de colaboradores
* Avaliar o fluxo de edição de registros
* Validar o fluxo de exclusão de colaboradores
* Verificar validações dos campos do formulário
* Identificar falhas de tratamento de erro
* Avaliar possíveis inconsistências de estado da aplicação
* Identificar problemas de experiência do usuário e usabilidade

A execução dos testes busca simular cenários reais de uso da aplicação, validando tanto o funcionamento esperado quanto possíveis comportamentos inesperados do sistema.

---

# 🧠 3. Abordagem de Teste

A estratégia de testes adotada neste desafio foi baseada inicialmente em uma exploração funcional da aplicação, seguida da definição de cenários estruturados de validação.

A abordagem considera os seguintes pontos:

---

## 🔹 Exploração Inicial do Sistema

Inicialmente foi realizada uma exploração da aplicação para compreender:

* Fluxos principais do sistema
* Estrutura das funcionalidades CRUD
* Comportamento da interface
* Estrutura do formulário de cadastro
* Fluxo de navegação entre páginas
* Possíveis pontos críticos da aplicação

Essa etapa permitiu identificar os fluxos prioritários e áreas de maior risco funcional.

---

## 🔹 Testes Baseados nos Fluxos Principais

Os testes foram priorizados considerando os fluxos mais críticos da aplicação:

* Cadastro de colaboradores
* Edição de colaboradores
* Exclusão de colaboradores
* Exibição da listagem
* Atualização do dashboard

Esses fluxos representam as funcionalidades centrais do sistema e possuem maior impacto para o usuário final.

---

## 🔹 Testes Negativos

Foram criados cenários para validar como o sistema se comporta diante de usos incorretos ou inesperados.

Exemplos:

* Campos obrigatórios vazios
* Inserção de dados inválidos
* Inserção de caracteres especiais
* Tentativas de exclusão inválidas
* Manipulação de IDs inexistentes
* Timeout de operações assíncronas

Esses testes ajudam a identificar falhas de validação, inconsistências de estado e ausência de tratamento de erros.

---

## 🔹 Testes Exploratórios

Durante a execução também foram realizadas sessões de testes exploratórios com foco em:

* Identificar comportamentos inesperados
* Validar consistência visual
* Avaliar experiência do usuário
* Detectar falhas não previstas inicialmente
* Verificar erros apresentados no console da aplicação

Essa abordagem permitiu identificar problemas relacionados a estado interno da aplicação e tratamento inadequado de exceções.

---

# 🧩 4. Escopo

## ✅ Incluído no escopo

* Cadastro de colaboradores
* Edição de colaboradores
* Exclusão de colaboradores
* Listagem de registros
* Dashboard inicial
* Validação dos campos do formulário
* Fluxos de CRUD
* Tratamento de erros de frontend
* Comportamento da aplicação em cenários negativos
* Responsividade básica da interface
* Usabilidade da aplicação
* Verificação de logs e erros no console

---

## ❌ Fora do escopo

* Testes de carga e performance
* Testes de segurança avançados
* Testes automatizados
* Testes de integração backend
* Testes de infraestrutura
* Testes de APIs externas

---

# ⚖️ 5. Ferramentas Utilizadas

## Navegadores Web

Os testes foram executados utilizando navegadores modernos em suas versões estáveis mais recentes:

* Google Chrome
* Mozilla Firefox
* Microsoft Edge

## Sistema Operacional

* Windows 11

---

## Ferramentas de apoio

* DevTools do navegador

  * Console
  * Network
  * Application Storage
  * Inspeção de elementos

* Google Sheets

* Google Drive

* GitHub

* Ferramentas de captura de tela

---

# 🧪 6. Técnicas de Teste Utilizadas

---

## 🔹 Testes Funcionais

Validação dos fluxos principais da aplicação:

* Cadastro de colaborador
* Atualização de colaborador
* Exclusão de colaborador
* Exibição correta da listagem

Esses testes garantem o funcionamento adequado das funcionalidades centrais do sistema.

---

## 🔹 Testes Negativos

Cenários executados para validar o comportamento da aplicação diante de entradas inválidas ou ações incorretas.

Exemplos:

* Campos vazios
* Dados inválidos
* IDs inexistentes
* Exclusões inválidas
* Timeout de operações

---

## 🔹 Testes Exploratórios

Sessões livres de exploração para identificar:

* Bugs inesperados
* Problemas de UX
* Inconsistência visual
* Problemas de estado da aplicação
* Erros de runtime

---

## 🔹 Testes de Tratamento de Erro

Foram realizados testes específicos para avaliar:

* Tratamento de Promises rejeitadas
* Mensagens de erro
* Comportamento do sistema após falhas
* Logs exibidos no console

---

## 🔹 Testes de Usabilidade

Validação de:

* Clareza da interface
* Facilidade de navegação
* Feedback visual
* Mensagens exibidas ao usuário
* Compreensão das ações disponíveis

---

# ⏱️ 7. Cronograma de Testes

| Atividade                        | Frequência           | Observação                    |
| -------------------------------- | -------------------- | ----------------------------- |
| Exploração inicial da aplicação  | Início do desafio    | Entendimento do sistema       |
| Identificação de fluxos críticos | Após análise inicial | Priorização dos testes        |
| Criação dos cenários de teste    | Após exploração      | Baseado em riscos             |
| Execução dos testes              | Durante análise      | Fluxos funcionais e negativos |
| Registro de defeitos             | Durante execução     | Bugs e inconsistências        |
| Coleta de evidências             | Durante execução     | Prints e logs                 |

---

# 📋 8. Módulos e Prioridades

| Código | Módulo                      | Prioridade |
| ------ | --------------------------- | ---------- |
| RF01   | Cadastro de colaboradores   | Alta       |
| RF02   | Edição de colaboradores     | Alta       |
| RF03   | Exclusão de colaboradores   | Crítica    |
| RF04   | Listagem de colaboradores   | Alta       |
| RF05   | Dashboard                   | Média      |
| RF06   | Validação de formulário     | Alta       |
| RF07   | Tratamento de erros         | Alta       |
| RF08   | Responsividade da interface | Média      |
| RF09   | Usabilidade da aplicação    | Média      |

---

# 🐞 9. Gestão de Defeitos

Os defeitos identificados durante a execução dos testes foram registrados contendo:

* Identificador do bug
* Descrição detalhada
* Passos para reprodução
* Resultado esperado
* Resultado obtido
* Severidade
* Evidências
* Logs do console quando aplicável

---

# ⚠️ 10. Análise de Risco

A priorização dos testes foi baseada em:

* Impacto ao usuário final
* Criticidade funcional
* Probabilidade de falha
* Integridade dos dados
* Estabilidade da aplicação

---

## Fluxos considerados mais críticos

* Cadastro de colaboradores
* Exclusão de registros
* Integridade do estado da aplicação
* Tratamento de erros assíncronos

Falhas nesses pontos podem comprometer diretamente a confiabilidade do sistema e gerar inconsistência de dados.

---

# 📄 11. Documentação dos Testes

A documentação dos testes executados foi organizada contendo:

* Cenários de teste
* Casos de teste
* Bugs encontrados
* Evidências
* Logs de erro
* Análise de risco
* Resultado das execuções

Além disso, os principais defeitos encontrados foram documentados diretamente no repositório do projeto.

---

# 🎯 Nota Final

Este plano de testes foi elaborado com o objetivo de estruturar a estratégia de qualidade aplicada ao sistema de gestão de colaboradores analisado no desafio técnico da Bee Vale & Rambly.

A abordagem utilizada priorizou os fluxos críticos da aplicação, especialmente operações de CRUD, validação de dados, tratamento de erros e integridade do estado interno da aplicação.

Durante os testes foram identificadas falhas relevantes relacionadas ao tratamento de exceções, inconsistência de estado e confiabilidade dos fluxos de exclusão, evidenciando oportunidades importantes de melhoria na robustez e experiência do usuário da aplicação.
