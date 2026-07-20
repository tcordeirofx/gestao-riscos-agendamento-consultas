# Etapa 2 — Análise Qualitativa dos Riscos

Análise estruturada dos riscos identificados na Etapa 1, considerando impactos potenciais e fatores condicionantes. As classificações de probabilidade e impacto são **qualitativas** (Baixa/Média/Alta × Baixo/Médio/Alto) e foram definidas pelo gerente de projetos com apoio do LLM — não são saída direta do modelo.

---

## R01 — Instabilidade na integração com o prontuário externo

- **Possíveis impactos:** bloqueio de funcionalidades críticas (a integração é indispensável para a entrega); retrabalho recorrente; atraso em cascata nas demais frentes; perda de confiança dos stakeholders na previsibilidade do projeto.
- **Fatores que influenciam a ocorrência:** falta de documentação da API; mudanças do fornecedor sem aviso prévio; ausência de ambiente de homologação estável do parceiro; inexistência de acordo formal de SLA/comunicação (**a validar**).
- **Probabilidade:** Alta — as falhas já vêm ocorrendo e as causas (documentação e mudanças sem aviso) seguem presentes.
- **Impacto:** Alto — afeta o núcleo do produto e a data de entrega.

## R02 — Mudança de requisitos no fluxo de agendamento

- **Possíveis impactos:** retrabalho em funcionalidades já implementadas; crescimento de escopo sem replanejamento de prazo; conflito de prioridades dentro da equipe.
- **Fatores que influenciam a ocorrência:** stakeholders ativos e com poder de decisão; projeto em fase intermediária (mudança custa mais); ausência de processo formal de controle de mudanças (**a validar**).
- **Probabilidade:** Alta — as solicitações já estão acontecendo.
- **Impacto:** Médio — gera retrabalho e pressão sobre o cronograma, mas é administrável se houver avaliação de impacto e repriorização.

## R03 — Sobrecarga e possível esgotamento da equipe

- **Possíveis impactos:** queda de produtividade e de qualidade; aumento de defeitos; rotatividade (perda de conhecimento em equipe pequena é especialmente grave); paralisação parcial do projeto.
- **Fatores que influenciam a ocorrência:** equipe enxuta (4 devs + 1 tester); acúmulo de retrabalho (R01) e escopo novo (R02) com prazos originais mantidos; sinais de sobrecarga já relatados.
- **Probabilidade:** Média — a sobrecarga existe; o risco é sua evolução para esgotamento/rotatividade.
- **Impacto:** Alto — em uma equipe de 5 pessoas, perder capacidade de 1 pessoa remove ~20% da força de trabalho.

## R04 — Gargalo de testes e queda da cobertura de qualidade

- **Possíveis impactos:** defeitos em produção num domínio sensível (saúde); ciclos de release mais longos; retrabalho de correção pós-entrega, mais caro que a prevenção.
- **Fatores que influenciam a ocorrência:** proporção 4:1 entre desenvolvedores e tester; regressões repetidas causadas pela integração instável; baixo grau de automação de testes (**a validar**).
- **Probabilidade:** Alta — o desequilíbrio estrutural da equipe torna o gargalo praticamente certo nos picos de entrega.
- **Impacto:** Médio — degrada qualidade e prazo de forma incremental, com potencial de escalar se combinado com R01.

## R05 — Atraso na entrega do projeto

- **Possíveis impactos:** quebra de compromissos com stakeholders e eventuais clínicas/pacientes; custos adicionais; pressão que retroalimenta R03 e R04.
- **Fatores que influenciam a ocorrência:** é o risco-consequência da cadeia R01→R04; probabilidade cresce enquanto os riscos-causa não forem tratados.
- **Probabilidade:** Média — evitável se as respostas da Etapa 3 forem aplicadas cedo.
- **Impacto:** Alto — afeta diretamente o resultado esperado do projeto.

## R06 — Tratamento inadequado de dados sensíveis de saúde (LGPD)

- **Possíveis impactos:** sanções legais, dano reputacional grave e perda de confiança de pacientes e parceiros — impacto desproporcional ao custo de prevenção.
- **Fatores que influenciam a ocorrência:** integração com prontuário; práticas de ambiente de teste ainda não conhecidas (**a validar**); maturidade de segurança do fornecedor externo desconhecida.
- **Probabilidade:** Baixa — sem evidência de exposição atual, mas com incerteza alta por falta de informação.
- **Impacto:** Alto — dados sensíveis de saúde têm proteção reforçada na LGPD.

---

## Matriz Qualitativa de Riscos (Probabilidade × Impacto)

| Probabilidade \ Impacto | Baixo | Médio | Alto |
| ----------------------- | ----- | ----- | ---- |
| **Alta**                |       | R02, R04 | **R01** |
| **Média**               |       |       | R03, R05 |
| **Baixa**               |       |       | R06 |

**Priorização resultante:** R01 é o risco crítico do projeto. R03 e R05 vêm em seguida, seguidos de R02 e R04 (alta frequência, impacto administrável) e R06 (baixa probabilidade, mas impacto alto — exige verificação, não pode ser simplesmente ignorado).

## Incertezas registradas

- Não há informação sobre existência de SLA ou canal formal com o fornecedor do prontuário.
- Não há informação sobre processo de controle de mudanças nem sobre grau de automação de testes.
- O risco R06 depende de confirmação sobre quais dados pessoais transitam pelo sistema e como os ambientes de teste são populados.
