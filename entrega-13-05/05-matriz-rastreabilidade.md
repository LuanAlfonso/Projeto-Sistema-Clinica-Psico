# Matriz de Rastreabilidade

## 1. Rastreabilidade Horizontal

Relaciona fontes, requisitos, casos de uso, protótipos, entidades e critérios de aceite.

| Fonte | Requisito | Descrição | Caso de uso | Protótipo | Entidades | Critério de aceite |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Questionário / Doctoralia | RF01 | Agendar, remarcar e cancelar consultas online | UC01, UC02 | Tela agenda, tela agendamento | Consulta, Paciente, Psicólogo, Agenda | Usuário consegue criar consulta em horário disponível. |
| Entrevista Mariana | RF02 | Enviar lembretes automáticos por WhatsApp/e-mail | UC01, UC02 | Tela agenda, tela detalhe consulta | Notificação, Consulta, Paciente | Sistema agenda lembrete 24h antes da consulta. |
| Entrevista Pedro | RF03 | Manter prontuário eletrônico restrito | UC03 | Tela prontuário | Prontuário, Evolução, Paciente, Psicólogo | Recepção não consegue acessar prontuário. |
| Entrevista Mariana | RF04 | Controlar pagamentos e faturamento | UC04 | Tela financeiro | Pagamento, Consulta, Paciente | Pagamento altera status financeiro da sessão. |
| Sistema análogo | RF05 | Exibir perfil do profissional | UC05 | Tela perfil profissional | Psicólogo, Especialidade | Paciente visualiza especialidades e modalidade. |
| Sistema análogo | RF06 | Permitir sessão online como modalidade | UC01 | Tela agendamento | Consulta | Consulta registra modalidade presencial ou online. |
| Questionário | RF07 | Confirmar presença na consulta | UC02 | Tela confirmação | Consulta, Notificação | Confirmação altera status da consulta. |
| Entrevista Pedro | RF08 | Consultar histórico clínico | UC03 | Tela prontuário | Prontuário, Evolução | Psicólogo visualiza histórico do próprio paciente. |
| Entrevista Mariana | RF09 | Registrar inadimplência | UC04 | Tela financeiro | Pagamento, Paciente | Sistema identifica pagamentos pendentes. |
| Escopo | RF10 | Gerar relatórios administrativos | UC06 | Tela relatórios | Pagamento, Consulta | Administrador gera relatório por período. |
| LGPD / Entrevista Pedro | RNF01 | Controlar acesso por perfil | UC03, UC07 | Todas | Usuário, PerfilAcesso | Permissões impedem acesso indevido. |
| LGPD | RNF02 | Proteger dados sensíveis com criptografia | UC03 | Tela login, prontuário | Prontuário, Evolução | Dados sensíveis são protegidos em trânsito e repouso. |
| Escopo | RNF03 | Ter interface responsiva | Todos | Todas | Não aplicável | Telas funcionam em desktop e mobile. |
| Escopo | RNF04 | Carregar agenda em até 2 segundos | UC01 | Tela agenda | Consulta, Agenda | Agenda responde dentro do limite definido. |
| Escopo | RNF05 | Registrar eventos relevantes para auditoria | UC02, UC03, UC04 | Todas | Auditoria | Alterações críticas são rastreáveis. |
| LGPD | RNF06 | Garantir privacidade de prontuários | UC03 | Tela prontuário | Prontuário, Evolução | Somente psicólogo autorizado acessa dados clínicos. |

## 2. Rastreabilidade Vertical

Relaciona objetivos de negócio a funcionalidades e artefatos técnicos.

| Objetivo de negócio | Requisitos derivados | Casos de uso | Dados envolvidos | Artefatos de validação |
| :--- | :--- | :--- | :--- | :--- |
| Reduzir faltas às consultas | RF01, RF02, RF07 | UC01, UC02 | Consulta, Notificação, Paciente | Diagrama de casos de uso, protótipo agenda, matriz de testes |
| Reduzir trabalho manual da recepção | RF01, RF02, RF04, RF09 | UC01, UC02, UC04 | Consulta, Pagamento, Paciente | Protótipo agenda, protótipo financeiro |
| Proteger sigilo clínico | RF03, RF08, RNF01, RNF02, RNF06 | UC03 | Prontuário, Evolução, Usuário, PerfilAcesso | Especificação suplementar, controle de permissões |
| Melhorar controle financeiro | RF04, RF09, RF10 | UC04, UC06 | Pagamento, Consulta, Paciente | Protótipo financeiro, relatórios |
| Oferecer experiência responsiva | RNF03, RNF04 | Todos | Não aplicável | Protótipos desktop/mobile, especificação suplementar |

## 3. Legenda

- RF: Requisito funcional.
- RNF: Requisito não funcional.
- UC: Caso de uso.
- A rastreabilidade horizontal acompanha o requisito entre artefatos do mesmo nível de entrega.
- A rastreabilidade vertical liga objetivos de negócio, requisitos, funcionalidades, dados e validação.
