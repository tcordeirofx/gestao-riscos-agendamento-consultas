# Etapa 1 — Identificação de Riscos

Riscos identificados a partir do cenário do projeto (app de agendamento de consultas médicas), com apoio de LLM e revisão do gerente de projetos. A análise se limita às informações fornecidas no cenário; itens inferidos estão sinalizados como **suposição a validar**.

---

## R01 — Instabilidade na integração com o sistema externo de prontuário

- **Descrição:** a integração com o prontuário eletrônico apresenta falhas recorrentes, causadas pela ausência de documentação clara da API e por mudanças recentes no sistema do fornecedor, feitas sem aviso prévio.
- **Contexto de ocorrência:** a cada ciclo de desenvolvimento ou teste que dependa da API externa; a cada atualização do sistema do fornecedor. Como a integração é crítica para a entrega, o risco pode se manifestar até a implantação em produção.

## R02 — Mudança de requisitos no fluxo de agendamento (scope creep)

- **Descrição:** stakeholders estão solicitando alterações em requisitos já definidos — novas validações e regras de negócio — com o projeto em fase intermediária e parte das funcionalidades já implementadas, o que gera retrabalho e aumento não planejado de escopo.
- **Contexto de ocorrência:** a cada nova solicitação aprovada sem avaliação formal de impacto em prazo, esforço e custo; agrava-se pela ausência (não confirmada) de um processo de controle de mudanças — **suposição a validar**.

## R03 — Sobrecarga e possível esgotamento da equipe

- **Descrição:** a equipe (4 desenvolvedores e 1 tester) já relata aumento de carga de trabalho e dificuldade para cumprir prazos. A combinação de retrabalho da integração instável com o escopo adicional pode evoluir para queda de produtividade, erros por pressa e esgotamento (burnout).
- **Contexto de ocorrência:** períodos de acúmulo simultâneo de correções da integração, novas demandas de escopo e prazos originais mantidos.

## R04 — Gargalo de testes e queda da cobertura de qualidade

- **Descrição:** com apenas 1 tester para 4 desenvolvedores, a etapa de testes tende a virar gargalo. Sob pressão de prazo, testes de regressão e de integração podem ser reduzidos ou pulados, elevando a chance de defeitos chegarem à produção.
- **Contexto de ocorrência:** fechamento de ciclos/releases, especialmente quando quebras na integração externa exigem regressão repetida das mesmas funcionalidades.

## R05 — Atraso na entrega do projeto

- **Descrição:** o efeito combinado dos riscos R01 a R04 pode tornar os prazos inicialmente estimados inviáveis, comprometendo o cronograma acordado com os stakeholders.
- **Contexto de ocorrência:** marcos intermediários e data de entrega final; torna-se mais provável a cada semana em que integração instável e mudanças de escopo coexistem sem repriorização.

## R06 — Tratamento inadequado de dados sensíveis de saúde (suposição a validar)

- **Descrição:** o sistema integra-se a prontuários e lida com dados de pacientes, potencialmente dados sensíveis de saúde protegidos pela LGPD. Falhas de segurança ou uso de dados reais em ambientes de teste podem gerar impacto legal e reputacional. Este risco não está descrito explicitamente no cenário — foi inferido a partir do domínio (saúde) e precisa ser validado com a equipe e os stakeholders.
- **Contexto de ocorrência:** troca de dados com o sistema de prontuário, ambientes de desenvolvimento/teste e eventuais incidentes de segurança.

---

## Observação sobre interdependência

Os riscos não são isolados: **R01 (integração instável)** gera retrabalho que alimenta **R03 (sobrecarga)** e **R04 (gargalo de testes)**; **R02 (scope creep)** amplifica os dois; e todos convergem para **R05 (atraso)**. Essa cadeia causal orienta a priorização feita na Etapa 2.
