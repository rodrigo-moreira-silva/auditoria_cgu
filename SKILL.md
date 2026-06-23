---
name: cgu-auditoria
description: >
  Analisa artefatos de auditoria da CGU (relatórios, seções, achados, recomendações,
  introduções, conclusões, matrizes de planejamento e achados) verificando conformidade
  com as normas internas da CGU: MOT 2017, OP 2019 e Metodologia de Riscos 2.0.
  Use esta skill sempre que o usuário pedir para revisar, validar, analisar ou avaliar
  qualquer artefato de auditoria da CGU — mesmo que use palavras como "checar",
  "conferir", "está certo?", "está conforme?", "me dá um feedback", "revisa isso",
  ou quando colar trechos de relatório pedindo opinião. Também deve ser usada quando
  o usuário pedir para redigir ou corrigir qualquer seção de relatório CGU, pois a
  norma deve guiar a produção. Acione sempre que houver menção a: Introdução do
  relatório, achados, critério/condição/causa/consequência, recomendações, conclusão,
  resumo (highlight), matriz de planejamento, matriz de achados, questões de auditoria,
  escopo, CGU, UAIG, SFC, relatório de auditoria.
---

# Skill: Análise de Conformidade de Artefatos de Auditoria CGU

## Objetivo

Verificar se artefatos de auditoria da CGU estão em conformidade com as normas
internas vigentes, apontando divergências, lacunas e pontos de melhoria com base
nos documentos normativos da organização.

---

## Arquivos de Referência

Os arquivos de norma estão divididos por tema em `references/`. **Leia apenas os
arquivos relevantes para o artefato em análise** — não carregue todos de uma vez.
Use a tabela abaixo para decidir quais ler.

> **Importante:** as normas são complementares. A OP 2019 detalha e operacionaliza
> o MOT 2017. Em caso de aparente conflito, a OP 2019 prevalece para questões de
> elaboração do relatório.

> **Arquivo obrigatório em todas as análises:** carregue sempre `references/op_apendice_gramatica.md`
> (falhas gramaticais comuns nos relatórios — apêndice F da OP 2019), independentemente
> do tipo de artefato. Ele deve ser consultado em qualquer análise que envolva texto redigido.

### Mapeamento artefato → arquivos a ler

| Artefato | Arquivos obrigatórios | Arquivos complementares |
|---|---|---|
| **Capa / Folha de rosto / Missão** | `op_capa_folha_missao.md` | `op_aspectos_formais.md` |
| **Lista de siglas / Sumário** | `op_siglas_sumario.md` | `op_aspectos_formais.md` |
| **Resumo / Highlight** | `op_resumo.md` | `op_qualidade.md` |
| **Introdução** | `op_introducao.md`, `mot_estrutura_relatorio.md` | `op_qualidade.md`, `mot_qualidade.md` |
| **Achado** (completo) | `op_achados.md`, `mot_achados.md` | `op_causa_raiz.md`, `op_qualidade.md` |
| **Recomendações** | `op_recomendacoes.md`, `mot_recomendacoes.md` | — |
| **Manifestação da unidade auditada** | `op_anexos_relatorio.md`, `mot_manifestacao_unidade.md` | — |
| **Conclusão** | `op_conclusao.md`, `mot_estrutura_relatorio.md` | `op_qualidade.md` |
| **Anexos do relatório** | `op_anexos_relatorio.md` | — |
| **Matriz de Planejamento** | `op_matrizes.md`, `mot_apendice_matrizes.md` | `op_planejamento_relatorio.md` |
| **Matriz de Achados** | `op_matrizes.md`, `mot_apendice_achados.md` | `op_achados.md` |
| **Solicitação de Auditoria / Nota de Auditoria** | `mot_execucao_comunicacao.md`, `mot_apendice_documentos.md` | — |
| **Papéis de trabalho** | `mot_papeis_trabalho.md` | — |
| **Coleta e análise de dados / Evidências** | `mot_coleta_evidencias.md` | — |
| **Qualidade da redação** (qualquer artefato) | `op_qualidade.md`, `mot_qualidade.md` | `op_apendice_paragrafos.md` |
| **Aspectos formais** (formatação, siglas) | `op_aspectos_formais.md` | — |
| **Revisão do relatório** | `op_revisao.md` | — |
| **Análise de causa raiz** | `op_causa_raiz.md` | — |
| **Análise de riscos** | `riscos_metodologia.md` | `riscos_fundamentos.md`, `riscos_estrutura.md` |
| **Monitoramento de recomendações** | `mot_monitoramento.md` | — |
| **Glossário / termos técnicos** | `mot_glossario.md` | — |
| **Escala de impacto / probabilidade / mapa de riscos** | `mot_anexos_riscos.md` | `riscos_metodologia.md` |

