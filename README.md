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

- **Seções do Relatório:** Introdução, Resultados dos Exames (Achados), Recomendações, Conclusão, Resumo (highlight)
- **Achados individuais:** descrição sumária, parágrafo introdutório, critério, condição, causa, consequência/efeito
- **Instrumentos de planejamento:** Matriz de Planejamento, Matriz de Achados
- **Documentos avulsos:** Nota de Auditoria, Solicitação de Auditoria

---

## Estrutura do Repositório

```
auditoria_cgu/
├── SKILL.md                              # Definição da skill (workflow, critérios, mapeamento de arquivos)
├── references/
│   ├── op_qualidade.md                   # OP 2019 — atributos de qualidade (cap. 1)
│   ├── op_planejamento_relatorio.md      # OP 2019 — planejamento do relatório (cap. 2)
│   ├── op_resumo.md                      # OP 2019 — Resumo/highlight (seção 3.4)
│   ├── op_introducao.md                  # OP 2019 — Introdução (seção 3.7)
│   ├── op_achados.md                     # OP 2019 — Achados: componentes e organização (seções 3.8–3.8.1)
│   ├── op_recomendacoes.md               # OP 2019 — Recomendações e planos de ação (seção 3.9)
│   ├── op_conclusao.md                   # OP 2019 — Conclusão (seção 3.10)
│   ├── op_aspectos_formais.md            # OP 2019 — Formatação, quadros, assinaturas (cap. 4)
│   ├── op_revisao.md                     # OP 2019 — Revisão de relatórios (cap. 5)
│   ├── op_causa_raiz.md                  # OP 2019 — Análise de causa raiz (apêndice A)
│   ├── op_matrizes.md                    # OP 2019 — Matriz de Planejamento e Achados (apêndices C e D)
│   ├── mot_qualidade.md                  # MOT 2017 — qualidade das comunicações e redação (seções 6.2–6.3)
│   ├── mot_estrutura_relatorio.md        # MOT 2017 — formas e componentes do relatório (seções 6.5.1–6.5.2)
│   ├── mot_comunicacao.md                # MOT 2017 — planejamento e encaminhamento (seções 6.1, 6.4, 6.6, 6.7)
│   ├── mot_achados.md                    # MOT 2017 — achados: requisitos e componentes (seções 5.4–5.4.3)
│   ├── mot_recomendacoes.md              # MOT 2017 — recomendações (seções 5.6–5.6.1)
│   ├── mot_matrizes.md                   # MOT 2017 — Matrizes de Riscos, Planejamento e Achados
│   ├── mot_monitoramento.md              # MOT 2017 — monitoramento de recomendações (cap. 7)
│   ├── riscos_fundamentos.md             # Riscos 2.0 — parâmetros legais e conceitos (caps. 1–2)
│   ├── riscos_estrutura.md               # Riscos 2.0 — estrutura de gestão e competências (cap. 3)
│   └── riscos_metodologia.md             # Riscos 2.0 — processo completo de gestão de riscos (cap. 4)
└── README.md
```

O `SKILL.md` contém uma tabela de mapeamento `artefato → arquivos a ler`, de forma que o modelo consulta apenas o subconjunto relevante para cada análise.

---

## Como Usar

### Instalação no Claude (claude.ai)

Não há instalação automática via repositório — a skill precisa ser carregada manualmente como contexto. Há dois caminhos:

**Opção A — Project Instructions (recomendado)**

Ideal para uso recorrente. Tudo que for colocado nas instruções do projeto fica disponível em todas as conversas daquele projeto.

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

> ⚠️ O limite de contexto do Claude é de ~200 mil tokens. Carregue apenas os arquivos de referência necessários para o seu caso de uso — não é preciso incluir todos os 21 arquivos.

**Opção B — Cola direto na conversa**

Para uso pontual, cole o conteúdo do `SKILL.md` no início de uma conversa nova antes de submeter o artefato. Sem os arquivos de referência, o modelo usará seu conhecimento geral das normas — suficiente para análises básicas.

---

### Integração via API (Python)

O script abaixo carrega seletivamente apenas os arquivos relevantes para o tipo de artefato, puxando direto do GitHub:

```python
import httpx

BASE = "https://raw.githubusercontent.com/rodrigo-moreira-silva/auditoria_cgu/main/references"

# Mapeamento: tipo de artefato → arquivos a carregar
REFERENCIAS = {
    "introducao":      ["op_introducao.md", "mot_estrutura_relatorio.md", "op_qualidade.md"],
    "achado":          ["op_achados.md", "mot_achados.md", "op_causa_raiz.md"],
    "recomendacoes":   ["op_recomendacoes.md", "mot_recomendacoes.md"],
    "conclusao":       ["op_conclusao.md", "mot_estrutura_relatorio.md"],
    "resumo":          ["op_resumo.md", "op_qualidade.md"],
    "matriz":          ["op_matrizes.md", "mot_matrizes.md"],
    "riscos":          ["riscos_metodologia.md", "riscos_fundamentos.md"],
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

tipo_artefato = "introducao"  # ou: achado, recomendacoes, conclusao, resumo, matriz, riscos
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

O modelo retorna sempre na seguinte estrutura:

```
## Análise de Conformidade — [Tipo de Artefato]

### Síntese
Avaliação geral em 2–4 frases.

### Tabela de Conformidade
| Critério | Status | Observação |
|---|---|---|
| Parágrafo 1 (objeto/escopo) | ✅ | Presente e completo |
| Parágrafo 2 (origem/justificativa) | ⚠️ | Menciona risco mas omite materialidade |
| ...

### Pontos Críticos
**[Critério com problema]** (❌/⚠️)
> Referência: OP 2019, seção 3.7, Quadro 2
Explicação do problema e impacto.

### Sugestões de Melhoria
Texto revisado ou orientações concretas.

### Pontos Positivos
O que está bem feito e merece destaque.
```

**Legenda de status:**
- ✅ Conforme
- ⚠️ Parcialmente conforme
- ❌ Não conforme
- ➖ Não aplicável

---

## Contexto

Desenvolvido na **Controladoria-Geral da União (CGU)** para apoiar equipes de auditoria na revisão de relatórios, com foco em consistência normativa e qualidade da redação.
