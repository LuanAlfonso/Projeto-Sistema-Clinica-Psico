# Dicionário de Dados e Glossário

## Glossário

| Termo | Definição | Informações |
| :--- | :--- | :--- |
| Agenda | Conjunto de horários disponíveis para atendimento de um psicólogo. | Usada para marcação de consultas. |
| Consulta | Atendimento agendado entre paciente e psicólogo. | Pode ser presencial ou online. |
| Confirmação | Ação do paciente informando presença prevista. | Atualiza status da consulta. |
| Evolução | Registro clínico feito pelo psicólogo após ou durante a sessão. | Parte do prontuário. |
| No-show | Falta do paciente sem aviso prévio. | Indicador importante para relatórios. |
| Paciente | Pessoa atendida pela clínica. | Possui dados cadastrais e prontuário. |
| Pagamento | Registro financeiro associado a consulta ou pacote. | Controlado pela recepção/administração. |
| Prontuário | Conjunto de registros clínicos do paciente. | Acesso restrito ao psicólogo responsável. |
| Psicólogo | Profissional responsável pelo atendimento clínico. | Identificado pelo CRP. |
| Recepção | Perfil administrativo que opera agenda, cadastro e financeiro. | Não acessa prontuários. |

## Dicionário de Dados

### USUARIO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_usuario | Identificador do usuário | Inteiro | PK | Obrigatório, único |
| nome | Nome completo | Texto, 120 | - | Obrigatório |
| email | E-mail de acesso | Texto, 160 | - | Obrigatório, único, formato de e-mail |
| senha_hash | Senha criptografada/hasheada | Texto, 255 | - | Obrigatório |
| telefone | Telefone de contato | Texto, 20 | - | Formato válido de telefone |
| status | Situação do usuário | Texto, 20 | - | Ativo, inativo ou bloqueado |
| criado_em | Data de criação | Data/hora | - | Gerado pelo sistema |

### PERFIL_ACESSO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_perfil | Identificador do perfil | Inteiro | PK | Obrigatório, único |
| nome | Nome do perfil | Texto, 50 | USUARIO | Administrador, recepção, psicólogo ou paciente |
| descricao | Descrição das permissões | Texto, 255 | - | Opcional |

### PACIENTE

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_paciente | Identificador do paciente | Inteiro | PK | Obrigatório, único |
| id_usuario | Usuário vinculado ao paciente | Inteiro | FK USUARIO | Obrigatório |
| data_nascimento | Data de nascimento | Data | - | Não pode ser futura |
| cpf | CPF do paciente | Texto, 14 | - | Único, formato válido quando informado |
| contato_emergencia | Contato emergencial | Texto, 120 | - | Opcional |
| observacoes_administrativas | Observações não clínicas | Texto, 500 | - | Não deve conter evolução clínica |

### PSICOLOGO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_psicologo | Identificador do psicólogo | Inteiro | PK | Obrigatório, único |
| id_usuario | Usuário vinculado ao psicólogo | Inteiro | FK USUARIO | Obrigatório |
| crp | Registro profissional | Texto, 30 | - | Obrigatório, único |
| especialidades | Especialidades de atendimento | Texto, 255 | - | Opcional |
| minibio | Apresentação profissional | Texto, 1000 | - | Opcional |
| modalidade_atendimento | Presencial, online ou ambos | Texto, 20 | CONSULTA | Valor permitido |

### CONSULTA

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_consulta | Identificador da consulta | Inteiro | PK | Obrigatório, único |
| id_paciente | Paciente atendido | Inteiro | FK PACIENTE | Obrigatório |
| id_psicologo | Psicólogo responsável | Inteiro | FK PSICOLOGO | Obrigatório |
| data_hora_inicio | Início da consulta | Data/hora | AGENDA | Obrigatório, não conflitante |
| data_hora_fim | Fim da consulta | Data/hora | AGENDA | Maior que início |
| modalidade | Tipo de atendimento | Texto, 20 | - | Presencial ou online |
| status_consulta | Situação da consulta | Texto, 20 | PAGAMENTO, EVOLUCAO | Agendada, confirmada, realizada, cancelada ou falta |
| status_confirmacao | Confirmação do paciente | Texto, 20 | NOTIFICACAO | Pendente, confirmada ou recusada |

### NOTIFICACAO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_notificacao | Identificador da notificação | Inteiro | PK | Obrigatório, único |
| id_consulta | Consulta relacionada | Inteiro | FK CONSULTA | Obrigatório |
| canal | Canal de envio | Texto, 20 | - | WhatsApp ou e-mail |
| status_envio | Estado do envio | Texto, 20 | - | Pendente, enviado ou falhou |
| enviar_em | Data/hora planejada | Data/hora | - | Deve ser anterior à consulta |
| enviado_em | Data/hora real de envio | Data/hora | - | Obrigatório quando status for enviado |

### PRONTUARIO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_prontuario | Identificador do prontuário | Inteiro | PK | Obrigatório, único |
| id_paciente | Paciente dono do prontuário | Inteiro | FK PACIENTE | Obrigatório |
| id_psicologo_responsavel | Psicólogo autorizado | Inteiro | FK PSICOLOGO | Obrigatório |
| criado_em | Data de criação | Data/hora | - | Gerado pelo sistema |
| status | Situação do prontuário | Texto, 20 | - | Ativo, arquivado ou bloqueado |

### EVOLUCAO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_evolucao | Identificador da evolução | Inteiro | PK | Obrigatório, único |
| id_prontuario | Prontuário relacionado | Inteiro | FK PRONTUARIO | Obrigatório |
| id_consulta | Consulta relacionada | Inteiro | FK CONSULTA | Opcional |
| id_psicologo_autor | Autor do registro | Inteiro | FK PSICOLOGO | Obrigatório |
| descricao | Conteúdo clínico | Texto longo | - | Obrigatório, acesso restrito |
| criado_em | Data de criação | Data/hora | - | Gerado pelo sistema |
| atualizado_em | Última alteração | Data/hora | - | Atualizado pelo sistema |

### PAGAMENTO

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_pagamento | Identificador do pagamento | Inteiro | PK | Obrigatório, único |
| id_consulta | Consulta vinculada | Inteiro | FK CONSULTA | Opcional para pacote |
| id_paciente | Paciente pagador | Inteiro | FK PACIENTE | Obrigatório |
| valor | Valor do pagamento | Decimal, 10,2 | - | Maior ou igual a zero |
| forma_pagamento | Meio de pagamento | Texto, 30 | - | Pix, cartão, dinheiro, transferência ou outro |
| status_pagamento | Situação financeira | Texto, 20 | - | Pendente, pago, parcial ou estornado |
| vencimento | Data de vencimento | Data | - | Obrigatório para cobrança |
| pago_em | Data do pagamento | Data/hora | - | Obrigatório quando status for pago |

### AUDITORIA

| Campo | Definição | Tipo / tamanho | Relacionamento | Regra de validação |
| :--- | :--- | :--- | :--- | :--- |
| id_auditoria | Identificador do evento | Inteiro | PK | Obrigatório, único |
| id_usuario | Usuário que executou a ação | Inteiro | FK USUARIO | Obrigatório |
| acao | Ação realizada | Texto, 80 | - | Obrigatório |
| entidade | Entidade afetada | Texto, 80 | - | Obrigatório |
| id_entidade | Registro afetado | Inteiro | - | Obrigatório quando aplicável |
| criado_em | Data/hora do evento | Data/hora | - | Gerado pelo sistema |
| ip_origem | IP de origem | Texto, 45 | - | IPv4 ou IPv6 |

