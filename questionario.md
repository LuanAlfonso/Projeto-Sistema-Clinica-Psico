## 📝 1. Questionário de Validação de Negócio

Este documento apresenta as definições estratégicas e operacionais coletadas com os proprietários e administradores da clínica para validar o entendimento do ecossistema do software.

### Definições de Processo e Operação

| Pergunta | Resposta Técnica / Operacional |
| :--- | :--- |
| **Como é feito o agendamento hoje?** | "O processo é manual, dependendo de trocas de mensagens via WhatsApp e registro em agenda física de papel." |
| **Qual a maior dor ou gargalo do processo atual?** | "O alto índice de esquecimento por parte dos pacientes (no-show) e a total falta de controle centralizado sobre quem pagou ou não a sessão." |
| **Quem terá permissão para acessar o prontuário?** | "Apenas o psicólogo responsável direto pelo atendimento do paciente. Nenhum outro colaborador deve visualizar o histórico clínico." |
| **Como deve ser o fluxo de aviso de consulta?** | "Deve ser automático, disparado via WhatsApp ou E-mail com antecedência de 24 horas antes do horário marcado." |
| **Qual o requisito principal para o registro financeiro?** | "O sistema deve vincular o status da sessão ao status de pagamento de forma simples e visual para a recepção." |

### Conclusões do Questionário
Com base nessas respostas, o projeto priorizará o desenvolvimento de um **módulo de notificações automatizadas** e um **sistema de níveis de acesso (ACL)** rigoroso, garantindo que a secretária gerencie a agenda e o financeiro sem ter acesso aos dados sensíveis de prontuário, em total conformidade com a LGPD.