### Catálogo completo dos arquivos

**OP 2019**
- `references/op_qualidade.md` — atributos de qualidade das comunicações e da redação (cap. 1)
- `references/op_planejamento_relatorio.md` — planejamento do relatório, Matriz de Planejamento e Achados (cap. 2)
- `references/op_capa_folha_missao.md` — Capa, Folha de rosto e Missão da CGU (seções 3.1–3.3)
- `references/op_resumo.md` — Resumo/highlight (seção 3.4)
- `references/op_siglas_sumario.md` — Lista de siglas e Sumário (seções 3.5–3.6)
- `references/op_introducao.md` — Introdução: quadro de parágrafos obrigatórios (seção 3.7)
- `references/op_achados.md` — Achados: componentes, classificação e organização (seções 3.8–3.8.2)
- `references/op_recomendacoes.md` — Recomendações e planos de ação (seção 3.9)
- `references/op_conclusao.md` — Conclusão do relatório (seção 3.10)
- `references/op_anexos_relatorio.md` — Anexos do relatório: manifestação da unidade, metodologia, outros documentos (seção 3.11)
- `references/op_aspectos_formais.md` — Formatação, quadros, tabelas, figuras, assinaturas (cap. 4)
- `references/op_revisao.md` — Revisão de relatórios (cap. 5)
- `references/op_causa_raiz.md` — Análise de causa raiz: técnicas e ferramentas (apêndice A)
- `references/op_apendice_paragrafos.md` — Desenvolvimento de parágrafos e argumentação (apêndice B)
- `references/op_matrizes.md` — Matriz de Planejamento e Matriz de Achados (apêndices C e D)
- `references/op_apendice_gramatica.md` — Falhas gramaticais comuns nos relatórios (apêndice F)

**MOT 2017**
- `references/mot_execucao_comunicacao.md` — comunicação com a unidade auditada durante a execução: reunião de abertura, SA, NA (seções 5.1–5.1.6)
- `references/mot_coleta_evidencias.md` — coleta e análise de dados, evidências e seus atributos (seções 5.2–5.3.4)
- `references/mot_achados.md` — achados de auditoria: requisitos e componentes (seções 5.4–5.4.3)
- `references/mot_manifestacao_unidade.md` — manifestação da unidade auditada (seção 5.5)
- `references/mot_recomendacoes.md` — recomendações: características desejáveis (seções 5.6–5.6.1)
- `references/mot_papeis_trabalho.md` — papéis de trabalho: elaboração, atributos, classificação e retenção (seções 5.7–5.7.6)
- `references/mot_qualidade.md` — qualidade das comunicações e da redação (seções 6.2–6.3)
- `references/mot_estrutura_relatorio.md` — formas e componentes do relatório (seções 6.5–6.5.2)
- `references/mot_comunicacao.md` — planejamento e encaminhamento das comunicações (seções 6.1, 6.4, 6.6, 6.7)
- `references/mot_monitoramento.md` — monitoramento de recomendações (cap. 7)
- `references/mot_glossario.md` — Glossário de termos técnicos
- `references/mot_apendice_matrizes.md` — Matrizes de Riscos e Planejamento (apêndices A e B)
- `references/mot_apendice_documentos.md` — Exemplos de Documento de Apresentação, SA e NA (apêndices C, D e E)
- `references/mot_apendice_achados.md` — Exemplo de Matriz de Achados (apêndice F)
- `references/mot_anexos_riscos.md` — Escalas de Impacto, Probabilidade e Mapa de Riscos (anexos A, B e C)

