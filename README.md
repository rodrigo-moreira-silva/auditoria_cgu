# cgu-auditoria-skill

> Skill de IA para análise de conformidade de artefatos de auditoria da CGU com as normas internas vigentes.

---

## O que é

Este repositório contém uma **skill para sistemas baseados em LLM** que automatiza a verificação de conformidade de artefatos de auditoria produzidos pela Controladoria-Geral da União (CGU). A skill instrui o modelo a analisar documentos de auditoria contra três normas internas e emitir um parecer estruturado com status, pontos críticos e sugestões de melhoria.

Os arquivos de norma são **divididos por tema** — o modelo carrega apenas os arquivos relevantes para o tipo de artefato submetido, em vez de carregar as normas completas a cada chamada.

---

## Normas de Referência

| Norma | Escopo |
|---|---|
| Manual de Orientações Técnicas 2017 (MOT 2017) | Normas gerais de execução, comunicação e estrutura do relatório |
| Orientação Prática: Relatório de Auditoria 2019 (OP 2019) | Estrutura detalhada, componentes de cada seção, atributos de qualidade |
| Metodologia de Gestão de Riscos 2.0 | Identificação, avaliação e tratamento de riscos |

> A OP 2019 detalha e operacionaliza o MOT 2017. Em caso de conflito aparente, a OP 2019 prevalece para questões de elaboração do relatório.

---

## Artefatos Suportados

- **Seções do Relatório:** Capa, Folha de rosto, Missão da CGU, Lista de siglas, Sumário, Resumo (highlight), Introdução, Achados, Recomendações, Conclusão, Anexos
- **Achados individuais:** descrição sumária, parágrafo introdutório, critério, condição, causa, consequência/efeito
- **Instrumentos de planejamento:** Matriz de Planejamento, Matriz de Achados
- **Documentos de campo:** Solicitação de Auditoria (SA), Nota de Auditoria (NA), Papéis de trabalho
- **Análises:** Causa raiz, Evidências, Manifestação da unidade auditada

---

## Estrutura do Repositório

