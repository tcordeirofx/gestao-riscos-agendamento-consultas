# Gestão de Riscos e Comunicação com apoio de IA Generativa

Atividade prática do **Curso 9 — Unidade 3 (Riscos, Comunicação e Documentação Inteligente)**.

## Descrição do projeto

O exercício utiliza o cenário proposto no curso: atuo como gerente de projetos responsável pelo desenvolvimento de um **aplicativo móvel de agendamento de consultas médicas**, com funcionalidades de cadastro de usuários, gestão de agenda médica, agendamento de consultas, notificações e integração com um sistema externo de prontuário eletrônico.

O projeto está em fase intermediária de desenvolvimento e enfrenta três desafios recentes:

- instabilidade na integração com o sistema de prontuário, causada pela falta de documentação clara da API e por mudanças recentes no sistema externo;
- solicitações dos stakeholders de alterações em requisitos do fluxo de agendamento (novas validações e regras de negócio);
- aumento da carga de trabalho da equipe, com dificuldade para cumprir os prazos estimados.

Restrições relevantes: a equipe é composta por **4 desenvolvedores e 1 tester**, e a integração com o sistema externo é **crítica** para a entrega.

## Objetivo do exercício

Aplicar Inteligência Artificial Generativa (LLMs) como ferramenta de **apoio** às etapas do gerenciamento de riscos — identificação, análise qualitativa, definição de estratégias de resposta — e à comunicação com stakeholders, mantendo o julgamento e a validação sob responsabilidade do gerente de projetos.

## Organização do repositório

| Pasta | Conteúdo |
|---|---|
| [`etapa-1-identificacao-riscos/`](etapa-1-identificacao-riscos/identificacao-riscos.md) | Lista de riscos identificados, com descrição e contexto de ocorrência |
| [`etapa-2-analise-riscos/`](etapa-2-analise-riscos/analise-riscos.md) | Análise qualitativa (impactos, fatores condicionantes) e matriz probabilidade × impacto |
| [`etapa-3-estrategias-resposta/`](etapa-3-estrategias-resposta/estrategias-resposta.md) | Estratégia de resposta para cada risco (evitar, mitigar, transferir, aceitar), com justificativa e ações |
| [`etapa-4-comunicacao-stakeholders/`](etapa-4-comunicacao-stakeholders/comunicacao-stakeholders.md) | Relatório de status para stakeholders, em linguagem de negócio |
| [`prompts/`](prompts/prompts-utilizados.md) | Prompts estruturados utilizados com o LLM em cada etapa |

## Nota sobre o uso de IA

Os artefatos foram produzidos em **fluxo agêntico** com um LLM (Claude, via Claude Code), a partir do material do curso e dos prompts estruturados registrados em [`prompts/`](prompts/prompts-utilizados.md). A revisão humana concentrou-se na camada de decisão: validação dos riscos frente ao cenário, comparação com outras análises do mesmo caso e escolha da estratégia priorizada — inclusive com redirecionamento da estratégia destacada após a revisão (ver histórico de commits). Nenhum dado real ou sensível foi utilizado.
