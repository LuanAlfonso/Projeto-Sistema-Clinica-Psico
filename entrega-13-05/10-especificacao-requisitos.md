# Especificação de Requisitos - IEEE 830 / EOR

## 1. Introdução

### 1.1 Propósito

Este documento especifica os objetivos e requisitos do Sistema de Gerenciamento e Agendamento de Consultas para Clínica de Psicologia. Ele consolida requisitos funcionais, não funcionais, regras de negócio, atores e critérios de aceitação.

### 1.2 Escopo

O sistema será uma aplicação web responsiva para centralizar agendamento, confirmação automática, prontuário eletrônico, controle financeiro e relatórios administrativos.

### 1.3 Definições

- RF: requisito funcional.
- RNF: requisito não funcional.
- UC: caso de uso.
- LGPD: Lei Geral de Proteção de Dados.
- Prontuário: conjunto de registros clínicos do paciente.

## 2. Descrição Geral

### 2.1 Perspectiva do Produto

O produto será usado por recepção, psicólogos, pacientes e administradores. Ele substitui fluxos manuais baseados em agenda física, mensagens avulsas e planilhas financeiras.

### 2.2 Funções do Produto

- Gerenciar agenda.
- Agendar e confirmar consultas.
- Enviar notificações automáticas.
- Manter cadastro de pacientes e profissionais.
- Registrar prontuários.
- Controlar pagamentos.
- Gerar relatórios.
- Controlar perfis e permissões.

### 2.3 Características dos Usuários

| Usuário | Característica |
| :--- | :--- |
| Paciente | Busca autonomia para agendar e confirmar consultas. |
| Recepção | Necessita eficiência operacional e controle financeiro. |
| Psicólogo | Necessita sigilo, mobilidade e organização clínica. |
| Administrador | Necessita visão gerencial e configuração de acesso. |

### 2.4 Restrições

- O sistema deve respeitar a LGPD.
- O prontuário deve ter acesso restrito.
- A interface deve ser responsiva.
- A agenda deve impedir conflitos de horário.

## 3. Objetivos e Requisitos

### 3.1 Objetivos

| ID | Objetivo | Medida de sucesso |
| :--- | :--- | :--- |
| OBJ01 | Reduzir faltas às consultas | Lembretes e confirmações automáticas disponíveis. |
| OBJ02 | Reduzir trabalho manual da recepção | Agenda e financeiro integrados. |
| OBJ03 | Proteger dados clínicos | Prontuário acessível apenas ao psicólogo responsável. |
| OBJ04 | Melhorar controle financeiro | Pagamentos vinculados a consultas e relatórios. |
| OBJ05 | Permitir uso em dispositivos móveis | Interface responsiva. |

### 3.2 Requisitos Funcionais

| ID | Requisito | Prioridade | Critério de aceitação |
| :--- | :--- | :--- | :--- |
| RF01 | O sistema deve permitir agendar, remarcar e cancelar consultas. | Alta | Consulta criada/alterada sem conflito de horário. |
| RF02 | O sistema deve enviar lembretes automáticos por WhatsApp ou e-mail. | Alta | Lembrete programado 24h antes da consulta. |
| RF03 | O sistema deve possuir prontuário eletrônico com acesso restrito. | Crítica | Recepção não acessa conteúdo clínico. |
| RF04 | O sistema deve controlar pagamentos e faturamento. | Alta | Pagamento registrado altera status financeiro. |
| RF05 | O sistema deve exibir perfil do profissional. | Média | Paciente visualiza especialidades, CRP e modalidade. |
| RF06 | O sistema deve registrar modalidade presencial ou online. | Média | Consulta salva com modalidade selecionada. |
| RF07 | O sistema deve permitir confirmação de presença pelo paciente. | Alta | Status muda para "Confirmada". |
| RF08 | O sistema deve permitir consulta ao histórico clínico pelo psicólogo responsável. | Crítica | Histórico exibido apenas para usuário autorizado. |
| RF09 | O sistema deve identificar pagamentos pendentes. | Alta | Financeiro lista pendências por paciente/período. |
| RF10 | O sistema deve gerar relatórios administrativos. | Média | Relatório gerado por período, profissional e status. |
| RF11 | O sistema deve permitir cadastro de pacientes. | Alta | Paciente salvo com dados obrigatórios válidos. |
| RF12 | O sistema deve permitir gerenciamento de usuários e perfis. | Alta | Administrador cria/edita perfis conforme permissão. |

### 3.3 Requisitos Não Funcionais

| ID | Requisito | Categoria ISO/IEC 25010 | Critério de aceitação |
| :--- | :--- | :--- | :--- |
| RNF01 | O sistema deve controlar acesso por perfil. | Segurança | Permissões validadas no servidor. |
| RNF02 | Dados sensíveis devem ser protegidos por criptografia. | Segurança | HTTPS e proteção dos dados armazenados. |
| RNF03 | O sistema deve ser responsivo. | Portabilidade / Usabilidade | Funciona em desktop, tablet e celular. |
| RNF04 | A agenda deve carregar em até 2 segundos. | Eficiência de desempenho | Teste com volume estimado de uso normal. |
| RNF05 | Ações sensíveis devem ser auditadas. | Segurança / Confiabilidade | Acesso ao prontuário e pagamentos ficam registrados. |
| RNF06 | O prontuário deve preservar privacidade clínica. | Segurança | Acesso limitado ao psicólogo responsável. |
| RNF07 | O sistema deve apresentar mensagens claras de validação. | Usabilidade | Campos obrigatórios e erros são informados. |
| RNF08 | O sistema deve possuir backup periódico. | Confiabilidade | Backup diário de dados críticos. |

## 4. Regras de Negócio

| ID | Regra |
| :--- | :--- |
| RN01 | Não pode existir mais de uma consulta ativa para o mesmo psicólogo no mesmo horário. |
| RN02 | A recepção não pode visualizar conteúdo de prontuário ou evolução clínica. |
| RN03 | O psicólogo só pode acessar prontuários de pacientes sob sua responsabilidade. |
| RN04 | Consultas canceladas devem permanecer no histórico. |
| RN05 | Pagamentos devem indicar status: pendente, pago, parcial ou estornado. |
| RN06 | Lembretes automáticos devem ser programados com antecedência padrão de 24 horas. |
| RN07 | Alterações em prontuários devem manter autor, data e histórico de auditoria. |

## 5. Interfaces Externas

| Interface | Descrição |
| :--- | :--- |
| WhatsApp/e-mail | Envio de lembretes e confirmação de consulta. |
| Navegador web | Acesso principal ao sistema. |
| Banco de dados | Persistência de usuários, consultas, prontuários e pagamentos. |

## 6. Critérios Gerais de Aceitação

- Todos os requisitos devem possuir rastreabilidade.
- As telas principais devem existir no protótipo.
- O MER e o dicionário de dados devem cobrir as entidades principais.
- A especificação suplementar deve contemplar requisitos não funcionais por categoria de qualidade.
- Os documentos devem estar versionados no GitHub.

