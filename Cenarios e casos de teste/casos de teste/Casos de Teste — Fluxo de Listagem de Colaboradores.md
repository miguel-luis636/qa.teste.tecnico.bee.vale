# Casos de Teste — Fluxo de Listagem de Colaboradores

---

#  CT-031 — Exibir listagem de colaboradores corretamente

| Campo              | Descrição                                              |
| ------------------ | ------------------------------------------------------ |
| ID                 | CT-031                                                 |
| Tipo de Teste      | Funcional                                              |
| Prioridade         | Alta                                                   |
| Objetivo           | Validar carregamento correto da listagem               |
| Pré-condição       | Existirem colaboradores cadastrados                    |
| Passos             | 1. Acessar página de listagem                          |
| Resultado Esperado | Sistema deve exibir todos os colaboradores cadastrados |
| Resultado Obtido   | exibiu todos os colaboradores cadastrados                                           |
| Status             | Passou                                          |

---

#  CT-032 — Validar exibição correta das informações dos colaboradores

| Campo              | Descrição                                                                |
| ------------------ | ------------------------------------------------------------------------ |
| ID                 | CT-032                                                                   |
| Tipo de Teste      | Funcional                                                                |
| Prioridade         | Alta                                                                     |
| Objetivo           | Verificar consistência dos dados exibidos                                |
| Pré-condição       | Existirem registros cadastrados                                          |
| Passos             | 1. Acessar listagem<br>2. Comparar dados exibidos com cadastro realizado |
| Resultado Esperado | Informações devem corresponder aos dados cadastrados                     |
| Resultado Obtido   |As Informações devem correspondem                                                              |
| Status             | Passou                                                         |

---

#  CT-033 — Atualizar listagem após cadastro de colaborador

| Campo              | Descrição                                                |
| ------------------ | -------------------------------------------------------- |
| ID                 | CT-033                                                   |
| Tipo de Teste      | Funcional                                                |
| Prioridade         | Alta                                                     |
| Objetivo           | Verificar atualização dinâmica da listagem após cadastro |
| Pré-condição       | Tela de listagem aberta                                  |
| Passos             | 1. Cadastrar novo colaborador                            |
| Resultado Esperado | Novo colaborador deve aparecer imediatamente na listagem |
| Resultado Obtido   | Novo colaborador apareceu                                                |
| Status             | passou                                            |

---

#  CT-034 — Atualizar listagem após edição de colaborador

| Campo              | Descrição                                                 |
| ------------------ | --------------------------------------------------------- |
| ID                 | CT-034                                                    |
| Tipo de Teste      | Funcional                                                 |
| Prioridade         | Alta                                                      |
| Objetivo           | Verificar atualização da listagem após edição             |
| Pré-condição       | Existir colaborador cadastrado                            |
| Passos             | 1. Editar colaborador                                     |
| Resultado Esperado | Dados atualizados devem aparecer corretamente na listagem |
| Resultado Obtido   | os Dados foram atualizados                                               |
| Status             | passou                                           |

---

#  CT-035 — Atualizar listagem após exclusão de colaborador

| Campo              | Descrição                                        |
| ------------------ | ------------------------------------------------ |
| ID                 | CT-035                                           |
| Tipo de Teste      | Funcional                                        |
| Prioridade         | Alta                                             |
| Objetivo           | Validar remoção visual do registro após exclusão |
| Pré-condição       | Existir colaborador cadastrado                   |
| Passos             | 1. Excluir colaborador                           |
| Resultado Esperado | Registro deve desaparecer da listagem            |
| Resultado Obtido   | os dados desaparecem                                        |
| Status             | Passou                                  |

---

#  CT-036 — Validar comportamento da listagem sem registros

| Campo              | Descrição                                                       |
| ------------------ | --------------------------------------------------------------- |
| ID                 | CT-036                                                          |
| Tipo de Teste      | Funcional                                                       |
| Prioridade         | Média                                                           |
| Objetivo           | Verificar comportamento quando não há colaboradores cadastrados |
| Pré-condição       | Não existir registros                                           |
| Passos             | 1. Acessar listagem vazia                                       |
| Resultado Esperado | Sistema deve exibir mensagem amigável de lista vazia            |
| Resultado Obtido   | Dashboard/listagem exibem apenas valores zerados                |
| Status             | Parcialmente Validado                                           |

---

# CT-037 — Validar ordenação visual da tabela

| Campo              | Descrição                                |
| ------------------ | ---------------------------------------- |
| ID                 | CT-037                                   |
| Tipo de Teste      | Exploratório                             |
| Prioridade         | Média                                    |
| Objetivo           | Verificar organização visual da listagem |
| Pré-condição       | Existirem múltiplos registros            |
| Passos             | 1. Acessar listagem                      |
| Resultado Esperado | Dados devem estar organizados e legíveis |
| Resultado Obtido   | A validar                                |
| Status             | passou                            |

---

# CT-038 — Validar responsividade da listagem em dispositivos móveis

| Campo              | Descrição                                           |
| ------------------ | --------------------------------------------------- |
| ID                 | CT-038                                              |
| Tipo de Teste      | Usabilidade                                         |
| Prioridade         | Média                                               |
| Objetivo           | Verificar comportamento da tabela em telas menores  |
| Pré-condição       | Aplicação aberta em viewport mobile                 |
| Passos             | 1. Reduzir resolução da tela<br>2. Acessar listagem |
| Resultado Esperado | Interface deve permanecer utilizável e responsiva   |
| Resultado Obtido   | interface quebra no mobile           |
| Status             | Falhou                            |

---

# CT-039 — Validar consistência visual da listagem

| Campo              | Descrição                                             |
| ------------------ | ----------------------------------------------------- |
| ID                 | CT-039                                                |
| Tipo de Teste      | Usabilidade                                           |
| Prioridade         | Média                                                 |
| Objetivo           | Avaliar organização visual da tabela                  |
| Pré-condição       | Tela de listagem aberta                               |
| Passos             | 1. Avaliar alinhamento e legibilidade                 |
| Resultado Esperado | Interface deve manter consistência visual             |
| Resultado Obtido   | Identificadas inconsistências de idioma e organização |
| Status             | Falhou                                                |
