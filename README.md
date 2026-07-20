# ESP-T1-ES-C9-agendamento-de-consultas-medicas
Repositorio de exercicio do curso de especializacao em IA - Engenharia de Software UFG

# 🏥 Aplicativo Móvel de Agendamento de Consultas Médicas

## 📝 Visão Geral do Projeto
Este repositório reúne a documentação estratégica, a arquitetura de informação e o mapeamento do gerenciamento de riscos do projeto do **Aplicativo Móvel para Agendamento de Consultas Médicas**.

A solução visa conceber e implementar uma plataforma mobile multiplataforma que simplifique a jornada do paciente e do médico no agendamento de consultas e gestão de horários clínicos, garantindo conformidade com a LGPD e sincronia com sistemas externos de saúde.

---

## 🎓 Contexto do Exercício Prático
Este projeto é parte integrante das atividades práticas da **Pós-Graduação em Engenharia de Software** (Módulo de Gerência de Projetos de Software Apoiada por Inteligência Artificial Generativa - Unidade III).

### 🎯 Objetivos do Exercício:
* Utilizar Grandes Modelos de Linguagem (LLMs / IA Generativa) como apoio na **identificação de riscos** em cenários de incerteza.
* Realizar a **análise qualitativa de impactos e fatores condicionantes**.
* Definir **estratégias de resposta** a riscos (mitigação, aceitação, transferência e prevenção).
* Elaborar **relatórios de comunicação executiva** para *stakeholders*.
* Organizar os artefatos técnicos em formato Markdown no GitHub, garantindo rastreabilidade das decisões.

---

## ⚙️ Funcionalidades Principais (Módulos do Sistema)

* **Autenticação e Perfis (Cadastro de Usuários):** Controle de acesso seguro para Pacientes, Médicos e Administradores com criptografia e conformidade com a LGPD.
* **Gestão de Agenda Médica:** Painel dinâmico para os profissionais configurarem seus horários de atendimento, bloqueios de plantão/férias e tempos de consulta.
* **Agendamento de Consultas:** Fluxo intuitivo de seleção de especialidade, médico e horário com validação de concorrência em tempo real.
* **Módulo de Notificações:** Envio de lembretes via *Push Notification* e SMS para redução das taxas de absenteísmo.
* **Integração com Prontuário Eletrônico (PEP):** Sincronização automatizada para verificação de histórico clínico e elegibilidade no momento do agendamento.

---

## 👥 Estrutura da Equipe de Engenharia
O projeto é conduzido por uma equipe enxuta operando sob metodologias ágeis:
* **1 Gerente de Projetos (PM):** Governança, gestão de riscos e comunicação com stakeholders.
* **4 Desenvolvedores de Software:** Construção das camadas mobile, APIs de serviço e esteira CI/CD.
* **1 Engenheiro de Qualidade (QA):** Automação de testes, testes de integração e validação de critérios de aceitação.

---

## 🚩 Estado Atual e Desafios Críticos
O projeto encontra-se na **fase intermediária de desenvolvimento**. Módulos de autenticação e interface base foram validados. Contudo, enfrenta os seguintes desafios críticos:
1. **Instabilidade na Integração Externa (PEP):** Falhas na API do fornecedor por falta de documentação clara e mudanças repentinas.
2. **Volatilidade de Escopo:** Novas solicitações de regras de negócio e validações complexas durante a fase ativa de desenvolvimento.
3. **Capacidade Operacional:** Sobrecarga da equipe (especialmente gargalo no setor de QA) gerando riscos de atraso e redução de qualidade.

---

## 📂 Organização do Repositório

A estrutura de arquivos e pastas segue estritamente as diretrizes estabelecidas na Unidade III:

```text
ESP-T1-ES-C9-agendamento-de-consultas-medicas/
├── README.md                            # Visão geral do projeto e contexto do exercício
├── riscos/
│   ├── identificacao.md                 # Lista e contexto dos riscos mapeados
│   ├── analise.md                       # Análise qualitativa e Matriz Probabilidade x Impacto
│   └── respostas.md                     # Estratégias de resposta, justificativas e planos de ação
└── comunicacao/
    └── status_stakeholders.md           # Relatório de status executivo consolidado
