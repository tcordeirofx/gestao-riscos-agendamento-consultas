# Prompts utilizados

Prompts estruturados (persona, tarefa, contexto, saída, restrições) baseados nos modelos do material da Unidade 3, adaptados ao cenário do projeto. Registrados aqui para rastreabilidade do uso da IA na atividade.

---

## Etapa 1 — Identificação de riscos

> **Persona:** Você atua como um especialista em gerenciamento de riscos em projetos de software, com experiência na identificação de riscos técnicos, organizacionais e de processo, especialmente em contextos de alta incerteza.
>
> **Tarefa:** Identificar possíveis riscos associados ao projeto, com base nas informações fornecidas, considerando fatores que podem impactar o andamento, a qualidade ou os resultados do projeto.
>
> **Contexto:** App móvel de agendamento de consultas médicas (cadastro de usuários, agenda médica, agendamento, notificações, integração com sistema externo de prontuário). Fase intermediária. Desafios recentes: instabilidade na integração com o prontuário (API sem documentação clara, mudanças sem aviso); stakeholders solicitando alterações em requisitos do fluxo de agendamento; equipe relatando aumento de carga de trabalho. Equipe: 4 desenvolvedores e 1 tester. A integração externa é crítica para a entrega. A análise deve se limitar às informações fornecidas e suas implicações diretas.
>
> **Saída:** Para cada risco: Risco (descrição clara), Descrição breve, Contexto de ocorrência.
>
> **Restrições:** Não assumir informações não fornecidas; indicar incertezas ou necessidade de validação; evitar riscos genéricos.

## Etapa 2 — Análise qualitativa

> **Persona:** Você atua como um analista de riscos em projetos de software, com experiência na análise qualitativa de riscos e aplicação de matrizes de probabilidade e impacto.
>
> **Tarefa:** Realizar análise estruturada dos riscos previamente identificados, descrevendo impactos e fatores associados, e organizá-los em uma matriz qualitativa de probabilidade × impacto.
>
> **Saída:** Para cada risco: descrição, possíveis impactos no projeto, fatores que influenciam a ocorrência, probabilidade (Baixa/Média/Alta), impacto (Baixo/Médio/Alto), justificativa da classificação; matriz qualitativa consolidada.
>
> **Restrições:** Não atribuir valores numéricos; indicar incertezas quando necessário.

## Etapa 3 — Estratégias de resposta

> **Persona:** Você atua como um gerente de projetos com experiência em resposta a riscos (evitar, mitigar, transferir e aceitar) em projetos de software.
>
> **Tarefa:** Sugerir possíveis estratégias de resposta para os riscos identificados e analisados, explorando alternativas viáveis e suas implicações, sem realizar escolha definitiva.
>
> **Saída:** Para cada risco: estratégias possíveis (evitar/mitigar/transferir/aceitar), considerações de aplicação e trade-offs, pontos que exigem validação com stakeholders.
>
> **Restrições:** Indicar limitações das sugestões; manter análise exploratória e qualitativa; considerar a restrição real da equipe (4 devs + 1 tester) — não propor soluções inviáveis como contratações imediatas.

## Etapa 4 — Comunicação para stakeholders

> **Persona:** Você atua como gerente de projetos preparando um relatório de status para sponsors e stakeholders não técnicos.
>
> **Tarefa:** A partir da análise de riscos e das estratégias definidas (fornecidas como contexto), estruturar uma narrativa com: contexto, situação atual, riscos em linguagem de negócio, ações em andamento, decisões necessárias e próximos passos.
>
> **Restrições:** Linguagem acessível, sem jargão técnico; foco em tomada de decisão; tom transparente, nem alarmista nem otimista; explicitar premissas e incertezas.

---

## Observação

As saídas do LLM foram tratadas como **rascunho estruturado**: classificação de probabilidade/impacto, priorização e escolha final das estratégias foram revisadas e decididas manualmente. Riscos sugeridos pelo modelo que não se sustentavam no cenário foram descartados; o risco de dados sensíveis (R06) foi mantido, mas sinalizado explicitamente como suposição a validar.
