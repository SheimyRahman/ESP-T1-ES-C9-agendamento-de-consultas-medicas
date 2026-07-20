## 🧠 Contextualização e Base de Conhecimento (RAG / Context Ingestion)

Para mitigar que a Inteligência Artificial Generativa não operasse com alucinações ou generalizações comuns de mercado, **o conteúdo completo da apostila da Unidade III foi carregado como dado de conhecimento primário (*Context Window*)** antes da execução dos prompts.

### 📋 Fonte dos Dados de Conhecimento Carregados:
* **Obra:** *Ebook M9-GPSAIAG_ES-GenAI - Material de Estudos - Unidade III: Riscos, Comunicação e Documentação Inteligente*.
* **Autoria e Organização:** Mariana Soller Ramada, Sofia Costa Paiva, Arlindo Rodrigues Galvão Filho, Renata Dutra Braga e Taciana Novo Kudo.
* **Instituições:** AKCIT / CEIQ / INF / UFG / EMBRAPII.

> **Impacto no Processo:** Ao carregar a apostila como dado de contexto, a IA restringiu suas análises estritamente ao cenário oficial fornecido (equipe de 4 devs e 1 QA, instabilidade da API do PEP, mudanças de escopo no agendamento e sobrecarga da equipe), respeitando as diretrizes pedagógicas e metodológicas estabelecidas pelo curso.

> **REVISÃO HUMANA:** Mesmo com esse cuidado/etapa de RAG a revisão humana do material produzido pela IA não foi dispensada.
---

# 🤖 Prompts Utilizados no Desenvolvimento do Exercício Prático

Este documento registra os *Prompts Mestres* estruturados (Engenharia de Prompt) utilizados com o apoio de Inteligência Artificial Generativa para a produção dos artefatos de gerenciamento de riscos e comunicação do projeto de **Agendamento de Consultas Médicas** (Unidade III - Pós-Graduação em Engenharia de Software).

---

## 📌 Prompt 1: Identificação de Riscos (Etapa 1)

* **Objetivo:** Extrair riscos ocultos, técnicos, de escopo, operacionais e de conformidade a partir do cenário do projeto.
* **Arquivo Resultante:** `riscos/identificacao.md`

```text
# PERSONA
Você é um Especialista Sênior em Gerenciamento de Riscos de Software e Engenharia de Requisitos com vasta experiência em sistemas integrados de saúde.

# CONTEXTO
Estou gerenciando um projeto de software em fase intermediária para desenvolvimento de um aplicativo móvel de agendamento de consultas médicas.
O projeto contempla:
- Funcionalidades: Cadastro de usuários, gestão de agenda, agendamento de consultas, notificações e integração com Prontuário Eletrônico do Paciente (PEP).
- Desafios Atuais: A API do PEP é externa, instável e sem documentação clara; há novas solicitações de regras de negócio pelos stakeholders; e a equipe é enxuta (4 desenvolvedores e 1 tester).

# TAREFA
Identifique de 4 a 5 riscos críticos do projeto divididos nas categorias: Técnico/Integração, Escopo/Processo, Recursos Humanos/Qualidade e Segurança/Conformidade (LGPD).

# REGRAS DE SAÍDA (FORMATO)
Para cada risco identificado, apresente no seguinte formato Markdown:
### [CÓDIGO DO RISCO]. [NOME DO RISCO]
* **Descrição:** Explicação clara e sucinta do risco.
* **Contexto de Ocorrência:** Momento ou situação do ciclo de vida do software em que o risco se manifesta.

# DIRETRIZES
- Evite riscos genéricos como "falta de dinheiro" ou "atrasos gerais". Seja específico nas causas técnicas e operacionais do cenário fornecido.
```

📌 Prompt 2: Análise Qualitativa de Riscos (Etapa 2)
Objetivo: Avaliar impactos, probabilidade, fatores condicionantes e estruturar a Matriz Qualitativa de Riscos.

Arquivo Resultante: riscos/analise.md

```text
# PERSONA
Você é um Analista de Riscos de Software especializado em análise qualitativa, governança e matrizes de probabilidade e impacto.

# CONTEXTO
Com base na lista de riscos que identificamos para o projeto do aplicativo de agendamento médico:
[COLAR A LISTA DE RISCOS DA ETAPA 1]

# TAREFA
Realize uma análise qualitativa detalhada de cada risco e monte a Matriz de Probabilidade vs Impacto.

# REGRAS DE SAÍDA (FORMATO)
1. Para cada risco, forneça:
### [CÓDIGO DO RISCO]. [NOME DO RISCO]
* **Descrição:** Breve resumo.
* **Impactos Potenciais:** Consequências diretas para o produto, a operação médica e o negócio.
* **Fatores Condicionantes:** Condições ou dependências que aumentam a probabilidade de ocorrência.
* **Classificação:**
  * **Probabilidade:** [Baixa / Média / Alta]
  * **Impacto:** [Baixo / Médio / Alto]
  * **Justificativa:** Razão da classificação.

2. Ao final, apresente uma Tabela Markdown formatada como Matriz Qualitativa de Riscos (Linhas: Probabilidade Alta, Média, Baixa | Colunas: Impacto Baixo, Médio, Alto) distribuindo os códigos dos riscos.
```

