# Aplicação de Métodos de Mineração de Dados sobre os Dados Abertos do ENEM 2023

Este repositório reúne os artefatos do Trabalho de Conclusão de Curso de **Gabriel Martins Spósito**, desenvolvido no curso de **Engenharia de Computação da UFES (CEUNES)**, com foco na aplicação de técnicas de **KDD**, **mineração de dados** e **aprendizado de máquina** sobre os microdados abertos do **ENEM 2023**.

O objetivo central do trabalho é analisar o perfil dos participantes do exame em nível nacional, com ênfase na comparação entre estudantes de **escolas públicas** e **escolas privadas**, identificando padrões socioeconômicos e fatores associados ao desempenho acadêmico.

## Contexto do trabalho

O estudo parte da premissa de que bases abertas governamentais permitem extrair conhecimento relevante para pesquisa e apoio à tomada de decisão. No caso do ENEM 2023, os microdados possibilitam avaliar relações entre:

- características socioeconômicas dos participantes;
- infraestrutura domiciliar e bens de consumo;
- escolaridade e ocupação dos responsáveis;
- tipo de escola;
- desempenho médio no exame.

O projeto segue a lógica do processo de **Descoberta de Conhecimento em Bases de Dados (KDD)**:

1. seleção dos dados;
2. limpeza e pré-processamento;
3. transformação das variáveis;
4. aplicação de algoritmos de mineração de dados;
5. interpretação dos resultados.

## Objetivo

Aplicar técnicas e modelos de mineração de dados em uma base aberta governamental, utilizando os microdados do ENEM 2023 para:

- comparar alunos de escolas públicas e privadas;
- identificar perfis distintos de estudantes;
- avaliar variáveis com maior influência sobre a média geral;
- extrair padrões frequentes relacionados ao contexto socioeconômico.

## Base de dados

A base principal utilizada no trabalho é formada pelos **microdados do ENEM 2023**, disponibilizados oficialmente pelo **INEP** em formato aberto.

Neste repositório, parte do processamento já está materializada nos arquivos em [`bases_limpas`](/d:/Desktop_git/TCC/bases_limpas), incluindo:

- [`base_dependencia_Privada.csv`](/d:/Desktop_git/TCC/bases_limpas/base_dependencia_Privada.csv)
- `base_dependencia_Publica.csv`
- [`base_dependencia_nulo.csv`](/d:/Desktop_git/TCC/bases_limpas/base_dependencia_nulo.csv)

As análises foram estruturadas principalmente a partir de variáveis socioeconômicas, escolares e da variável-alvo **`NU_MEDIA_GERAL`**, criada como média das notas das áreas avaliadas no exame.

## Técnicas utilizadas

O trabalho combina métodos descritivos e preditivos.

### Modelos aplicados

- **K-Means**: identificação de clusters de estudantes com perfis semelhantes.
- **Regressão Linear**: modelo de referência para estimar a média geral.
- **Árvore de Decisão Regressora**: análise interpretável de predição.
- **Random Forest Regressor**: modelo supervisionado com melhor desempenho entre os avaliados.
- **FP-Growth**: mineração de regras de associação para identificar padrões frequentes.

### Stack utilizada

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Mlxtend
- Jupyter Notebook

## Estrutura do repositório

```text
TCC/
├── bases_limpas/
│   ├── base_dependencia_Privada.csv
│   ├── base_dependencia_Publica.csv
│   ├── base_dependencia_nulo.csv
│   └── ...
├── limpeza.ipynb
├── projeto.ipynb
├── TCC_2_Gabriel_UFES.pdf
├── TCC_2_Gabriel_UFES_versao_2.docx
└── README.md
```

### Arquivos principais

- [`limpeza.ipynb`](/d:/Desktop_git/TCC/limpeza.ipynb): preparação, filtragem, transformação e separação das bases.
- [`projeto.ipynb`](/d:/Desktop_git/TCC/projeto.ipynb): execução dos modelos, geração de gráficos e análise comparativa.
- [`TCC_2_Gabriel_UFES.pdf`](/d:/Desktop_git/TCC/TCC_2_Gabriel_UFES.pdf): versão em PDF do trabalho.

## Principais etapas do projeto

### 1. Limpeza e seleção

Foram removidos atributos considerados irrelevantes para a análise proposta e tratados registros inconsistentes, ausentes ou sem utilidade prática para os modelos.

### 2. Construção da variável de desempenho

Foi criada a variável **`NU_MEDIA_GERAL`**, representando a média das notas das áreas do ENEM, utilizada como referência para os modelos preditivos.

### 3. Separação por tipo de escola

As bases foram segmentadas para permitir comparação entre:

- **escolas públicas**;
- **escolas privadas**;
- registros com informação ausente.

### 4. Mineração de dados

Os algoritmos foram aplicados sobre as bases processadas para comparar desempenho, importância de variáveis, formação de grupos e padrões frequentes.

## Principais resultados do TCC

Com base no texto do trabalho e nas análises implementadas no notebook:

- o **Random Forest** apresentou o melhor desempenho preditivo entre os modelos testados;
- a **renda familiar mensal** apareceu como o fator de maior importância para explicar a **média geral**;
- a **escolaridade dos responsáveis** também se destacou como variável fortemente associada ao desempenho;
- o **K-Means** identificou grupos com perfis socioeconômicos distintos, reforçando a presença de desigualdades estruturais;
- o **FP-Growth** evidenciou padrões de abundância e escassez de recursos entre os grupos analisados;
- a comparação entre escolas públicas e privadas mostrou realidades socioeconômicas bastante diferentes.

Em termos interpretativos, o trabalho converge para um ponto central: **o contexto socioeconômico é um dos principais determinantes do desempenho dos participantes do ENEM 2023**.

## Como executar

### Requisitos

Instale um ambiente Python com as bibliotecas abaixo:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend notebook jupyter
```

### Ordem sugerida

1. Execute [`limpeza.ipynb`](/d:/Desktop_git/TCC/limpeza.ipynb) para preparar e exportar as bases.
2. Execute [`projeto.ipynb`](/d:/Desktop_git/TCC/projeto.ipynb) para rodar os modelos e gerar os gráficos.

## Exemplos de análises presentes

O notebook principal contempla análises comparativas entre bases pública e privada para:

- dispersão entre valor real e valor previsto;
- importância das variáveis nos modelos supervisionados;
- perfis de clusters com K-Means;
- médias por cluster;
- regras de associação extraídas via FP-Growth.

## Contribuição acadêmica

O repositório documenta uma aplicação prática de mineração de dados educacionais sobre uma base aberta nacional de grande escala. Além de servir como suporte ao TCC, o material pode ser útil para:

- estudantes de computação e ciência de dados;
- pesquisadores em educação e políticas públicas;
- análises exploratórias sobre desigualdade educacional;
- estudos reprodutíveis com microdados do ENEM.

## Autoria

**Gabriel Martins Spósito**  
Engenharia de Computação - UFES / CEUNES

**Orientação:** Profª. Dra. Silvia das Dores Rissino

## Referência do trabalho

Se for citar este repositório ou o trabalho, utilize como referência principal o TCC:

**Spósito, Gabriel Martins.** *Aplicação de métodos de Mineração de Dados sobre os dados abertos do ENEM de 2023*. Universidade Federal do Espírito Santo, São Mateus, 2025.
