# 🧪 Casos de Teste — Fluxo de Edição de Colaborador

---

# 🔹 CT-010 — Editar colaborador com dados válidos

| Campo              | Descrição                                                                           |
| ------------------ | ----------------------------------------------------------------------------------- |
| ID                 | CT-011                                                                              |
| Tipo de Teste      | Funcional                                                                           |
| Prioridade         | Alta                                                                                |
| Objetivo           | Validar edição de colaborador com dados válidos                                     |
| Pré-condição       | Existir colaborador cadastrado                                                      |
| Passos             | 1. Acessar listagem<br>2. Clicar em editar<br>3. Alterar dados válidos<br>4. Salvar |
| Dados de Teste     | Alterar cargo de “QA Jr” para “QA Pleno”                                            |
| Resultado Esperado | Sistema deve salvar alterações e atualizar listagem                                 |
| Resultado Obtido   | A definir                                                                           |
| Status             | Não Executado                                                                       |

---

# 🔹 CT-011 — Editar colaborador deixando campos obrigatórios vazios

| Campo              | Descrição                                                                        |
| ------------------ | -------------------------------------------------------------------------------- |
| ID                 | CT-012                                                                           |
| Tipo de Teste      | Negativo                                                                         |
| Prioridade         | Alta                                                                             |
| Objetivo           | Verificar validação de campos obrigatórios durante edição                        |
| Pré-condição       | Existir colaborador cadastrado                                                   |
| Passos             | 1. Editar colaborador<br>2. Remover conteúdo de campos obrigatórios<br>3. Salvar |
| Resultado Esperado | Sistema deve impedir atualização e exibir mensagens de validação                 |
| Resultado Obtido   | A validar                                                                        |
| Status             | Não Executado                                                                    |

---

# 🔹 CT-012 — Editar colaborador com email inválido

| Campo              | Descrição                                                       |
| ------------------ | --------------------------------------------------------------- |
| ID                 | CT-013                                                          |
| Tipo de Teste      | Negativo                                                        |
| Prioridade         | Alta                                                            |
| Objetivo           | Validar rejeição de email inválido                              |
| Pré-condição       | Existir colaborador cadastrado                                  |
| Passos             | 1. Editar colaborador<br>2. Inserir email inválido<br>3. Salvar |
| Dados de Teste     | `emailinvalido.com`                                             |
| Resultado Esperado | Sistema deve bloquear atualização                               |
| Resultado Obtido   | A validar                                                       |
| Status             | Não Executado                                                   |

---

# 🔹 CT-013 — Editar colaborador com CPF inválido

| Campo              | Descrição                                                     |
| ------------------ | ------------------------------------------------------------- |
| ID                 | CT-014                                                        |
| Tipo de Teste      | Negativo                                                      |
| Prioridade         | Alta                                                          |
| Objetivo           | Verificar validação de CPF durante edição                     |
| Pré-condição       | Existir colaborador cadastrado                                |
| Passos             | 1. Editar colaborador<br>2. Inserir CPF inválido<br>3. Salvar |
| Dados de Teste     | CPF: 123                                                      |
| Resultado Esperado | Sistema deve impedir atualização                              |
| Resultado Obtido   | A validar                                                     |
| Status             | Não Executado                                                 |

---

# 🔹 CT-014 — Verificar persistência dos dados editados

| Campo              | Descrição                                        |
| ------------------ | ------------------------------------------------ |
| ID                 | CT-015                                           |
| Tipo de Teste      | Funcional                                        |
| Prioridade         | Alta                                             |
| Objetivo           | Validar persistência das alterações após refresh |
| Pré-condição       | Edição realizada com sucesso                     |
| Passos             | 1. Editar colaborador<br>2. Atualizar página     |
| Resultado Esperado | Dados alterados devem permanecer salvos          |
| Resultado Obtido   | A validar                                        |
| Status             | Não Executado                                    |

---

# 🔹 CT-015 — Cancelar edição de colaborador

| Campo              | Descrição                                  |
| ------------------ | ------------------------------------------ |
| ID                 | CT-016                                     |
| Tipo de Teste      | Funcional                                  |
| Prioridade         | Média                                      |
| Objetivo           | Verificar comportamento ao cancelar edição |
| Pré-condição       | Tela de edição aberta                      |
| Passos             | 1. Alterar dados<br>2. Cancelar edição     |
| Resultado Esperado | Alterações não devem ser salvas            |
| Resultado Obtido   | A validar                                  |
| Status             | Não Executado                              |

---

# 🔹 CT-016 — Editar colaborador com caracteres especiais

| Campo              | Descrição                                    |
| ------------------ | -------------------------------------------- |
| ID                 | CT-017                                       |
| Tipo de Teste      | Negativo                                     |
| Prioridade         | Média                                        |
| Objetivo           | Validar tratamento de caracteres especiais   |
| Pré-condição       | Existir colaborador cadastrado               |
| Passos             | 1. Inserir caracteres especiais<br>2. Salvar |
| Dados de Teste     | Nome: `@@@###$$$`                            |
| Resultado Esperado | Sistema deve validar ou sanitizar entrada    |
| Resultado Obtido   | A validar                                    |
| Status             | Não Executado                                |

---

# 🔹 CT-017 — Editar colaborador com texto excessivamente longo

| Campo              | Descrição                                 |
| ------------------ | ----------------------------------------- |
| ID                 | CT-018                                    |
| Tipo de Teste      | Negativo                                  |
| Prioridade         | Média                                     |
| Objetivo           | Validar limite máximo de caracteres       |
| Pré-condição       | Tela de edição disponível                 |
| Passos             | 1. Inserir texto muito longo<br>2. Salvar |
| Resultado Esperado | Sistema deve limitar tamanho dos campos   |
| Resultado Obtido   | A validar                                 |
| Status             | Não Executado                             |

---

# 🔹 CT-018 — Verificar feedback visual durante edição

| Campo              | Descrição                                    |
| ------------------ | -------------------------------------------- |
| ID                 | CT-019                                       |
| Tipo de Teste      | Usabilidade                                  |
| Prioridade         | Média                                        |
| Objetivo           | Validar feedback visual durante atualização  |
| Pré-condição       | Tela de edição aberta                        |
| Passos             | 1. Salvar alterações                         |
| Resultado Esperado | Sistema deve exibir loading, sucesso ou erro |
| Resultado Obtido   | Feedback visual insuficiente                 |
| Status             | Falhou                                       |
