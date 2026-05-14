# Casos de Teste — Fluxo de Exclusão de Colaborador

---

# CT-019 — Excluir colaborador existente com sucesso

| Campo              | Descrição                                                            |
| ------------------ | -------------------------------------------------------------------- |
| ID                 | CT-019                                                              |
| Tipo de Teste      | Funcional                                                            |
| Prioridade         | Crítica                                                              |
| Objetivo           | Validar exclusão correta de colaborador existente                    |
| Pré-condição       | Existir colaborador cadastrado                                       |
| Passos             | 1. Acessar listagem<br>2. Clicar em excluir<br>3. Confirmar exclusão |
| Resultado Esperado | Sistema deve remover colaborador da listagem                         |
| Resultado Obtido   | removeu o colaborador da listagem                                                          |
| Status             | passou                                                        |
                                                                     |
---

#  CT-020 — Validar erro de objeto undefined durante exclusão

| Campo              | Descrição                                                            |
| ------------------ | -------------------------------------------------------------------- |
| ID                 | CT-020                                                             |
| Tipo de Teste      | Tratamento de Erro                                                   |
| Prioridade         | Crítica                                                              |
| Objetivo           | Verificar tratamento de estado inconsistente durante exclusão        |
| Pré-condição       | Lista de colaboradores carregada                                     |
| Passos             | 1. Executar exclusão em cenários consecutivos<br>2. Observar console |
| Resultado Esperado | Sistema deve validar existência do colaborador antes da exclusão     |
| Resultado Obtido   | Erro identificado:<br>`employees[idx] is undefined`                  |
| Status             | Falhou                                                               |

---

#  CT-021 — Validar dupla execução da exclusão

| Campo              | Descrição                                                |
| ------------------ | -------------------------------------------------------- |
| ID                 | CT-021                                                   |
| Tipo de Teste      | Exploratório                                             |
| Prioridade         | Alta                                                     |
| Objetivo           | Verificar possibilidade de múltiplas execuções do delete |
| Pré-condição       | Existir colaborador cadastrado                           |
| Passos             | 1. Clicar rapidamente múltiplas vezes em excluir         |
| Resultado Esperado | Sistema deve impedir múltiplas execuções simultâneas     |
| Resultado Obtido   | Possível inconsistência de estado identificada           |
| Status             | Parcialmente Validado                                    |

---

# CT-022 — Validar atualização da listagem após exclusão

| Campo              | Descrição                                           |
| ------------------ | --------------------------------------------------- |
| ID                 | CT-022                                             |
| Tipo de Teste      | Funcional                                           |
| Prioridade         | Alta                                                |
| Objetivo           | Verificar atualização da UI após exclusão           |
| Pré-condição       | Exclusão realizada                                  |
| Passos             | 1. Excluir colaborador                              |
| Resultado Esperado | Registro deve desaparecer imediatamente da listagem |
| Resultado Obtido   | desapareceu imediatamente da listagem                                            |
| Status             | passou                                       |

---

# CT-023 — Validar persistência da exclusão após refresh

| Campo              | Descrição                                     |
| ------------------ | --------------------------------------------- |
| ID                 | CT-023                                        |
| Tipo de Teste      | Funcional                                     |
| Prioridade         | Alta                                          |
| Objetivo           | Verificar persistência da exclusão            |
| Pré-condição       | Exclusão realizada                            |
| Passos             | 1. Excluir colaborador<br>2. Atualizar página |
| Resultado Esperado | Colaborador removido não deve reaparecer      |
| Resultado Obtido   | Colaborador removido não deve reapareceu                                      |
| Status             | passou                                |

---

# CT-024 — Validar feedback visual durante exclusão

| Campo              | Descrição                                       |
| ------------------ | ----------------------------------------------- |
| ID                 | CT-024                                          |
| Tipo de Teste      | Usabilidade                                     |
| Prioridade         | Média                                           |
| Objetivo           | Verificar feedback visual durante exclusão      |
| Pré-condição       | Modal de exclusão aberto                        |
| Passos             | 1. Confirmar exclusão                           |
| Resultado Esperado | Sistema deve exibir loading e confirmação clara |
| Resultado Obtido   |       exibiu loading e confirmação clara          |
| Status             | Passou                                          |

---

# CT-025 — Validar clareza do modal de confirmação

| Campo              | Descrição                                                     |
| ------------------ | ------------------------------------------------------------- |
| ID                 | CT-025                                                        |
| Tipo de Teste      | Usabilidade                                                   |
| Prioridade         | Média                                                         |
| Objetivo           | Avaliar clareza das mensagens do modal                        |
| Pré-condição       | Modal de confirmação aberto                                   |
| Passos             | 1. Abrir modal de exclusão                                    |
| Resultado Esperado | Modal deve informar claramente qual colaborador será removido |
| Resultado Obtido   | não aparece modal nenhum                           |
| Status             | Falhou                                                        |