**Metodologia de Riscos 2.0**
- `references/riscos_fundamentos.md` — parâmetros legais, frameworks e conceitos (caps. 1 e 2)
- `references/riscos_estrutura.md` — estrutura de gestão, competências, comunicação (cap. 3)
- `references/riscos_metodologia.md` — processo completo: identificação, avaliação, tratamento, monitoramento (cap. 4)

---

## Artefatos Suportados

Esta skill cobre qualquer artefato produzido no ciclo de auditoria da CGU:

- **Seções do Relatório:** Capa, Folha de rosto, Missão da CGU, Lista de siglas, Sumário, Resumo (highlight), Introdução, Resultados dos Exames (Achados), Recomendações, Conclusão, Anexos
- **Achados individuais:** descrição sumária, parágrafo introdutório, critério, condição, causa, consequência/efeito
- **Instrumentos de planejamento:** Matriz de Planejamento, Matriz de Achados
- **Documentos de campo:** Solicitação de Auditoria (SA), Nota de Auditoria (NA), Papéis de trabalho
- **Análises:** Causa raiz, Evidências, Manifestação da unidade auditada

---

## Workflow de Análise

### Passo 1 — Identificar o artefato

Determine:
- Qual é o tipo do artefato (seção do relatório, achado, matriz…)?
- Qual é o tipo de serviço de auditoria (avaliação, consultoria ou apuração)?
- Há contexto adicional relevante (questões de auditoria definidas, objeto auditado, escopo)?

Se o usuário não informar o tipo de serviço e isso for relevante para a análise, pergunte antes de continuar.

### Passo 2 — Carregar apenas os arquivos pertinentes

Consulte a tabela "Mapeamento artefato → arquivos a ler" acima e leia **somente** os
arquivos indicados para o tipo de artefato submetido. Não carregue arquivos desnecessários.

### Passo 3 — Executar a análise

Avalie o artefato contra os critérios normativos relevantes para seu tipo. Para cada critério:

- ✅ **Conforme** — o artefato atende ao requisito
- ⚠️ **Parcialmente conforme** — atende parcialmente ou há dúvida
- ❌ **Não conforme** — o artefato não atende ao requisito
- ➖ **Não aplicável** — o critério não se aplica neste caso

### Passo 4 — Estruturar o resultado

Apresente o resultado sempre nesta ordem:

1. **Síntese** (2–4 frases): avaliação geral do artefato
2. **Tabela de conformidade**: critérios, status e observações
3. **Pontos críticos** (❌ e ⚠️): explicação detalhada de cada problema, com referência à norma
4. **Sugestões de melhoria**: texto revisado ou orientações concretas para correção
5. **Pontos positivos** (✅ relevantes): o que está bem feito e merece destaque

---

## Workflow de Geração

### Quando usar este modo

Use o modo geração quando o usuário fornecer insumos estruturados e pedir para **redigir**, **gerar** ou **elaborar** qualquer artefato — em vez de revisar um texto já existente. O modo se aplica tanto a um relatório completo quanto a artefatos individuais.

### Regra absoluta: proibido inventar informações

**O modelo não deve, em hipótese alguma, gerar informações que não foram fornecidas pelo usuário.** Isso inclui:

- Valores, datas, percentuais ou quantitativos não presentes nos insumos
- Nomes de unidades, programas, normas ou agentes não mencionados
- Causas, efeitos ou recomendações não constantes dos insumos
- Qualquer contextualização, histórico ou justificativa não fornecida

Quando uma informação obrigatória não estiver disponível, o modelo **deve inserir um marcador** no lugar, nunca preencher com suposição ou texto genérico.

### Formato dos marcadores

Use sempre o padrão abaixo, com instrução clara do que precisa ser fornecido:

```
[PREENCHER: <descrição objetiva do que é necessário>]
```