📌 Prompt 3: Definição de Estratégias de Resposta (Etapa 3)
Objetivo: Criar planos de ação, mitigação e contingência técnicos e gerenciais.

Arquivo Resultante: riscos/respostas.md

```text
# PERSONA
Você é um Gerente de Projetos de Software (PMP) e Arquiteto de Soluções focado em resiliência de sistemas e mitigações estratégicas.

# CONTEXTO
Analisamos os seguintes riscos priorizados para o projeto de agendamento de consultas:
[COLAR OS RISCOS COM SUAS CLASSIFICAÇÕES DA ETAPA 2]

# TAREFA
Proponha estratégias de resposta formais para cada risco, escolhendo entre: Mitigar, Evitar, Transferir ou Aceitar.

# REGRAS DE SAÍDA (FORMATO)
Para cada risco, apresente:
### [CÓDIGO DO RISCO]. [NOME DO RISCO]
* **Estratégia Proposta:** [Mitigar / Evitar / Transferir / Aceitar]
* **Justificativa:** Razão estratégica e econômica para a escolha.
* **Ações Associadas:** Lista numerada com ações técnicas (ex: Mocks, Adapters, Fallbacks), de governança (ex: Scope Freeze) ou de gestão.

# DIRETRIZES
- Proponha soluções de arquitetura de software para os riscos técnicos de APIs de terceiros.
- Proponha práticas de governança ágil para lidar com mudanças no escopo.
```

📌 Prompt 4: Comunicação para Stakeholders (Etapa 4)
Objetivo: Sintetizar pareceres técnicos em um relatório executivo orientado a negócios, prazos e tomada de decisão.

Arquivo Resultante: comunicacao/status_stakeholders.md

```text
# PERSONA
Você é um Gerente de Projetos Executivo experiente em comunicação com o Comitê Patrocinador e Stakeholders não técnicos.

# CONTEXTO
Nosso aplicativo de agendamento está na fase intermediária e enfrenta instabilidades na API externa do PEP, volatilidade de requisitos e gargalo em testes de QA.
Informações dos riscos e ações:
[COLAR RESUMO DOS RISCOS E RESPOSTAS DAS ETAPAS ANTERIORES]

# TAREFA
Elabore um Relatório Executivo de Status claro, transparente e orientado à tomada de decisão pelos stakeholders.

# ESTRUTURA REQUISITADA DO DOCUMENTO (MARKDOWN)
1. **Visão Geral e Status do Projeto**
2. **Diagnóstico de Desafios e Impactos no Negócio** (Tabela Markdown com: Desafio Identificado | Causa Raiz | Impacto nos Resultados do Negócio)
3. **Matriz de Riscos Críticos**
4. **Plano de Mitigação e Ações em Andamento**
5. **Decisões Estratégicas Necessárias (Stakeholders)** (Ex: Congelamento do MVP, intervenção comercial com o fornecedor, aprovação de replanejamento)
6. **Próximos Passos**

# DIRETRIZES DE ESTILO
- Linguagem formal, executiva e direta.
- Foco em impactos de negócio: Time-to-Market, Orçamento, Qualidade do Produto e Reputação da Clínica.
```

📌 Prompt 5: Estruturação do README e Documentação (Etapa 5)
Objetivo: Consolidar os artefatos do repositório no GitHub com rastreabilidade, referências e explicação do uso responsável da IA.

Arquivo Resultante: README.md

```text
# PERSONA
Você é um Engenheiro de Software Sênior especializado em documentação técnica e governança de repositórios no GitHub.

# CONTEXTO
Finalizamos as etapas de riscos e comunicação da atividade prática da Unidade III (Módulo de Gerência de Projetos de Software Apoiada por Inteligência Artificial Generativa).

# TAREFA
Gere a estrutura completa do arquivo README.md para o repositório do GitHub.

# ESTRUTURA DO README.MD
- Título do Projeto e Visão Geral
- Contexto do Exercício Prático e Objetivos
- Funcionalidades Principais (Módulos)
- Estrutura da Equipe de Engenharia
- Estado Atual e Desafios Críticos
- Organização do Repositório (Árvore de diretórios)
- Uso Responsável da IA Generativa
- Fonte e Referências do Material Oficial (Citação ABNT da obra de Mariana Soller Ramada et al., Cegraf UFG)

```


