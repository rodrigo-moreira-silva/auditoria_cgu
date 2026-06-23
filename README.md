# cgu-auditoria-skill

> Skill de IA para análise de conformidade de artefatos de auditoria da CGU com as normas internas vigentes.

---

## O que é

Este repositório contém uma **skill para sistemas baseados em LLM** que automatiza a verificação de conformidade de artefatos de auditoria produzidos pela Controladoria-Geral da União (CGU). A skill instrui o modelo a analisar documentos de auditoria contra três normas internas e emitir um parecer estruturado com status, pontos críticos e sugestões de melhoria.

---

## Normas de Referência

| Arquivo | Norma | Escopo |
|---|---|---|
| `references/MOT_2017.md` | Manual de Orientações Técnicas 2017 | Normas gerais de execução, comunicação e estrutura do relatório |
| `references/OP_2019.md` | Orientação Prática: Relatório de Auditoria 2019 | Estrutura detalhada, componentes de cada seção, atributos de qualidade |
| `references/Metodologia_Riscos_2_0.md` | Metodologia de Gestão de Riscos 2.0 | Identificação, avaliação e tratamento de riscos |

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
cgu-auditoria-skill/
├── SKILL.md                          # Definição da skill (workflow, critérios, output)
├── references/
│   ├── MOT_2017.md                   # Manual de Orientações Técnicas 2017
│   ├── OP_2019.md                    # Orientação Prática: Relatório de Auditoria 2019
│   └── Metodologia_Riscos_2_0.md     # Metodologia de Riscos 2.0
└── README.md
```

---

## Como Usar

### Em sistemas com suporte a skills (ex: Claude)

Registre a skill apontando para `SKILL.md`. O modelo carregará automaticamente os arquivos de referência conforme o tipo de artefato submetido.

### Integração via API (Python)

```python
from pathlib import Path

SKILL = Path("SKILL.md").read_text(encoding="utf-8")
MOT   = Path("references/MOT_2017.md").read_text(encoding="utf-8")
OP    = Path("references/OP_2019.md").read_text(encoding="utf-8")

system_prompt = f"""
{SKILL}

---

## Documentos Normativos Carregados

### MOT 2017
{MOT}

### OP 2019
{OP}
"""

# Use system_prompt como system message em qualquer cliente OpenAI / Anthropic
```

### Exemplo de chamada (OpenAI / Azure OpenAI)

```python
from openai import AzureOpenAI

client = AzureOpenAI(
    azure_endpoint="https://<seu-recurso>.openai.azure.com/",
    api_key="<sua-chave>",
    api_version="2024-02-01",
)

artefato = """
<cole aqui o texto da Introdução ou outro artefato a ser analisado>
"""

response = client.chat.completions.create(
    model="gpt-5",  # nome do deployment no Azure
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": f"Analise a conformidade desta Introdução:\n\n{artefato}"},
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
