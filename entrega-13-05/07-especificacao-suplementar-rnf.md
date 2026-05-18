# Especificação Suplementar de Requisitos Não Funcionais

Referência de qualidade: ISO/IEC 25010.

## 1. Adequação Funcional

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-AF01 | O sistema deve manter coerência entre agenda, pagamento e prontuário. | Uma consulta realizada deve poder ser vinculada a pagamento e evolução clínica. |
| RNF-AF02 | Funcionalidades devem respeitar o perfil do usuário. | Usuário da recepção não visualiza prontuário. |

## 2. Eficiência de Desempenho

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-ED01 | A agenda diária deve carregar em até 2 segundos em condições normais de uso. | Teste com volume estimado de 50 consultas por dia. |
| RNF-ED02 | Consultas de histórico clínico devem retornar em até 3 segundos. | Considerando paciente com até 200 evoluções. |

## 3. Compatibilidade

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-CM01 | O sistema deve funcionar nos navegadores modernos mais utilizados. | Chrome, Edge, Firefox e Safari atuais. |
| RNF-CM02 | O envio de notificação deve suportar integração por e-mail e WhatsApp. | Falha em um canal não pode corromper o agendamento. |

## 4. Usabilidade

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-US01 | A interface deve ser responsiva para desktop, tablet e celular. | Telas principais sem perda de função em largura móvel. |
| RNF-US02 | Status de consulta e pagamento devem ser visualmente distinguíveis. | Usuário identifica pendências sem abrir detalhes. |
| RNF-US03 | Formulários devem apresentar mensagens claras de validação. | Campos obrigatórios indicados antes de salvar. |

## 5. Confiabilidade

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-CF01 | O sistema deve evitar conflito de horários. | Duas consultas ativas não ocupam o mesmo profissional, data e horário. |
| RNF-CF02 | Falhas no envio de notificação devem ser registradas. | Consulta permanece íntegra e notificação aparece como pendente ou falha. |
| RNF-CF03 | Dados críticos devem possuir backup periódico. | Backup diário para dados operacionais e clínicos. |

## 6. Segurança

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-SG01 | O sistema deve autenticar usuários antes do acesso. | Nenhum módulo interno acessível sem login. |
| RNF-SG02 | O sistema deve aplicar autorização por perfil. | Permissões validadas no servidor, não apenas na interface. |
| RNF-SG03 | Dados sensíveis devem ser criptografados em trânsito e em repouso. | Uso de HTTPS e proteção de dados clínicos armazenados. |
| RNF-SG04 | Acesso ao prontuário deve ser limitado ao psicólogo responsável. | Tentativas indevidas devem ser negadas e auditadas. |
| RNF-SG05 | O sistema deve registrar auditoria de ações sensíveis. | Login, acesso ao prontuário, edição de evolução e pagamento. |

## 7. Manutenibilidade

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-MN01 | Regras de negócio devem estar documentadas e rastreáveis. | Matriz de rastreabilidade atualizada. |
| RNF-MN02 | O sistema deve separar módulos administrativos e clínicos. | Permite manutenção sem misturar responsabilidades. |

## 8. Portabilidade

| ID | Requisito | Critério |
| :--- | :--- | :--- |
| RNF-PT01 | O sistema deve ser acessível por navegador web. | Não exigir instalação de aplicativo nativo. |
| RNF-PT02 | A interface deve adaptar-se a diferentes resoluções. | Layout usável em celular, tablet e desktop. |

