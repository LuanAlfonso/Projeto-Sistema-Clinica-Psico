# Casos de Uso Essenciais

Foram descritos quatro casos de uso completos, suficientes para atender grupos de até quatro integrantes. Caso o grupo tenha mais integrantes, recomenda-se adicionar novos casos seguindo o mesmo modelo.

## UC01 - Agendar Consulta

| Campo | Descrição |
| :--- | :--- |
| Ator principal | Paciente ou Recepção |
| Interessados | Paciente, Recepção, Psicólogo |
| Objetivo | Registrar uma consulta em horário disponível. |
| Pré-condições | Paciente e psicólogo cadastrados; agenda do profissional configurada. |
| Pós-condições | Consulta criada com status "Agendada"; lembrete programado. |
| Requisitos relacionados | RF01, RF02, RF06, RNF01, RNF03 |

### Fluxo Principal

1. O ator acessa a agenda.
2. O sistema apresenta profissionais, modalidades e horários disponíveis.
3. O ator seleciona profissional, data, horário e modalidade.
4. O sistema solicita confirmação dos dados da consulta.
5. O ator confirma o agendamento.
6. O sistema registra a consulta com status "Agendada".
7. O sistema programa envio de lembrete automático.
8. O sistema exibe confirmação do agendamento.

### Fluxos Alternativos

| Código | Situação | Tratamento |
| :--- | :--- | :--- |
| A1 | Horário não está mais disponível | Sistema informa indisponibilidade e solicita nova escolha. |
| A2 | Paciente não cadastrado | Recepção cadastra paciente antes de concluir. |
| A3 | Falha no envio do lembrete | Sistema mantém consulta criada e registra pendência de notificação. |

### Regras de Negócio

- Uma consulta não pode ocupar o mesmo horário, profissional e sala de outra consulta ativa.
- Cancelamentos e remarcações devem manter histórico.
- O lembrete deve ser enviado com antecedência padrão de 24 horas.

## UC02 - Confirmar Consulta

| Campo | Descrição |
| :--- | :--- |
| Ator principal | Paciente |
| Interessados | Paciente, Recepção, Psicólogo |
| Objetivo | Confirmar presença em uma consulta agendada. |
| Pré-condições | Consulta existente com status "Agendada"; paciente recebeu lembrete ou acessou portal. |
| Pós-condições | Consulta atualizada para "Confirmada". |
| Requisitos relacionados | RF02, RF07, RNF01, RNF05 |

### Fluxo Principal

1. O paciente acessa o link de confirmação ou o portal.
2. O sistema apresenta dados resumidos da consulta.
3. O paciente seleciona "Confirmar presença".
4. O sistema valida o token ou autenticação do paciente.
5. O sistema atualiza o status para "Confirmada".
6. O sistema disponibiliza a nova situação na agenda da recepção e do psicólogo.

### Fluxos Alternativos

| Código | Situação | Tratamento |
| :--- | :--- | :--- |
| A1 | Link expirado | Sistema orienta o paciente a acessar o portal ou contatar a clínica. |
| A2 | Paciente escolhe remarcar | Sistema direciona para o fluxo UC03 - Remarcar Consulta. |
| A3 | Consulta já cancelada | Sistema informa que a confirmação não pode ser realizada. |

### Regras de Negócio

- Apenas consultas futuras podem ser confirmadas.
- A confirmação deve ficar visível imediatamente na agenda.
- A recepção deve conseguir filtrar consultas não confirmadas.

## UC03 - Registrar Prontuário

| Campo | Descrição |
| :--- | :--- |
| Ator principal | Psicólogo |
| Interessados | Psicólogo, Paciente, Clínica |
| Objetivo | Registrar a evolução clínica de uma sessão. |
| Pré-condições | Psicólogo autenticado; paciente vinculado ao psicólogo; consulta realizada. |
| Pós-condições | Evolução registrada no prontuário com data, autor e vínculo com a sessão. |
| Requisitos relacionados | RF03, RF08, RNF02, RNF04, RNF06 |

### Fluxo Principal

1. O psicólogo acessa sua agenda.
2. O psicólogo seleciona a consulta realizada.
3. O sistema exibe o prontuário do paciente autorizado.
4. O psicólogo registra evolução, observações e encaminhamentos.
5. O psicólogo salva o registro.
6. O sistema grava a evolução com identificação do autor e data/hora.
7. O sistema mantém o registro indisponível para usuários sem permissão clínica.

### Fluxos Alternativos

| Código | Situação | Tratamento |
| :--- | :--- | :--- |
| A1 | Usuário não é psicólogo responsável | Sistema nega acesso ao prontuário. |
| A2 | Consulta ainda não realizada | Sistema permite rascunho ou bloqueia conforme configuração da clínica. |
| A3 | Falha ao salvar | Sistema preserva rascunho local temporário e informa erro. |

### Regras de Negócio

- A recepção nunca deve visualizar conteúdo do prontuário.
- Cada evolução deve registrar autor, data e sessão relacionada.
- Edições posteriores devem manter rastreabilidade.

## UC04 - Registrar Pagamento

| Campo | Descrição |
| :--- | :--- |
| Ator principal | Recepção |
| Interessados | Recepção, Administrador, Paciente |
| Objetivo | Registrar pagamento de uma consulta ou pacote de sessões. |
| Pré-condições | Consulta ou pacote cadastrado; usuário com perfil administrativo. |
| Pós-condições | Pagamento registrado e vinculado ao paciente e à consulta. |
| Requisitos relacionados | RF04, RF09, RNF01, RNF05 |

### Fluxo Principal

1. A recepção acessa a agenda ou o painel financeiro.
2. O sistema lista consultas com status financeiro.
3. A recepção seleciona a consulta ou paciente.
4. O sistema apresenta valor, vencimento e status atual.
5. A recepção informa forma de pagamento e data.
6. O sistema registra o pagamento.
7. O sistema atualiza o status financeiro para "Pago".
8. O sistema disponibiliza o registro para relatórios.

### Fluxos Alternativos

| Código | Situação | Tratamento |
| :--- | :--- | :--- |
| A1 | Pagamento parcial | Sistema registra valor pago e mantém saldo pendente. |
| A2 | Pagamento estornado | Sistema registra estorno e retorna status conforme saldo. |
| A3 | Consulta cancelada | Sistema solicita confirmação antes de registrar pagamento. |

### Regras de Negócio

- O financeiro não deve exibir conteúdo clínico.
- Pagamentos devem estar associados a paciente e consulta, quando aplicável.
- Relatórios devem permitir filtro por período, profissional e status.

