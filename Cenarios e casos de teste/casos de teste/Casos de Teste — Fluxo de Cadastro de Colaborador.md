# Casos de Teste — Fluxo de Cadastro de Colaborador

---

# CT-001 — Cadastro de colaborador com dados válidos

| Campo              | Descrição                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| ID                 | CT-001                                                                                                                    |
| Tipo de Teste      | Funcional                                                                                                                 |
| Prioridade         | Alta                                                                                                                      |
| Objetivo           | Validar que o sistema permite cadastrar um colaborador com dados válidos                                                  |
| Pré-condição       | Usuário deve estar na tela de cadastro                                                                                    |
| Passos             | 1. Acessar formulário de cadastro<br>2. Preencher todos os campos obrigatórios com dados válidos<br>3. Clicar em “Salvar” |
| Resultado Esperado | Sistema deve cadastrar colaborador com sucesso e exibir registro na listagem                                              |
| Resultado Obtido   | cadastrado com sucesso                                                                                               |
| Status             | passou                                                                                                           |

---

# CT-002 — Cadastro com campos obrigatórios vazios

| Campo              | Descrição                                                                   |
| ------------------ | --------------------------------------------------------------------------- |
| ID                 | CT-002                                                                      |
| Tipo de Teste      | Negativo                                                                    |
| Prioridade         | Alta                                                                        |
| Objetivo           | Validar comportamento ao tentar cadastrar sem preencher campos obrigatórios |
| Pré-condição       | Estar na tela de cadastro                                                   |
| Passos             | 1. Acessar formulário<br>2. Deixar campos vazios<br>3. Clicar em “Salvar”   |
| Resultado Esperado | Sistema deve impedir cadastro e exibir mensagens de validação               |
| Resultado Obtido   | Campos aparentam não possuir validação robusta                              |
| Status             | Falhou                                                                       |

---

# CT-003 — Cadastro com email inválido

| Campo              | Descrição                                                                            |
| ------------------ | ------------------------------------------------------------------------------------ |
| ID                 | CT-003                                                                               |
| Tipo de Teste      | Negativo                                                                             |
| Prioridade         | Alta                                                                                 |
| Objetivo           | Validar aceitação de email inválido                                                  |
| Pré-condição       | Tela de cadastro aberta                                                              |
| Passos             | 1. Preencher formulário<br>2. Inserir email inválido (`testeemail.com`)<br>3. Salvar |
| Resultado Esperado | Sistema deve bloquear envio e informar erro de validação                             |
| Resultado Obtido   | o sistema bloqueou                                                                          |
| Status             | passou                                                                        |

---

# CT-004 — Cadastro com CPF inválido

| Campo              | Descrição                                     |
| ------------------ | --------------------------------------------- |
| ID                 | CT-004                                        |
| Tipo de Teste      | Negativo                                      |
| Prioridade         | Alta                                          |
| Objetivo           | Verificar validação de CPF                    |
| Pré-condição       | Tela de cadastro disponível                   |
| Passos             | 1. Inserir CPF inválido<br>2. Salvar cadastro |
| Dados de Teste     | CPF: 111                                      |
| Resultado Esperado | Sistema deve rejeitar CPF inválido            |
| Resultado Obtido   | Aceitou com o CPF ERRADO                                     |
| Status             | Falhou                                 |                                                                                          |

---

# CT-005 — Cadastro com múltiplos cliques no botão salvar

| Campo              | Descrição                                                                 |
| ------------------ | ------------------------------------------------------------------------- |
| ID                 | CT-005                                                                    |
| Tipo de Teste      | Exploratório                                                              |
| Prioridade         | Média                                                                     |
| Objetivo           | Verificar duplicidade de envio                                            |
| Pré-condição       | Formulário preenchido                                                     |
| Passos             | 1. Preencher formulário<br>2. Clicar várias vezes rapidamente em “Salvar” |
| Resultado Esperado | Sistema deve bloquear múltiplos submits                                   |
| Resultado Obtido   | Possível risco de duplicidade                                             |
| Status             | Parcialmente Validado                                                     |

---

# CT-006 — Cadastro com caracteres especiais

| Campo              | Descrição                                               |
| ------------------ | ------------------------------------------------------- |
| ID                 | CT-006                                                  |
| Tipo de Teste      | Negativo                                                |
| Prioridade         | Média                                                   |
| Objetivo           | Verificar tratamento de caracteres especiais            |
| Pré-condição       | Tela de cadastro disponível                             |
| Passos             | 1. Inserir caracteres especiais nos campos<br>2. Salvar |
| Dados de Teste     | Nome: @@@###$$$                                         |
| Resultado Esperado | Sistema deve validar entrada ou sanitizar dados         |
| Resultado Obtido   | Aceita cadastro com o nome errado                                               |
| Status             | Falhou                                          |

---

# CT-007 — Verificar feedback visual durante cadastro

| Campo              | Descrição                                    |
| ------------------ | -------------------------------------------- |
| ID                 | CT-007                                       |
| Tipo de Teste      | Usabilidade                                  |
| Prioridade         | Média                                        |
| Objetivo           | Verificar feedback visual durante salvamento |
| Pré-condição       | Formulário preenchido                        |
| Passos             | 1. Realizar cadastro                         |
| Resultado Esperado | Sistema deve exibir loading, sucesso ou erro |
| Resultado Obtido   | há feedback visual consistente           |
| Status             | Passou                                  |

---

# CT-008 — Cadastro com texto excessivamente longo

| Campo              | Descrição                                            |
| ------------------ | ---------------------------------------------------- |
| ID                 | CT-008                                               |
| Tipo de Teste      | Negativo                                             |
| Prioridade         | Média                                                |
| Objetivo           | Validar limite de entrada dos campos                 |
| Pré-condição       | Tela de cadastro disponível                          |
| Passos             | 1. Inserir texto muito longo nos campos<br>2. Salvar |
| Resultado Esperado | Sistema deve limitar quantidade de caracteres        |
| Resultado Obtido   | Não tem limites de quantidade de caracteres                                          |
| Status             | Falhou                                       |

---

# CT-009 — Persistência correta após cadastro

| Campo              | Descrição                                                     |
| ------------------ | ------------------------------------------------------------- |
| ID                 | CT-009                                                        |
| Tipo de Teste      | Funcional                                                     |
| Prioridade         | Alta                                                          |
| Objetivo           | Verificar se colaborador permanece após atualização da página |
| Pré-condição       | Cadastro realizado                                            |
| Passos             | 1. Cadastrar colaborador<br>2. Atualizar página               |
| Resultado Esperado | Registro deve permanecer salvo                                |
| Resultado Obtido   | Permaneceu salvo|
| Status             | Passou                                                |
