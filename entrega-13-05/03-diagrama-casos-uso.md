# Diagrama de Casos de Uso

## Atores

| Ator | Descrição |
| :--- | :--- |
| Paciente | Pessoa atendida pela clínica que agenda, confirma, remarca ou cancela consultas. |
| Recepção | Usuário administrativo que gerencia agenda, cadastro e pagamentos. |
| Psicólogo | Profissional que atende pacientes, acompanha agenda e registra prontuários. |
| Administrador | Usuário responsável por configurações, perfis e relatórios. |
| Serviço de Notificação | Integração externa para envio de WhatsApp ou e-mail. |

## Diagrama

```mermaid
flowchart LR
    Paciente["Paciente"]
    Recepcao["Recepção"]
    Psicologo["Psicólogo"]
    Administrador["Administrador"]
    Notificacao["Serviço de Notificação"]

    subgraph Sistema["Sistema Clínica Psico"]
        UC01["Agendar consulta"]
        UC02["Remarcar consulta"]
        UC03["Cancelar consulta"]
        UC04["Confirmar consulta"]
        UC05["Enviar lembrete automático"]
        UC06["Cadastrar paciente"]
        UC07["Gerenciar agenda"]
        UC08["Registrar prontuário"]
        UC09["Consultar histórico clínico"]
        UC10["Registrar pagamento"]
        UC11["Gerar relatório financeiro"]
        UC12["Gerenciar usuários e permissões"]
        UC13["Consultar perfil do profissional"]
    end

    Paciente --> UC01
    Paciente --> UC02
    Paciente --> UC03
    Paciente --> UC04
    Paciente --> UC13

    Recepcao --> UC01
    Recepcao --> UC02
    Recepcao --> UC03
    Recepcao --> UC06
    Recepcao --> UC07
    Recepcao --> UC10

    Psicologo --> UC07
    Psicologo --> UC08
    Psicologo --> UC09

    Administrador --> UC11
    Administrador --> UC12

    UC01 --> UC05
    UC02 --> UC05
    UC05 --> Notificacao
```

## Observações

- O caso "Enviar lembrete automático" é acionado pelo agendamento ou remarcação.
- O prontuário não é acessível pela recepção.
- O administrador gerencia permissões, mas o acesso ao conteúdo clínico deve respeitar regras de autorização e responsabilidade profissional.

