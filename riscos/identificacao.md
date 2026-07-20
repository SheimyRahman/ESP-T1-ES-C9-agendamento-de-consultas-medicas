# 1. Identificação de Riscos

## Contexto do Projeto
O projeto propõe o desenvolvimento de um aplicativo móvel para agendamento de consultas médicas. O sistema abrange desde cadastro de usuários, gestão de agenda e notificações até a integração com prontuário eletrônico externo (PEP). A equipe é composta por 4 desenvolvedores e 1 tester (QA).

---

## Lista de Riscos Identificados

### R1. Instabilidade e Mudanças na API Externa do Prontuário (PEP)
* **Descrição:** O sistema legado de Prontuário Eletrônico do Paciente apresenta instabilidades frequentes, falta de documentação clara e alterações repentinas na API sem aviso prévio pelo fornecedor.
* **Contexto de Ocorrência:** Manifesta-se durante a sincronização dos dados do paciente e na validação de elegibilidade e histórico clínico no momento do agendamento.

### R2. Volatilidade e Aumento Incontrolado de Escopo (Scope Creep)
* **Descrição:** Solicitação de novas regras de negócio e validações complexas pelos stakeholders no fluxo de agendamento durante a execução do projeto.
* **Contexto de Ocorrência:** Ocorre nas reuniões de acompanhamento intermediário e revisão de entregáveis.

### R3. Gargalo de Validação e Qualidade (Capacidade de QA)
* **Descrição:** Incapacidade de realizar testes completos de regressão e validação das novas regras a tempo, devido à presença de apenas 1 tester para 4 desenvolvedores.
* **Contexto de Ocorrência:** Manifesta-se nas etapas de testes de integração, homologação e preparação para liberação da versão.

### R4. Sobrecarga e Risco de Esgotamento da Equipe Técnica
* **Descrição:** Aumento da carga de trabalho e retrabalho decorrentes de alterações de escopo e instabilidades de terceiros, o que gera atrasos nas estimativas iniciais.
* **Contexto de Ocorrência:** Ocorre ao longo do desenvolvimento ativo das sprints e na tentativa de cumprir os prazos acordados.

### R5. Exposição e Inconformidade no Tratamento de Dados Sensíveis (LGPD)
* **Descrição:** Risco de vazamento ou registros inadequados de dados de saúde e identificadores de pacientes em logs de comunicação com o PEP.
* **Contexto de Ocorrência:** Durante as chamadas de integração e persistência de dados em ambientes de desenvolvimento e testes.
