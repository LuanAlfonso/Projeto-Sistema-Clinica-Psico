# Modelo Entidade Relacionamento

## Diagrama ER

```mermaid
erDiagram
    USUARIO {
        int id_usuario PK
        string nome
        string email
        string senha_hash
        string telefone
        string status
        datetime criado_em
    }

    PERFIL_ACESSO {
        int id_perfil PK
        string nome
        string descricao
    }

    PACIENTE {
        int id_paciente PK
        int id_usuario FK
        date data_nascimento
        string cpf
        string contato_emergencia
        string observacoes_administrativas
    }

    PSICOLOGO {
        int id_psicologo PK
        int id_usuario FK
        string crp
        string especialidades
        string minibio
        string modalidade_atendimento
    }

    AGENDA {
        int id_agenda PK
        int id_psicologo FK
        string dia_semana
        time hora_inicio
        time hora_fim
        int duracao_padrao_min
        boolean ativo
    }

    CONSULTA {
        int id_consulta PK
        int id_paciente FK
        int id_psicologo FK
        datetime data_hora_inicio
        datetime data_hora_fim
        string modalidade
        string status_consulta
        string status_confirmacao
    }

    NOTIFICACAO {
        int id_notificacao PK
        int id_consulta FK
        string canal
        string status_envio
        datetime enviar_em
        datetime enviado_em
    }

    PRONTUARIO {
        int id_prontuario PK
        int id_paciente FK
        int id_psicologo_responsavel FK
        datetime criado_em
        string status
    }

    EVOLUCAO {
        int id_evolucao PK
        int id_prontuario FK
        int id_consulta FK
        int id_psicologo_autor FK
        text descricao
        datetime criado_em
        datetime atualizado_em
    }

    PAGAMENTO {
        int id_pagamento PK
        int id_consulta FK
        int id_paciente FK
        decimal valor
        string forma_pagamento
        string status_pagamento
        date vencimento
        datetime pago_em
    }

    AUDITORIA {
        int id_auditoria PK
        int id_usuario FK
        string acao
        string entidade
        int id_entidade
        datetime criado_em
        string ip_origem
    }

    USUARIO }o--|| PERFIL_ACESSO : possui
    PACIENTE ||--|| USUARIO : referencia
    PSICOLOGO ||--|| USUARIO : referencia
    PSICOLOGO ||--o{ AGENDA : configura
    PACIENTE ||--o{ CONSULTA : agenda
    PSICOLOGO ||--o{ CONSULTA : atende
    CONSULTA ||--o{ NOTIFICACAO : gera
    PACIENTE ||--o{ PRONTUARIO : possui
    PSICOLOGO ||--o{ PRONTUARIO : responsavel
    PRONTUARIO ||--o{ EVOLUCAO : contem
    CONSULTA ||--o| EVOLUCAO : origina
    CONSULTA ||--o{ PAGAMENTO : possui
    PACIENTE ||--o{ PAGAMENTO : realiza
    USUARIO ||--o{ AUDITORIA : executa
```

## Regras de Relacionamento

- Um usuário possui um perfil de acesso.
- Um paciente referencia um usuário.
- Um psicólogo referencia um usuário.
- Um psicólogo possui uma ou mais agendas.
- Uma consulta pertence a um paciente e a um psicólogo.
- Uma consulta pode gerar notificações.
- Um paciente pode possuir prontuário por psicólogo responsável.
- Uma evolução pertence a um prontuário e pode estar vinculada a uma consulta.
- Uma consulta pode possuir um ou mais registros de pagamento.
- A auditoria registra ações sensíveis executadas por usuários.