Exemplos:
- `[PREENCHER: origem e justificativa da auditoria — risco, materialidade ou criticidade que motivou a inclusão no Plano de Auditoria Interna]`
- `[PREENCHER: metodologia utilizada — natureza dos dados coletados, técnicas aplicadas e forma de tratamento]`
- `[PREENCHER: período de referência do escopo da auditoria]`
- `[PREENCHER: número e data da Solicitação de Auditoria]`
- `[PREENCHER: evidência que suporta a condição descrita]`

### Mapeamento insumo → artefatos geráveis

| Insumo fornecido | Artefatos que podem ser gerados |
|---|---|
| **Matriz de Achados** | Relatório completo (parcial), Achados individuais, Recomendações, Conclusão, Resumo |
| **Matriz de Planejamento** | Introdução, Resumo; complementa a Matriz de Achados para o relatório completo |
| **Ambas as matrizes** | Relatório completo com menos marcadores |
| **Achado estruturado** (critério, condição, causa, efeito) | Achado individual redigido, Recomendação correspondente |
| **Notas de campo / dados brutos** | Achado individual, SA, NA |
| **Relatório já redigido** | Resumo/highlight, Conclusão |
| **Dados de acompanhamento** | Nota de Auditoria (NA) de monitoramento |

### Passo 1 — Identificar os insumos e o artefato solicitado

Verifique:
- Qual artefato o usuário quer gerar (relatório completo, seção isolada, achado, SA, NA…)?
- Quais insumos foram fornecidos?
- Há informações suficientes para gerar o artefato solicitado, mesmo que com marcadores?

### Passo 2 — Carregar os arquivos de referência

Carregue apenas os arquivos correspondentes ao artefato a ser gerado:

| Artefato a gerar | Arquivos obrigatórios |
|---|---|
| Relatório completo | `op_introducao.md`, `mot_estrutura_relatorio.md`, `op_achados.md`, `mot_achados.md`, `op_recomendacoes.md`, `mot_recomendacoes.md`, `op_conclusao.md`, `op_resumo.md` |
| Resumo (highlight) | `op_resumo.md` |
| Introdução | `op_introducao.md`, `mot_estrutura_relatorio.md` |
| Achado individual | `op_achados.md`, `mot_achados.md` |
| Recomendação | `op_recomendacoes.md`, `mot_recomendacoes.md` |
| Conclusão | `op_conclusao.md`, `mot_estrutura_relatorio.md` |
| Solicitação de Auditoria (SA) | `mot_execucao_comunicacao.md`, `mot_apendice_documentos.md` |
| Nota de Auditoria (NA) | `mot_execucao_comunicacao.md`, `mot_apendice_documentos.md` |

Sempre carregue também: `op_qualidade.md`, `mot_qualidade.md`, `op_apendice_gramatica.md`.

### Passo 3 — Gerar o artefato

Redija o artefato usando **exclusivamente** as informações fornecidas pelo usuário. Para cada campo obrigatório sem dado correspondente nos insumos, insira o marcador `[PREENCHER: ...]` com instrução específica.

Para artefatos compostos por múltiplas seções (ex: relatório completo), gere seção por seção na ordem correta e liste os marcadores de cada seção ao final dela.

### Passo 4 — Consolidar os marcadores

Ao final do artefato gerado, apresente um **resumo dos marcadores pendentes** agrupados por seção, para facilitar o preenchimento pelo usuário.

---

## Critérios por Tipo de Artefato

### Introdução do Relatório (OP 2019, seção 3.7; MOT 2017, seção 6.5.2)

| Parágrafo | Conteúdo obrigatório |
|---|---|
| 1º | Unidade auditada; objeto auditado; ação/programa orçamentário; referencial legal; escopo (o quê, quanto, quando, onde) |
| 2º | Origem e justificativa (risco, materialidade, relevância, criticidade) |
| 3º | Objetivos/questões de auditoria |
| 4º | Metodologia (natureza dos dados, coleta, tratamento) |
| 5º | Limitações/restrições (somente se houver) |
| 6º | Considerações iniciais / visão geral (aspectos positivos, histórico relevante) |

