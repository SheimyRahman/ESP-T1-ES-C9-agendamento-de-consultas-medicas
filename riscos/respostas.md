# 3. Estratégias de Resposta aos Riscos

Este documento apresenta as estratégias planejadas para tratar os riscos mais relevantes do projeto, detalhando a abordagem, a justificativa e as ações associadas para mitigação e contingência.

---

## 1. Estratégias de Resposta por Risco

### R1. Instabilidade e Mudanças na API Externa do Prontuário (PEP)
* **Estratégia Proposta:** **Mitigar (Internamente) e Transferir (Externamente)**
* **Justificativa:** Como a integração é indispensável para o funcionamento da aplicação, não podemos eliminar o risco completamente. A melhor saída é isolar a dependência técnica e cobrar contratualmente o parceiro externo. Uma pessoa do time fica com essa tarefa como main responsibility. 
* **Ações Associadas:**
  1. **Desenvolvimento via *Mocking*:** Criar um servidor com backup simulado da API do PEP para destravar o trabalho do time de desenvolvimento e do QA.
  2. **Implementação de Resiliência no Código:** Adicionar camada de *Adapter* com tratamento de *fallback* e fila assíncrona para registrar o agendamento em caso de oscilação do PEP.
  3. **Escalamento Comercial/Gestão:** Acionar os patrocinadores do projeto para exigir formalmente do fornecedor a entrega da documentação atualizada e garantias de SLA.

---

### R2. Volatilidade e Aumento Incontrolado de Escopo (Scope Creep)
* **Estratégia Proposta:** **Mitigar e Prevenir (Congelamento do MVP)**
* **Justificativa:** O avanço descontrolado de requisitos compromete o prazo e o orçamento do lançamento. É necessário limitar a entrega inicial ao indispensável.
* **Ações Associadas:**
  1. **Instituição do *Scope Freeze*:** Congelar o escopo funcional para a primeira versão (MVP), focando apenas no caminho crítico de agendamento.
  2. **Comitê de Controle de Mudanças:** Definir que qualquer nova regra de negócio solicitada seja registrada em um backlog secundário para implementação na Fase 2.

---

### R3. Gargalo de Validação e Qualidade (Capacidade de QA)
* **Estratégia Proposta:** **Mitigar**
* **Justificativa:** Um único profissional de QA não consegue validar todas as integrações e novas regras manualmente sem virar um gargalo de entregas ou deixar passar bugs graves.
* **Ações Associadas:**
  1. **Automação de Testes pela Engenharia:** Engajar os 4 desenvolvedores na escrita de testes unitários e de integração automatizados.
  2. **Foco no Fluxo Crítico:** Criar uma matriz de testes priorizada baseada nos cenários de maior impacto para o usuário.
  3. **Avaliando *Staff Augmentation*:** Solicitar autorização para alocação temporária de mais 1 profissional de QA durante a janela de homologação.

---

### R4. Sobrecarga e Risco de Esgotamento da Equipe Técnica
* **Estratégia Proposta:** **Aceitar de Forma Consciente e Mitigar via Replanejamento**
* **Justificativa:** O risco não pode ser zerado sem um ajuste realista na capacidade de entrega do time frente aos atrasos e retrabalhos já ocorridos.
* **Ações Associadas:**
  1. **Readequação do Cronograma:** Refazer a estimativa de prazos com a equipe com base na velocidade real de desenvolvimento.
  2. **Priorização Rígida de Sprints:** Proteger o time contra demandas paralelas, focando estritamente nas tarefas planejadas.

---

### R5. Exposição e Inconformidade no Tratamento de Dados Sensíveis (LGPD)
* **Estratégia Proposta:** **Evitar**
* **Justificativa:** Vazamento de dados de saúde acarreta penalidades legais graves, sanções financeiras e perda irreversível de reputação.
* **Ações Associadas:**
  1. **Mascaramento e Anonimização:** Criar rotinas automatizadas para ocultar CPFs, nomes e dados médicos nos logs da aplicação e nos ambientes de teste.
  2. **Revisão de Segurança:** Realizar checklist de conformidade com as diretrizes da LGPD antes da subida em ambiente de produção.

---

## 2. Considerações sobre as Estratégias

* **Trade-offs:** A escolha por congelar o escopo e utilizar mocks acelera o desenvolvimento e protege a equipe, porém exige o adiamento de melhorias desejadas pelos stakeholders para versões futuras.
* **Pontos de Validação:** A estratégia do PEP necessita do apoio direto da diretoria/sponsors para surtir efeito comercial junto ao fornecedor externo.
