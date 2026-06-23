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

## Normas de Referência

Leia os arquivos de referência abaixo **antes de qualquer análise**. Cada um cobre
um domínio específico; leia todos que forem pertinentes ao artefato sob análise:

| Arquivo | Conteúdo | Quando ler |
|---|---|---|
| `references/MOT_2017.md` | Manual de Orientações Técnicas 2017 — normas gerais de execução, comunicação e estrutura do relatório (cap. 6) | Sempre; é o documento-base |
| `references/OP_2019.md` | Orientação Prática: Relatório de Auditoria 2019 — estrutura detalhada do relatório, componentes de cada seção, atributos de qualidade, revisão | Sempre que o artefato for uma seção do relatório |
| `references/Metodologia_Riscos_2_0.md` | Metodologia de Gestão de Riscos 2.0 — processo de identificação, avaliação e tratamento de riscos | Quando o artefato envolver análise ou referência a riscos |

> **Importante:** as normas são complementares. A OP 2019 detalha e operacionaliza
> o MOT 2017. Em caso de aparente conflito, a OP 2019 prevalece para questões de
> elaboração do relatório.

---

## Artefatos Suportados

Esta skill cobre qualquer artefato produzido no ciclo de auditoria da CGU:

- **Seções do Relatório:** Introdução, Resultados dos Exames (Achados), Recomendações, Conclusão, Resumo (highlight), Capa, Folha de rosto, Lista de siglas
- **Achados individuais:** descrição sumária, parágrafo introdutório, critério, condição, causa, consequência/efeito
- **Instrumentos de planejamento:** Matriz de Planejamento, Matriz de Achados
- **Documentos avulsos:** Nota de Auditoria, Solicitação de Auditoria

---

## Workflow de Análise

### Passo 1 — Identificar o artefato

Determine:
- Qual é o tipo do artefato (seção do relatório, achado, matriz…)?
- Qual é o tipo de serviço de auditoria (avaliação, consultoria ou apuração)?
- Há contexto adicional relevante (questões de auditoria definidas, objeto auditado, escopo)?

Se o usuário não informar o tipo de serviço e isso for relevante para a análise, pergunte antes de continuar.

### Passo 2 — Carregar a norma pertinente

Leia os arquivos de referência conforme a tabela acima. Para análise de seções do
relatório, leia **sempre** o MOT_2017 (cap. 6, seção 6.5.2) e o OP_2019 (cap. 3).

### Passo 3 — Executar a análise

Avalie o artefato contra os critérios normativos relevantes para seu tipo (veja
seção "Critérios por Tipo de Artefato" abaixo). Para cada critério:

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

## Critérios por Tipo de Artefato

### Introdução do Relatório (OP 2019, seção 3.7; MOT 2017, seção 6.5.2)

A introdução deve conter os seguintes parágrafos/conteúdos:

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

### Achado de Auditoria (OP 2019, seção 3.8 e 3.8.1)

Componentes obrigatórios de cada achado:

| Componente | O que verificar |
|---|---|
| Descrição sumária | Resume adequadamente o achado; inclui números/valores quando relevantes; não abre margem para interpretações não suportadas pelas evidências |
| Parágrafo introdutório | Contextualiza o achado; responde: o quê, quem, quando, quanto, onde, como, por quê |
| Critério | Padrão utilizado para avaliação; classificado como interno, externo ou melhores práticas; definido na fase de planejamento |
| Condição | Situação existente identificada e documentada; suficientemente evidenciada; não excessivamente detalhada (nível intermediário, não analítico) |
| Causa | Razão para a diferença entre critério e condição; identifica causa raiz quando possível |
| Consequência/Efeito | Impacto real ou potencial da condição identificada |

Critérios adicionais:
- Achados apresentados **por ordem de relevância** (mais relevante primeiro)
- Cada achado deve responder a **pelo menos uma questão de auditoria**
- Devem ser convincentes e fundamentados em **evidências**

### Recomendações (OP 2019, seção 3.9; MOT 2017, seção 6.5.2)

- Elaboradas **com base na causa raiz** (quando possível)
- Práticas e viáveis
- Em harmonia com os achados
- Foco em evitar recorrência (não apenas corrigir a condição)

### Conclusão (OP 2019, seção 3.10; MOT 2017, seção 6.5.2)

- Emissão da **opinião final** da equipe sobre o objeto auditado
- Pode apresentar achados de forma sintética
- Pode mencionar benefícios decorrentes da auditoria
- Deve ter **caráter gerencial** (alçada da alta administração)
- Pode registrar boas práticas identificadas

### Resumo / Highlight (OP 2019, seção 3.4)

Deve responder a três perguntas:
1. **Qual foi o trabalho realizado** (objeto + escopo)?
2. **Por que foi realizado** (risco, materialidade, relevância, criticidade — não mencionar denúncias ou demandas externas)?
3. **Quais as conclusões e recomendações** principais?

Restrições:
- Máximo **uma página**
- Não deve conter metodologias técnicas detalhadas

### Atributos de Qualidade da Redação (MOT 2017, seção 6.2; OP 2019, cap. 1)

Aplique a todos os artefatos:

| Atributo | O que verificar |
|---|---|
| **Clara** | Pensamento exposto de forma compreensível; uma ideia por parágrafo; linguagem acessível |
| **Completa** | Contém todas as informações necessárias para compreender os resultados; não prolixo |
| **Concisa** | Sem elaboração desnecessária, detalhes supérfluos ou redundância |
| **Construtiva** | Útil para os destinatários; conduz a melhorias; tom não conflituoso |
| **Objetiva** | Imparcial, neutra, livre de influência indevida |
| **Precisa** | Livre de erros e distorções; fiel aos fatos e evidências |
| **Tempestiva** | (verificar se há indicações de atraso ou defasagem) |
| **Coerente** | Ordenação lógica; orações e parágrafos logicamente vinculados |
| **Sóbria** | Tom comedido; sem depreciação de pessoas ou instituições; sem insinuações ou generalizações |

---

## Referências Cruzadas Rápidas

Use estes atalhos para localizar conteúdo específico nas normas:

**MOT 2017:**
- Atributos de qualidade das comunicações → seção 6.2
- Qualidade da redação → seção 6.3
- Formas de relatório → seção 6.5.1
- Componentes do relatório → seção 6.5.2

**OP 2019:**
- Atributos de qualidade → cap. 1
- Matriz de Planejamento e Achados → cap. 2
- Estrutura do relatório (todas as seções) → cap. 3
- Introdução (quadro de parágrafos) → seção 3.7, Quadro 2
- Componentes do achado → seção 3.8.1
- Aspectos formais (formatação, siglas, assinaturas) → cap. 4
- Revisão do relatório → cap. 5

**Metodologia de Riscos 2.0:**
- Processo de gerenciamento de riscos → seção principal
- Identificação, avaliação e tratamento → seções específicas

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

- **Seja específico nas referências normativas**: cite sempre a seção/parágrafo da norma, não apenas o nome do documento.
- **Não invente requisitos**: se um elemento não estiver nas normas de referência, não o exija. Anote como sugestão, não como não conformidade.
- **Contexto importa**: a OP 2019 admite flexibilidade na estrutura da introdução ("se houver necessidade, esse roteiro poderá ser desdobrado em mais parágrafos"). Avalie a substância, não apenas a forma.
- **Tipos de serviço têm especificidades**: avaliação, consultoria e apuração têm nuances. Quando relevante, sinalize diferenças de tratamento previstas nas normas.