Critérios adicionais:
- A introdução **não deve ser excessivamente longa**
- Detalhes complementares devem ir para **anexo**, não para a introdução
- Não deve conter achados; a função é contextualizar

### Achado de Auditoria (OP 2019, seções 3.8–3.8.2; MOT 2017, seções 5.4–5.4.3)

| Componente | O que verificar |
|---|---|
| Descrição sumária | Resume adequadamente o achado; inclui números/valores quando relevantes |
| Parágrafo introdutório | Contextualiza o achado; responde: o quê, quem, quando, quanto, onde, como, por quê |
| Critério | Padrão utilizado para avaliação; classificado como interno, externo ou melhores práticas |
| Condição | Situação existente identificada e documentada; suficientemente evidenciada |
| Causa | Razão para a diferença entre critério e condição; identifica causa raiz quando possível |
| Consequência/Efeito | Impacto real ou potencial da condição identificada |

Critérios adicionais:
- Achados apresentados **por ordem de relevância** (mais relevante primeiro)
- Cada achado deve responder a **pelo menos uma questão de auditoria**
- Devem ser convincentes e fundamentados em **evidências**

### Recomendações (OP 2019, seção 3.9; MOT 2017, seções 5.6–5.6.1)

- Elaboradas **com base na causa raiz** (quando possível)
- Práticas e viáveis
- Em harmonia com os achados
- Foco em evitar recorrência (não apenas corrigir a condição)

### Conclusão (OP 2019, seção 3.10; MOT 2017, seção 6.5.2)

- Emissão da **opinião final** da equipe sobre o objeto auditado
- Pode apresentar achados de forma sintética
- Deve ter **caráter gerencial** (alçada da alta administração)
- Pode registrar boas práticas identificadas

### Resumo / Highlight (OP 2019, seção 3.4)

Deve responder a três perguntas:
1. **Qual foi o trabalho realizado** (objeto + escopo)?
2. **Por que foi realizado** (risco, materialidade, relevância, criticidade)?
3. **Quais as conclusões e recomendações** principais?

Restrições:
- Máximo **uma página**
- Não deve conter metodologias técnicas detalhadas

### Atributos de Qualidade da Redação (MOT 2017, seção 6.2; OP 2019, cap. 1)

| Atributo | O que verificar |
|---|---|
| **Clara** | Pensamento exposto de forma compreensível; uma ideia por parágrafo; linguagem acessível |
| **Completa** | Contém todas as informações necessárias; não prolixo |
| **Concisa** | Sem elaboração desnecessária, detalhes supérfluos ou redundância |
| **Construtiva** | Útil para os destinatários; conduz a melhorias; tom não conflituoso |
| **Objetiva** | Imparcial, neutra, livre de influência indevida |
| **Precisa** | Livre de erros e distorções; fiel aos fatos e evidências |
| **Coerente** | Ordenação lógica; orações e parágrafos logicamente vinculados |
| **Sóbria** | Tom comedido; sem depreciação de pessoas ou instituições |

---

## Output Esperado (template)

```
## Análise de Conformidade — [Tipo de Artefato]

### Síntese
[Avaliação geral em 2–4 frases]

### Tabela de Conformidade

| Critério | Status | Observação |
|---|---|---|
| [critério] | ✅/⚠️/❌/➖ | [observação] |

### Pontos Críticos
**[Critério com problema]** (❌/⚠️)
> Referência: [norma, seção]
[Explicação do problema e impacto]

### Sugestões de Melhoria
[Texto revisado ou orientações concretas]

### Pontos Positivos
[O que está bem feito]
```

---

## Notas de Aplicação

- **Seja específico nas referências normativas**: cite sempre a seção/parágrafo da norma.
- **Não invente requisitos**: se um elemento não estiver nas normas de referência, não o exija. Anote como sugestão, não como não conformidade.
- **Contexto importa**: a OP 2019 admite flexibilidade na estrutura da introdução. Avalie a substância, não apenas a forma.
- **Tipos de serviço têm especificidades**: avaliação, consultoria e apuração têm nuances. Quando relevante, sinalize diferenças de tratamento previstas nas normas.
