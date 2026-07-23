Relatório de status elaborado com apoio de LLM para traduzir a situação técnica do projeto em linguagem de negócio, com foco em tomada de decisão. Público-alvo: sponsors e stakeholders não técnicos.

---

## Relatório de Status — Projeto App de Agendamento de Consultas

**Período:** situação atual | **Preparado por:** Gerência de Projetos

### Resumo executivo

O projeto segue em desenvolvimento ativo, com parte importante das funcionalidades já implementada. Três fatores, porém, estão pressionando o prazo e a qualidade da entrega: a instabilidade do sistema de prontuário do fornecedor externo, o volume de mudanças recentes solicitadas no fluxo de agendamento e o limite de capacidade da equipe atual. **Já iniciamos ações para conter os dois primeiros fatores, mas precisamos de duas decisões desta diretoria para garantir uma entrega previsível.**

### Situação atual

- **Progresso:** cadastro de usuários, gestão de agenda e parte do fluxo de agendamento estão implementados; notificações e a integração com o prontuário estão em andamento.
- **Principal obstáculo:** a conexão com o sistema de prontuário do fornecedor externo vem falhando de forma recorrente. O sistema dele muda sem aviso e a documentação disponível é insuficiente. Cada falha obriga a equipe a refazer trabalho e retestar funcionalidades já prontas — hoje, este é o maior consumidor de tempo do time.
- **Mudanças de escopo:** as melhorias solicitadas recentemente no fluxo de agendamento são bem-vindas do ponto de vista do produto, mas, somadas ao retrabalho da integração, excedem a capacidade da equipe dentro do prazo original.

### Principais riscos para o negócio

1. **Dependência do fornecedor de prontuário** — sem estabilidade ou compromisso formal do parceiro, a data de entrega fica fora do nosso controle direto.
2. **Prazo** — mantidos escopo ampliado e instabilidade atual, o prazo original torna-se inviável sem perda de qualidade.
3. **Sustentabilidade da equipe** — o time (5 pessoas) opera acima da capacidade; a continuidade desse ritmo ameaça qualidade e retenção.

### Ações já em andamento

- Construção de uma "camada de proteção" técnica que isola nosso aplicativo das mudanças do fornecedor e permite que o agendamento continue funcionando mesmo quando o prontuário estiver fora do ar (sincronizando depois).
- Testes simulados da integração, para que o desenvolvimento avance sem depender da estabilidade do parceiro.
- Reforço da qualidade: automação dos testes do fluxo crítico de agendamento e responsabilidade de testes compartilhada por toda a equipe.

### Decisões necessárias

1. **Acionamento formal do fornecedor:** solicitamos apoio da diretoria para exigir contratualmente documentação atualizada, canal de suporte e aviso prévio de mudanças (SLA). Sem isso, seguiremos absorvendo o custo da instabilidade.
2. **Priorização do escopo:** propomos congelar temporariamente as mudanças não essenciais do fluxo de agendamento até a estabilização da integração, reavaliando-as em seguida. Alternativas: estender o prazo ou ampliar a equipe — apresentamos os trade-offs de cada opção na reunião de acompanhamento.

### Próximos passos

- Concluir a camada de proteção da integração (em andamento).
- Reunião com fornecedor externo, com participação do sponsor.
- Replanejamento do cronograma após decisão sobre escopo, com nova data comunicada formalmente.

*Premissas e incertezas: o cenário assume manutenção da equipe atual e resposta do fornecedor em até duas semanas após o acionamento formal. Qualquer alteração será comunicada imediatamente.*
