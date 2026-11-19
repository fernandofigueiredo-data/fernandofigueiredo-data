<div align="center">

<img alt="Fernando Figueiredo — análise de dados e business intelligence" src="assets/hero.svg" width="100%">

<p>
  <a href="https://www.linkedin.com/in/fernandofigueiredoalves/"><img alt="pergunta, evidência, decisão — análise de dados com SQL, Power BI, Python e machine learning" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=17&pause=1200&duration=3600&color=00E5FF&center=true&vCenter=true&width=720&height=44&lines=pergunta+%E2%86%92+evid%C3%AAncia+%E2%86%92+decis%C3%A3o;an%C3%A1lise+de+dados+orientada+a+decis%C3%A3o+de+neg%C3%B3cio;SQL+%C2%B7+Power+BI+%C2%B7+Python+%C2%B7+Machine+Learning;10%2B+anos+em+Comunica%C3%A7%C3%A3o%2C+Estrat%C3%A9gia+e+Storytelling"></a>
</p>

<p>
  <img alt="SQL" src="https://img.shields.io/badge/SQL-151C2B?style=flat-square&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0iI0E5NzBGRiI%2BPGVsbGlwc2UgY3g9IjEyIiBjeT0iNSIgcng9IjgiIHJ5PSIzIi8%2BPHBhdGggZD0iTTQgOHY0YzAgMS42NiAzLjU4IDMgOCAzczgtMS4zNCA4LTNWOGMwIDEuNjYtMy41OCAzLTggM3MtOC0xLjM0LTgtM3oiLz48cGF0aCBkPSJNNCAxNHY0YzAgMS42NiAzLjU4IDMgOCAzczgtMS4zNCA4LTN2LTRjMCAxLjY2LTMuNTggMy04IDNzLTgtMS4zNC04LTN6Ii8%2BPC9zdmc%2B">
  <img alt="Power BI" src="https://img.shields.io/badge/Power%20BI-151C2B?style=flat-square&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0iI0E5NzBGRiI%2BPHJlY3QgeD0iMyIgeT0iMTMiIHdpZHRoPSI1IiBoZWlnaHQ9IjgiIHJ4PSIxIi8%2BPHJlY3QgeD0iOS41IiB5PSI4IiB3aWR0aD0iNSIgaGVpZ2h0PSIxMyIgcng9IjEiLz48cmVjdCB4PSIxNiIgeT0iMyIgd2lkdGg9IjUiIGhlaWdodD0iMTgiIHJ4PSIxIi8%2BPC9zdmc%2B">
  <img alt="Python" src="https://img.shields.io/badge/Python-151C2B?style=flat-square&logo=python&logoColor=A970FF">
  <img alt="Machine Learning" src="https://img.shields.io/badge/Machine%20Learning-151C2B?style=flat-square&logo=scikitlearn&logoColor=A970FF">
</p>

</div>

---

## `$ python -i bio.py`

```python
"""Bio executável"""

from collections.abc import Iterable
from dataclasses import dataclass

import pandas as pd


@dataclass(frozen=True)
class Perfil:
    nome: str
    base: str
    competencias: tuple[str, ...]
    stack: tuple[str, ...]
    foco: tuple[str, ...]


fernando = Perfil(
    nome="Fernando Figueiredo",
    base="10+ anos em Comunicação, Estratégia de Conteúdo e Storytelling",
    competencias=(
        "Análise de Dados",
        "Pensamento Analítico",
        "Comunicação Estratégica",
    ),
    stack=("SQL", "Power BI", "Python", "Machine Learning"),
    foco=(
        "Analista de Dados",
        "Data Analytics",
        "Business Intelligence Analyst",
        "Product Analyst",
        "Marketing Analytics",
    ),
)

# Repertório em formato longo: um domínio, uma habilidade por linha.
repertorio = pd.DataFrame(
    {
        "dominio": ["Comunicação", "Comunicação", "Dados", "Dados"],
        "habilidade": ["narrativa", "estratégia", "análise", "machine learning"],
    }
)


def bloco(titulo: str, corpo: str) -> None:
    print(f"\n\n{titulo}")
    print(corpo)


def espacado(itens: Iterable[str]) -> str:
    return "\n\n".join(itens)


def bio(p: Perfil, repertorio: pd.DataFrame) -> None:
    leitura = repertorio.groupby("dominio", sort=False)["habilidade"].agg(" · ".join)

    print(f"\n{p.nome.upper()}")
    print("=" * 64)

    bloco("BASE", f"  {p.base}")
    bloco("COMPETÊNCIAS", f"  {' · '.join(p.competencias)}")
    bloco("STACK", f"  {' · '.join(p.stack)}")
    bloco("FOCO", espacado(f"  → {cargo}" for cargo in p.foco))
    bloco(
        "LEITURA DOS DADOS",
        "\n" + espacado(f"  {dominio:<14} {hab}" for dominio, hab in leitura.items()),
    )
    bloco(
        "HIPÓTESE",
        espacado(
            (
                "  Comunicação + narrativa + pensamento analítico",
                "  = capacidade de transformar informação em entendimento.",
            )
        ),
    )
    bloco("OUTPUT", "  transformar dados em respostas.")


if __name__ == "__main__":
    bio(fernando, repertorio)
```

