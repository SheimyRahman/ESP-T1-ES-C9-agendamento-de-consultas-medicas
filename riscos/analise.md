# 2. Análise Qualitativa de Riscos

## Análise Estruturada

### R1. Instabilidade e Mudanças na API Externa do Prontuário (PEP)
* **Descrição:** A API do sistema de prontuário externo apresenta oscilações, falta de documentação organizada e clara, alem de mudanças não notificadas pelo fornecedor.
* **Impactos Potenciais:** Risco severo de indisponibilidade do serviço principal de agendamento, falha na verificação de histórico clínico/elegibilidade e possibilidade de agendamentos duplicados ou conflitantes para um mesmo cliente inclusive.
* **Fatores Condicionantes:** Dependência direta de um sistema legado de terceiros, ausência de contrato de SLA com garantia de disponibilidade e falta de testes integrados no ambiente do fornecedor.
* **Classificação:**
  * **Probabilidade:** Alta
  * **Impacto:** Alto
  * **Justificativa:** A funcionalidade de integração é crítica para o funcionamento do produto. Sem ela, o core da aplicação fica comprometido.

---

### R2. Volatilidade e Aumento Incontrolado de Escopo (Scope Creep)
* **Descrição:** Solicitação contínua de novas validações e regras de negócio para o fluxo de agendamento pelos stakeholders com o projeto em andamento.
* **Impactos Potenciais:** Aumento de custos, atrasos diretos no cronograma oficial de lançamento e necessidade de retrabalho em módulos já homologados.
* **Fatores Condicionantes:** Mudanças nas necessidades de negócio durante a fase intermediária e ausência de um processo formal de controle de mudanças com aprovação prévia de impacto.
* **Classificação:**
  * **Probabilidade:** Alta
  * **Impacto:** Médio
  * **Justificativa:** Solicitações constantes sem reavaliação de prazo e custo pressionam a entrega do MVP.

---

### R3. Gargalo de Validação e Qualidade (Capacidade de QA)
* **Descrição:** Desproporção na estrutura do time (4 desenvolvedores para 1 tester) diante de múltiplas regras de negócio e instabilidades externas.
* **Impactos Potenciais:** Acúmulo de demandas na fila de QA, testes incompletos e risco elevado de envio de software com bugs críticos para os usuários finais.
* **Fatores Condicionantes:** Capacidade limitada de 1 único profissional de QA e necessidade de testes manuais exaustivos devido à volatilidade das regras.
* **Classificação:**
  * **Probabilidade:** Alta
  * **Impacto:** Alto
  * **Justificativa:** A validação de fluxos críticos é indispensável para evitar falhas graves na experiência do paciente.

---

### R4. Sobrecarga e Risco de Esgotamento da Equipe Técnica
* **Descrição:** Pressão no time por prazos associada a desvios de estimativas causados por retrabalho e integrações instáveis.
* **Impactos Potenciais:** Redução na produtividade, queda na qualidade do código entregue, faltas e alto risco de rotatividade/esgotamento (burnout).
* **Fatores Condicionantes:** Acúmulo de requisitos e pressão para cumprir as datas iniciais sem revisão formal da capacidade da equipe.
* **Classificação:**
  * **Probabilidade:** Média
  * **Impacto:** Alto
  * **Justificativa:** A perda de profissionais durante a fase intermediária paralisaria o desenvolvimento por tempo indeterminado.

---

### R5. Exposição e Inconformidade no Tratamento de Dados Sensíveis (LGPD)
* **Descrição:** Risco de vazamento ou gravação indevida de informações de saúde de pacientes durante a troca de dados entre o app e o PEP.
* **Impactos Potenciais:** Penalidades legais por infração à LGPD, multas financeiras e danos graves à reputação da clínica.
* **Fatores Condicionantes:** Falta de mecanismos de sanitização/mascaramento de dados em ambientes de desenvolvimento e logs de teste.
* **Classificação:**
  * **Probabilidade:** Baixa
  * **Impacto:** Alto
  * **Justificativa:** Incidentes com dados de saúde possuem impacto reputacional e financeiro irreversíveis.

---

## Matriz Qualitativa de Riscos

| Probabilidade \ Impacto | Baixo | Médio | Alto |
| :--- | :--- | :--- | :--- |
| **Alta** | | R2 (Escopo) | R1 (PEP), R3 (QA) |
| **Média** | | | R4 (Equipe) |
| **Baixa** | | | R5 (LGPD) |
