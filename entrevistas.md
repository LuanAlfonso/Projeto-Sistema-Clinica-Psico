
## 🎙️ Documentação das Entrevistas de Levantamento

Para o levantamento de requisitos, foram realizadas duas entrevistas semiestruturadas com perfis distintos para cobrir tanto as necessidades administrativas quanto as clínicas.

### 1. Descrição das Entrevistas

#### **Entrevista 01: Perspectiva Administrativa e Operacional**
* **Entrevistado:** Mariana Souza
* **Função:** Secretária e Recepcionista
* **Resumo do Relato:** Mariana destacou que o maior problema atual é o "no-show" (pacientes que faltam sem avisar). Ela gasta cerca de 3 horas por dia mandando mensagens manuais no WhatsApp para confirmar horários. Além disso, o controle de quem pagou a sessão é feito em uma planilha separada, o que gera erros de cobrança e esquecimentos.

#### **Entrevista 02: Perspectiva Clínica e de Especialista**
* **Entrevistado:**  Pedro Cotrim
* **Função:** Psicólogo Clínico 
* **Resumo do Relato:** Ricardo enfatizou a necessidade absoluta de sigilo. Ele deseja um prontuário onde possa escrever a evolução das sessões de forma rápida, mas que garanta que ninguém da recepção consiga ler o conteúdo. Ele também mencionou o desejo de acessar o histórico do paciente via tablet ou celular quando estiver fora do consultório.

---

### 2. Síntese dos Requisitos das Entrevistas

Após a análise das transcrições, os requisitos foram sintetizados nos seguintes pontos focais:

#### **A. Automatização de Comunicação (Foco: Eficiência)**
* **Necessidade:** Reduzir o trabalho manual da recepção.
* **Requisito Gerado:** O sistema deve enviar lembretes automáticos com botões de "Confirmar" ou "Remarcar" que atualizam a agenda em tempo real.

#### **B. Gestão Financeira Integrada (Foco: Controle)**
* **Necessidade:** Unificar agenda e pagamento.
* **Requisito Gerado:** O sistema deve permitir vincular o status de "Sessão Realizada" ao status de "Pagamento Pendente/Concluído", gerando alertas de inadimplência.

#### **C. Segregação de Níveis de Acesso (Foco: Segurança/LGPD)**
* **Necessidade:** Proteger a intimidade do paciente.
* **Requisito Gerado:** Implementação de perfis de acesso distintos. O perfil "Recepção" visualiza apenas horários e dados cadastrais. O perfil "Psicólogo" possui acesso exclusivo e criptografado ao módulo de prontuário.

#### **D. Portabilidade e Disponibilidade (Foco: Mobilidade)**
* **Necessidade:** Consulta de informações fora da estação fixa de trabalho.
* **Requisito Gerado:** A interface deve ser responsiva (Web) para permitir o uso em dispositivos móveis (Tablets/Smartphones) sem perda de funcionalidade.

---