<details>
<summary><b>saída</b></summary>

```text
FERNANDO FIGUEIREDO
================================================================


BASE
  10+ anos em Comunicação, Estratégia de Conteúdo e Storytelling


COMPETÊNCIAS
  Análise de Dados · Pensamento Analítico · Comunicação Estratégica


STACK
  SQL · Power BI · Python · Machine Learning


FOCO
  → Analista de Dados

  → Data Analytics

  → Business Intelligence Analyst

  → Product Analyst

  → Marketing Analytics


LEITURA DOS DADOS

  Comunicação    narrativa · estratégia

  Dados          análise · machine learning


HIPÓTESE
  Comunicação + narrativa + pensamento analítico

  = capacidade de transformar informação em entendimento.


OUTPUT
  transformar dados em respostas.
```

</details>

---

## `$ ls projetos/`

**[Sistema Financeiro Brasileiro](https://github.com/fernandofigueiredo-data/sistema-financeiro-brasileiro)** · [ver o site](https://fernandofigueiredo-data.github.io/sistema-financeiro-brasileiro/)

Análise das 1.622 instituições financeiras do IF.data (Banco Central, junho/2026) em Excel, SQL, Power BI e Python, com um estudo de estatística inferencial. Os números foram conferidos de uma ferramenta para outra.

| Ferramenta | O que a análise mostrou |
|---|---|
| Excel | O TCB b1 (bancos comerciais, múltiplos com carteira comercial e Caixa) reúne 7,2% das instituições e 73,3% do ativo do sistema |
| SQL | As 5 maiores instituições detêm 52,1% do ativo (58,0% por conglomerado) |
| Power BI | R$ 19,5 tri em ativos; a média simples do ROE (0,8%) esconde um ROE agregado de 7,52% |
| Python | As 756 instituições sem agência são cooperativas, não bancos digitais |

**[Eleições presidenciais no Brasil, 2014–2026](https://github.com/fernandofigueiredo-data/eleicoes-presidenciais-br)** · [ver o site](https://eleicoes-presidenciais-br.vercel.app)

O TSE publica o resultado por zona eleitoral, em arquivos separados por eleição e turno, sem indicadores do município. O projeto liga 8 turnos (340.702 linhas, 5.571 municípios) a população, alfabetização e PIB do IBGE, do arquivo bruto até um site interativo. Os totais conferem com os do TSE nos 8 turnos, e 41 testes automatizados rodam no GitHub Actions.

| Ferramenta | O que o projeto mostra |
|---|---|
| Python | Coleta rastreável (SHA-256) e limpeza em modelo estrela |
| statsmodels | Na regressão ponderada com controle por região e alfabetização, a associação entre dobrar a renda do município e o voto cai de 8,8 para 1,7 ponto percentual e deixa de se distinguir de zero |
| SQL | Banco relacional em SQLite, com restrições, triggers, funções de janela e views |
| Power BI | Modelo estrela e 55 medidas DAX |
| JavaScript | Site com mapa, filtros cruzados e exportação em CSV; 340 de 340 indicadores iguais aos do Power BI |

**[Bilheteria do cinema brasileiro](https://github.com/fernandofigueiredo-data/bilheteria-cinema-brasileiro-analytics)** · [ver o dashboard](https://bilheteria-cinema-brasileiro-analytics.onrender.com) (a primeira visita pode levar cerca de 1 minuto)

O cinema brasileiro voltou ao nível de antes da pandemia? Análise de 60 milhões de registros de bilheteria diária da ANCINE (2014 a setembro de 2026), com pipeline em DuckDB, notebook em pandas e dashboard em Dash. As duas fontes da ANCINE descrevem as mesmas exibições, então cada pergunta usa só uma delas; somá-las duplicaria o público. Comparações com 2026 usam os mesmos meses dos outros anos, e os limites estão declarados: sem preço nem receita nos dados, tudo é associação.

| Pergunta | Achado |
|---|---|
| Voltou ao nível de 2019? | Não. Em 2025, 65% do público de 2019 (115 milhões de espectadores contra 178 milhões); de janeiro a setembro de 2026, 77% |
| É falta de cinema? | Não: 3.595 salas contra 3.601 e 4,39 milhões de sessões contra 4,40 milhões. O que caiu foi o público por sessão, de 40 para 26 pessoas |

**[Power BI Layout Agent](https://github.com/fernandofigueiredo-data/powerbi-layout-agent-automation)**

Plugin do Claude Code que reorganiza o layout de relatórios Power BI (.pbix): grade de 12 colunas, alinhamento e leitura em Z. Só a posição e o tamanho dos visuais mudam; dados, medidas, filtros e formatação ficam intactos, e o resultado vai para uma cópia. A nota de layout mede a aderência às regras do próprio plugin, então 100 prova consistência, não legibilidade, e por isso a conferência final é visual.

| Caso | Resultado |
|---|---|
| Exemplo do repositório | Nota de layout de 48,9 para 100; a checagem passa de 1 sobreposição e 18 avisos para zero |
| Painel IFData (Banco Central), 2 páginas e 18 visuais | Nota de 60,6 para 100; a comparação confirma que só a geometria mudou |
| Teste no Power BI Desktop | Apareceram problemas que a nota não captura: rótulo da rosca cortado e tabela com 5 linhas em vez de 7. A versão 0.3.1 passou a sinalizar gráficos que encolhem demais |

**[Manual de Análise de Dados](https://github.com/fernandofigueiredo-data/manual-analise-de-dados)** · [ver o site](https://manual-analise-de-dados.vercel.app)

Guia de referência em português que segue a ordem real de um projeto: importar, conhecer, limpar, descrever, explorar, testar, modelar e comunicar. Todo o código é executado na geração do site, e a verificação automática confirma que 10.292 de 10.292 trechos dos materiais de origem estão nas páginas.

| Parte | O que mostra |
|---|---|
| Estudo de caso (ANAC) | 2,75 milhões de voos e 238 mil reclamações: cada ponto percentual a mais de voos cancelados acompanha 7,0 reclamações a mais por 100 mil passageiros (IC 95%: 3,0 a 11,0); um ponto a mais de chegadas atrasadas não se distingue de zero, e o teste placebo passa |
| Machine Learning | 10 notebooks reescritos a partir de exercícios de curso e revisados: 59 problemas registrados e corrigidos, como vazamento de dados e avaliação feita no próprio treino |
| Qualidade do site | 0 violações de acessibilidade (WCAG 2.2 AA) em 73 páginas e Lighthouse de 98 a 99 em desempenho |

---

## `$ cat formacao.md`

**Formação técnica em dados**

| Área | Formação | Instituição |
|---|---|---|
| Python | Curso completo de Python | Curso em Vídeo — Gustavo Guanabara |
| SQL | CS50's Databases with SQL | Harvard University |
| Power BI | Power BI para Análise de Dados | Preditiva Analytics |
| Análise de Dados | Formação Analista de Dados | Asimov Academy |
| Machine Learning | Machine Learning Specialization | DeepLearning.AI · Stanford University |

---

## `$ contact --list`

```console
email     fernandofigueiredo123@gmail.com
linkedin  in/fernandofigueiredoalves
```

[**LinkedIn**](https://www.linkedin.com/in/fernandofigueiredoalves/) · [**E-mail**](mailto:fernandofigueiredo123@gmail.com)

<!--
  TRACK B — seção de métricas do GitHub.
  Descomentar somente quando as três condições estiverem satisfeitas:
    1. os commits estiverem sendo contabilizados no grafo de contribuições;
    2. "Include private contributions on my profile" estiver ligado nas configurações;
    3. existirem ao menos dois repositórios públicos.
  Antes disso, estes cartões exibem zeros.

---

## `$ git log --stat`

<div align="center">
<img alt="Estatísticas do GitHub de Fernando Figueiredo" src="https://github-readme-stats.vercel.app/api?username=fernandofigueiredo-data&show_icons=true&hide=stars,issues&hide_border=true&bg_color=00000000&title_color=00E5FF&icon_color=A970FF&text_color=AAB8CC">
<img alt="Gráfico de atividade de contribuições" src="https://github-readme-activity-graph.vercel.app/graph?username=fernandofigueiredo-data&hide_border=true&bg_color=00000000&color=AAB8CC&line=00E5FF&point=A970FF&area=true">
<img alt="Animação da cobra percorrendo o gráfico de contribuições" src="https://raw.githubusercontent.com/fernandofigueiredo-data/fernandofigueiredo-data/output/snake-dark.svg">
</div>
-->
