# Documento Visão

## 1. Introdução

Este documento apresenta a visão do produto para um sistema web de gerenciamento e agendamento de consultas voltado a uma clínica de psicologia. O sistema busca centralizar agenda, comunicação com pacientes, registros clínicos e controle financeiro, reduzindo tarefas manuais da recepção e preservando o sigilo das informações sensíveis dos pacientes.

## 2. Problema

Atualmente, o processo de agendamento e confirmação de consultas é realizado de forma manual, principalmente por WhatsApp e agenda física. Esse fluxo gera retrabalho, esquecimento de confirmações, falta de visão centralizada da agenda, dificuldade de controle de pagamentos e riscos de exposição indevida de informações clínicas.

## 3. Objetivo do Produto

Disponibilizar uma plataforma web responsiva que permita:

- Agendar, remarcar e cancelar consultas.
- Enviar lembretes automáticos por WhatsApp ou e-mail.
- Controlar pagamentos vinculados às sessões.
- Registrar prontuários eletrônicos com acesso restrito ao psicólogo responsável.
- Consultar agenda e histórico do paciente em dispositivos móveis.
- Garantir segurança, privacidade e conformidade com a LGPD.

## 4. Público-Alvo

| Perfil | Necessidade principal |
| :--- | :--- |
| Paciente | Marcar, consultar, confirmar, remarcar ou cancelar consultas com facilidade. |
| Secretária/Recepção | Gerenciar agenda, confirmações, pagamentos e dados cadastrais sem acessar prontuários. |
| Psicólogo | Acompanhar agenda, registrar evolução clínica e acessar prontuário com sigilo. |
| Administrador da clínica | Acompanhar indicadores, cadastros, perfis de acesso e controle financeiro. |

## 5. Escopo do Produto

### Incluído

- Cadastro e autenticação de usuários.
- Perfis de acesso: administrador, recepção, psicólogo e paciente.
- Cadastro de pacientes e profissionais.
- Agenda online com disponibilidade por profissional.
- Marcação, remarcação, cancelamento e confirmação de consultas.
- Notificações automáticas de confirmação.
- Controle financeiro por sessão.
- Prontuário eletrônico restrito.
- Relatórios básicos de agenda, faltas e pagamentos.
- Interface responsiva para web e mobile.

### Fora do escopo inicial

- Integração bancária completa.
- Assinatura digital de documentos.
- Prontuário interoperável com sistemas externos.
- Aplicativo nativo Android/iOS.
- Videochamada própria dentro do sistema.

## 6. Principais Restrições

- Dados de saúde mental são dados sensíveis e devem obedecer à LGPD.
- Apenas o psicólogo responsável pode acessar o prontuário do paciente.
- A recepção pode visualizar agenda, cadastro e situação financeira, mas não o conteúdo clínico.
- O sistema deve funcionar em navegador web e adaptar-se a telas móveis.

## 7. Benefícios Esperados

- Redução de faltas por esquecimento.
- Menos tempo gasto pela recepção em confirmações manuais.
- Controle financeiro mais confiável.
- Maior segurança no tratamento de dados sensíveis.
- Melhor experiência para pacientes e profissionais.
- Histórico clínico organizado e acessível apenas ao profissional autorizado.

## 8. Critérios de Sucesso

| Critério | Métrica sugerida |
| :--- | :--- |
| Redução de faltas | Reduzir no-show após implantação dos lembretes automáticos. |
| Eficiência administrativa | Diminuir tempo diário gasto com confirmações manuais. |
| Segurança | Não permitir acesso de recepção a prontuários. |
| Usabilidade | Agenda deve carregar em até 2 segundos em condições normais. |
| Rastreabilidade | Requisitos, casos de uso, telas, entidades e testes devem permanecer vinculados. |

