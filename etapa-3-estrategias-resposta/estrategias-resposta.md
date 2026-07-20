# Etapa 3 — Estratégias de Resposta aos Riscos

Para cada risco priorizado na Etapa 2, foi definida uma estratégia principal (evitar, mitigar, transferir ou aceitar), com justificativa e ações associadas. As alternativas foram exploradas com apoio do LLM; a escolha final é decisão do gerente de projetos, considerando o contexto e as restrições da equipe.

---

## R01 — Instabilidade na integração com o prontuário externo

**Estratégia: Mitigar (técnica) + Transferir (contratual)**

- **Justificativa:** a integração é crítica e não pode ser evitada; aceitá-la passivamente deixaria o cronograma refém de um sistema fora do nosso controle. A resposta atua em duas frentes: reduzir o impacto tecnicamente e transferir ao fornecedor a responsabilidade pelo que só ele pode resolver.
- **Ações:**
  - criar uma **camada de isolamento (adapter)** entre o app e a API externa, de modo que mudanças do fornecedor afetem um único ponto do código;
  - implementar **circuit breaker, retentativas e modo degradado**: se o prontuário estiver indisponível, o agendamento é registrado como pendente e sincronizado depois, em vez de travar o paciente;
  - desenvolver **mocks e testes de contrato** da API, permitindo que a equipe avance sem depender da estabilidade do parceiro;
  - documentar internamente os comportamentos observados da API;
  - **transferir via stakeholders/contrato:** acionar os sponsors para formalizar com o fornecedor SLA, suporte técnico, documentação atualizada e aviso prévio de mudanças.

## R02 — Mudança de requisitos no fluxo de agendamento

**Estratégia: Mitigar (com componente de Evitar para mudanças não essenciais)**

- **Justificativa:** as solicitações vêm de stakeholders legítimos e não devem ser bloqueadas em absoluto, mas precisam deixar de entrar "por fora" do planejamento. Na cadeia causal mapeada nas Etapas 1 e 2, este é o **ponto de intervenção de maior alavancagem**: cada mudança absorvida sem avaliação amplifica simultaneamente a sobrecarga (R03), o gargalo de testes (R04) e o risco de atraso (R05). É também a resposta de menor custo e aplicação mais imediata do plano.
- **Ações:**
  - instituir um **processo leve de controle de mudanças**: toda solicitação passa por avaliação de impacto (prazo, esforço, risco) antes de ser aprovada;
  - negociar um **congelamento parcial de escopo** até a estabilização da integração crítica, adiando mudanças não essenciais para uma fase posterior (evitar);
  - para mudanças essenciais, **devolver a decisão aos stakeholders de forma explícita**: reduzir escopo, ampliar prazo ou aumentar capacidade, com o custo de cada opção quantificado — em vez de a equipe absorver silenciosamente as três pressões;
  - manter um backlog priorizado e visível para os stakeholders, explicitando o custo de cada troca.

## R03 — Sobrecarga e possível esgotamento da equipe

**Estratégia: Mitigar**

- **Justificativa:** o risco humano é o menos reversível — recuperar uma equipe esgotada ou substituir alguém que saiu custa muito mais do que prevenir. Soluções "mágicas" (contratar rapidamente, horas extras contínuas) foram descartadas por inviáveis ou contraproducentes.
- **Ações:**
  - repriorizar o backlog junto aos stakeholders, tornando explícito que prazo original + escopo novo + retrabalho da integração são incompatíveis com a capacidade atual;
  - proteger a equipe de interrupções e demandas paralelas durante a estabilização;
  - monitorar sinais de sobrecarga nas cerimônias do time (não apenas métricas de entrega);
  - se a pressão persistir, escalar formalmente a decisão: reduzir escopo, estender prazo ou ampliar equipe — decisão dos sponsors, com dados.

## R04 — Gargalo de testes e queda da cobertura de qualidade

**Estratégia: Mitigar**

- **Justificativa:** a proporção 4:1 dev/tester é estrutural; sem redistribuir a responsabilidade por qualidade, o gargalo é inevitável.
- **Ações:**
  - adotar **shift-left**: desenvolvedores escrevem e automatizam testes das próprias entregas; o tester foca em cenários exploratórios e de integração;
  - automatizar a **regressão do fluxo crítico de agendamento**, que hoje é retestado a cada quebra da integração;
  - definir critérios de pronto (Definition of Done) que incluam testes, impedindo que a cobertura seja sacrificada silenciosamente sob pressão.

## R05 — Atraso na entrega do projeto

**Estratégia: Mitigar + Aceitar (residual)**

- **Justificativa:** R05 é consequência dos demais; a melhor resposta é tratar as causas (R01–R04). O risco residual de atraso deve ser aceito de forma **transparente e comunicada**, não escondida.
- **Ações:**
  - replanejar o cronograma com base na capacidade real e no cenário da integração;
  - comunicar aos stakeholders o novo cenário com opções e trade-offs (ver Etapa 4);
  - acompanhar semanalmente o risco de prazo com indicadores simples (burndown, pendências da integração).

## R06 — Tratamento inadequado de dados sensíveis de saúde (LGPD)

**Estratégia: Mitigar / Evitar exposição desnecessária**

- **Justificativa:** probabilidade baixa, mas impacto alto e assimétrico — prevenção barata versus incidente muito caro. Parte do risco pode ser simplesmente evitada eliminando exposições desnecessárias.
- **Ações:**
  - validar com a equipe quais dados pessoais transitam pelo sistema e com que finalidade (princípio da minimização);
  - **proibir dados reais de pacientes em desenvolvimento e testes** — usar dados fictícios ou anonimizados (evitar);
  - garantir criptografia em trânsito na integração com o prontuário e revisão de acessos;
  - incluir o tema na pauta com o fornecedor externo (responsabilidade compartilhada no tratamento de dados).

---

## Resumo

| Risco | Estratégia principal | Ação-chave |
|---|---|---|
| R01 | Mitigar + Transferir | Adapter + modo degradado; SLA via sponsors |
| R02 | Mitigar / Evitar | Controle de mudanças; decisão escopo × prazo × capacidade devolvida aos stakeholders |
| R03 | Mitigar | Repriorização com dados; proteção do time |
| R04 | Mitigar | Shift-left e automação de regressão |
| R05 | Mitigar + Aceitar | Replanejamento transparente |
| R06 | Mitigar / Evitar | Sem dados reais em teste; minimização |

**Pontos que exigem validação com stakeholders:** congelamento parcial de escopo (R02), replanejamento de prazo (R05) e acionamento contratual do fornecedor (R01).