```
auditoria_cgu/
├── SKILL.md
├── references/
│   ├── op_qualidade.md                   # OP 2019 — atributos de qualidade (cap. 1)
│   ├── op_planejamento_relatorio.md      # OP 2019 — planejamento do relatório (cap. 2)
│   ├── op_capa_folha_missao.md           # OP 2019 — Capa, Folha de rosto, Missão (seções 3.1–3.3)
│   ├── op_resumo.md                      # OP 2019 — Resumo/highlight (seção 3.4)
│   ├── op_siglas_sumario.md              # OP 2019 — Lista de siglas e Sumário (seções 3.5–3.6)
│   ├── op_introducao.md                  # OP 2019 — Introdução (seção 3.7)
│   ├── op_achados.md                     # OP 2019 — Achados: componentes e organização (seções 3.8–3.8.2)
│   ├── op_recomendacoes.md               # OP 2019 — Recomendações e planos de ação (seção 3.9)
│   ├── op_conclusao.md                   # OP 2019 — Conclusão (seção 3.10)
│   ├── op_anexos_relatorio.md            # OP 2019 — Anexos do relatório (seção 3.11)
│   ├── op_aspectos_formais.md            # OP 2019 — Formatação, quadros, assinaturas (cap. 4)
│   ├── op_revisao.md                     # OP 2019 — Revisão de relatórios (cap. 5)
│   ├── op_causa_raiz.md                  # OP 2019 — Análise de causa raiz (apêndice A)
│   ├── op_apendice_paragrafos.md         # OP 2019 — Desenvolvimento de parágrafos e argumentação (apêndice B)
│   ├── op_matrizes.md                    # OP 2019 — Matriz de Planejamento e Achados (apêndices C e D)
│   ├── op_apendice_gramatica.md          # OP 2019 — Falhas gramaticais comuns (apêndice F)
│   ├── mot_execucao_comunicacao.md       # MOT 2017 — comunicação durante a execução: SA, NA (seções 5.1–5.1.6)
│   ├── mot_coleta_evidencias.md          # MOT 2017 — coleta de dados e evidências (seções 5.2–5.3.4)
│   ├── mot_achados.md                    # MOT 2017 — achados: requisitos e componentes (seções 5.4–5.4.3)
│   ├── mot_manifestacao_unidade.md       # MOT 2017 — manifestação da unidade auditada (seção 5.5)
│   ├── mot_recomendacoes.md              # MOT 2017 — recomendações (seções 5.6–5.6.1)
│   ├── mot_papeis_trabalho.md            # MOT 2017 — papéis de trabalho (seções 5.7–5.7.6)
│   ├── mot_qualidade.md                  # MOT 2017 — qualidade das comunicações e redação (seções 6.2–6.3)
│   ├── mot_estrutura_relatorio.md        # MOT 2017 — formas e componentes do relatório (seções 6.5–6.5.2)
│   ├── mot_comunicacao.md                # MOT 2017 — planejamento e encaminhamento (seções 6.1, 6.4, 6.6, 6.7)
│   ├── mot_monitoramento.md              # MOT 2017 — monitoramento de recomendações (cap. 7)
│   ├── mot_glossario.md                  # MOT 2017 — Glossário
│   ├── mot_apendice_matrizes.md          # MOT 2017 — Matrizes de Riscos e Planejamento (apêndices A e B)
│   ├── mot_apendice_documentos.md        # MOT 2017 — Exemplos de SA, NA e Documento de Apresentação (apêndices C, D e E)
│   ├── mot_apendice_achados.md           # MOT 2017 — Exemplo de Matriz de Achados (apêndice F)
│   ├── mot_anexos_riscos.md              # MOT 2017 — Escalas de Impacto, Probabilidade e Mapa de Riscos (anexos A, B e C)
│   ├── riscos_fundamentos.md             # Riscos 2.0 — parâmetros legais e conceitos (caps. 1–2)
│   ├── riscos_estrutura.md               # Riscos 2.0 — estrutura de gestão e competências (cap. 3)
│   └── riscos_metodologia.md             # Riscos 2.0 — processo completo de gestão de riscos (cap. 4)
└── README.md
```

O `SKILL.md` contém uma tabela de mapeamento `artefato → arquivos a ler`, de forma que o modelo consulta apenas o subconjunto relevante para cada análise.

---

## Como Usar

### Instalação no Claude (claude.ai)

**Opção A — Project Instructions (recomendado)**

1. Clone o repositório:
   ```bash
   git clone https://github.com/rodrigo-moreira-silva/auditoria_cgu.git
   cd auditoria_cgu
   ```
