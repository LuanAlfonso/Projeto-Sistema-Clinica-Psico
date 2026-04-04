## 🔍 Análise de Sistema Análogo (Doctoralia)

Abaixo estão os requisitos levantados e adaptados a partir da análise da plataforma Doctoralia, servindo como base para o desenvolvimento do sistema clínico.

### 1. Requisitos Funcionais (RF)
* **Perfil Público do Profissional:** Possibilidade de exibir especialidades (ex: TCC, Psicanálise), fotos do consultório e mini-currículo.
* **Agenda On-line em Tempo Real:** Visualização de horários disponíveis e marcação direta pelo paciente, sem necessidade de intermédio humano inicial.
* **Sistema de Confirmação Automática:** Envio de mensagens (WhatsApp/E-mail) solicitando que o paciente confirme ou cancele a presença, atualizando o status na agenda automaticamente.
* **Gestão de Avaliações/Feedback:** Espaço para pacientes deixarem depoimentos sobre o atendimento (seguindo o código de ética da psicologia).
* **Filtros de Busca Avançados:** Busca por convênio, preço, modalidade (presencial ou online) e sintomas/especialidades.
* **Telemedicina Integrada:** Ferramenta de videochamada própria ou integração com plataformas seguras para sessões online.

### 2. Requisitos Não Funcionais (RNF)
* **Usabilidade Mobile-First:** Interface intuitiva para dispositivos móveis, facilitando o agendamento rápido pelo paciente.
* **Disponibilidade:** O sistema deve estar operacional 24/7 para permitir marcações a qualquer momento.
* **Escalabilidade:** Capacidade de suportar o aumento no volume de profissionais e pacientes sem perda de desempenho.
* **Segurança de Dados:** Utilização de criptografia na transmissão de todas as informações de agendamento.

### 3. Adaptações Necessárias (Foco em Psicologia)
Diferente dos sistemas médicos genéricos, o projeto foca em lacunas críticas para o atendimento terapêutico:

* **Prontuário Estruturado:** Implementação de um módulo robusto para a evolução das sessões, garantindo profundidade clínica.
* **Controle de Pagamentos Recorrentes:** Suporte para configuração de "pacotes de sessões" e mensalidades, refletindo a natureza semanal da terapia.
* **Conformidade Estrita com LGPD:** Tratamento rigoroso de dados sensíveis de saúde mental, incluindo a anonimização de dados para fins estatísticos.


> **Síntese dos Requisitos do Sistema Análogo:**
> "Através da análise do sistema Doctoralia, identificou-se a necessidade de uma interface de agendamento simplificada e autônoma para o paciente. O requisito de confirmação automática de consulta foi extraído como funcionalidade crítica para reduzir a taxa de faltas. Contudo, observou-se a lacuna na gestão financeira de mensalidades, requisito este que será personalizado para a realidade das clínicas de psicologia no sistema proposto."