2. No [claude.ai](https://claude.ai), crie um **Project** (menu lateral → *New Project*)
3. Abra as configurações do projeto → **Project Instructions**
4. Cole, em sequência:
   - o conteúdo de `SKILL.md` (raiz do repositório)
   - o conteúdo dos arquivos em `references/` relevantes para o seu caso de uso (veja tabela de mapeamento no `SKILL.md`)
5. Salve — a skill estará ativa em todas as conversas desse projeto

> ⚠️ O limite de contexto do Claude é de ~200 mil tokens. Carregue apenas os arquivos de referência necessários para o seu caso de uso — não é preciso incluir todos os 34 arquivos.

**Opção B — Cola direto na conversa**

Para uso pontual, cole o conteúdo do `SKILL.md` no início de uma conversa nova antes de submeter o artefato. Sem os arquivos de referência, o modelo usará seu conhecimento geral das normas — suficiente para análises básicas.

---

### Integração via API (Python)

O script abaixo carrega seletivamente apenas os arquivos relevantes para o tipo de artefato:

```python
import httpx

BASE = "https://raw.githubusercontent.com/rodrigo-moreira-silva/auditoria_cgu/main/references"

# Mapeamento: tipo de artefato → arquivos a carregar
REFERENCIAS = {
    "capa":              ["op_capa_folha_missao.md", "op_aspectos_formais.md"],
    "siglas_sumario":    ["op_siglas_sumario.md", "op_aspectos_formais.md"],
    "resumo":            ["op_resumo.md", "op_qualidade.md"],
    "introducao":        ["op_introducao.md", "mot_estrutura_relatorio.md", "op_qualidade.md", "mot_qualidade.md"],
    "achado":            ["op_achados.md", "mot_achados.md", "op_causa_raiz.md", "op_qualidade.md"],
    "recomendacoes":     ["op_recomendacoes.md", "mot_recomendacoes.md"],
    "manifestacao":      ["op_anexos_relatorio.md", "mot_manifestacao_unidade.md"],
    "conclusao":         ["op_conclusao.md", "mot_estrutura_relatorio.md", "op_qualidade.md"],
    "anexos":            ["op_anexos_relatorio.md"],
    "matriz":            ["op_matrizes.md", "mot_apendice_matrizes.md", "op_planejamento_relatorio.md"],
    "sa_na":             ["mot_execucao_comunicacao.md", "mot_apendice_documentos.md"],
    "papeis_trabalho":   ["mot_papeis_trabalho.md"],
    "evidencias":        ["mot_coleta_evidencias.md"],
    "redacao":           ["op_qualidade.md", "mot_qualidade.md", "op_apendice_paragrafos.md", "op_apendice_gramatica.md"],
    "aspectos_formais":  ["op_aspectos_formais.md"],
    "revisao":           ["op_revisao.md"],
    "causa_raiz":        ["op_causa_raiz.md"],
    "riscos":            ["riscos_metodologia.md", "riscos_fundamentos.md", "riscos_estrutura.md"],
    "monitoramento":     ["mot_monitoramento.md"],
}

def carregar_referencias(tipo_artefato: str) -> str:
    arquivos = REFERENCIAS.get(tipo_artefato, [])
    blocos = []
    for arquivo in arquivos:
        conteudo = httpx.get(f"{BASE}/{arquivo}").text
        blocos.append(f"### {arquivo}\n\n{conteudo}")
    return "\n\n---\n\n".join(blocos)

def montar_system_prompt(tipo_artefato: str) -> str:
    skill = httpx.get(
        "https://raw.githubusercontent.com/rodrigo-moreira-silva/auditoria_cgu/main/SKILL.md"
    ).text
    refs = carregar_referencias(tipo_artefato)
    return f"{skill}\n\n---\n\n## Documentos Normativos Carregados\n\n{refs}"
```

### Exemplo de chamada (Azure OpenAI)

```python
from openai import AzureOpenAI

client = AzureOpenAI(
    azure_endpoint="https://<seu-recurso>.openai.azure.com/",
    api_key="<sua-chave>",
    api_version="2024-02-01",
)

tipo_artefato = "introducao"  # ver chaves do dicionário REFERENCIAS acima
artefato = "<cole aqui o texto a ser analisado>"

response = client.chat.completions.create(
    model="gpt-5",  # nome do deployment no Azure
    messages=[
        {"role": "system", "content": montar_system_prompt(tipo_artefato)},
        {"role": "user", "content": f"Analise a conformidade desta {tipo_artefato}:\n\n{artefato}"},
    ],
)

print(response.choices[0].message.content)
```

---

## Output Esperado

```
## Análise de Conformidade — [Tipo de Artefato]

### Síntese
Avaliação geral em 2–4 frases.

### Tabela de Conformidade
| Critério | Status | Observação |
|---|---|---|
| Parágrafo 1 (objeto/escopo) | ✅ | Presente e completo |
| Parágrafo 2 (origem/justificativa) | ⚠️ | Menciona risco mas omite materialidade |

### Pontos Críticos
**[Critério com problema]** (❌/⚠️)
> Referência: OP 2019, seção 3.7
Explicação do problema e impacto.

### Sugestões de Melhoria
Texto revisado ou orientações concretas.

### Pontos Positivos
O que está bem feito e merece destaque.
```

**Legenda:** ✅ Conforme · ⚠️ Parcialmente conforme · ❌ Não conforme · ➖ Não aplicável

---

## Contexto

Desenvolvido na **Controladoria-Geral da União (CGU)** para apoiar equipes de auditoria na revisão de relatórios, com foco em consistência normativa e qualidade da redação.
