# Checkpoint 02 — SERS

## Grupo:

Andrey Crence Fernandes - RM 573840

Giulliana Maistro Brasolin - RM 569381

Mikaella Mirela Dos Santos Lucindo - RM 573775

Lara Dos Santos Cândido Alves - RM 573827

Lucas Parkin Devito - RM 573251

## Descrição da atividade

Repositório com as atividades práticas da disciplina **Soluções em Energias Renováveis e Sustentáveis**, aplicando Python e aprendizado de máquina (classificação e regressão) em dados do setor elétrico.


O trabalho está dividido em três etapas:

1. **Parte 1 — Classificação (Aula 06)** — desenvolvimento de um modelo de classificação com Regressão Logística para prever a condição da rede elétrica (variável `stabf`: estável ou instável), com separação dos dados em treino e teste, geração das previsões e avaliação por métricas de classificação e matriz de confusão.
2. **Parte 2 — Regressão (Aula 07)** — desenvolvimento de modelos de Regressão Linear para prever o valor numérico da variável `stab`, comparando dois modelos: um com as cinco variáveis de maior correlação absoluta com `stab` e outro com todas as variáveis cujos nomes começam com `tau` ou `g`, avaliados por R², MAE e MSE.
3. **Parte 4 — Desafio final: APIs, energias renováveis e aprendizado de máquina** — consulta a duas APIs públicas (ANEEL e Open-Meteo) e desenvolvimento de duas tarefas independentes, treinando e comparando três algoritmos em cada uma:
   - **Tarefa 1 — Classificação da fonte renovável:** prever se um empreendimento de geração é Solar, Eólica ou Hidráulica usando apenas a potência outorgada, a latitude e a longitude, com divisão estratificada entre treino e teste e avaliação por Accuracy, Precision, Recall, F1 e matriz de confusão.
   - **Tarefa 2 — Regressão da radiação solar:** estimar a radiação solar horária (`radiacao_w_m2`) a partir de temperatura, umidade, nuvens, vento e hora do dia, com divisão temporal entre treino e teste e avaliação por MAE, MSE e R², além do gráfico de valores reais × previstos.

## Arquivos

| Arquivo | Descrição |
|---|---|
| `parte_1_classificação/classificacao_estabilidade.ipynb` | Parte 1: classificação da estabilidade da rede elétrica com Regressão Logística |
| `parte_2_regressão/regressao_estabilidade.ipynb` | Parte 2: regressão linear de `stab` com dois conjuntos de variáveis |
| `parte_4_desafio_final/Desafio_Tarefa_1.ipynb` | Desafio final, Tarefa 1: classificação da fonte renovável (ANEEL) |
| `parte_4_desafio_final/Desafio_Tarefa_2.ipynb` | Desafio final, Tarefa 2: regressão da radiação solar (Open-Meteo) |

## Fontes dos dados analisados

### Partes 1 e 2 — Estabilidade da rede elétrica

| Dataset | Fonte | Link |
|---|---|---|
| Electrical Grid Stability Simulated Data | UCI Machine Learning Repository | https://archive.ics.uci.edu/dataset/471/electrical+grid+stability+simulated+data |

Arquivo no repositório: `datasets/Data_for_UCI_named.csv`

### Desafio final — Tarefa 1: Classificação da fonte renovável

- **Fonte:** API pública do SIGA — Sistema de Informações de Geração da ANEEL (sem token)
- **Portal:** https://dadosabertos.aneel.gov.br/
- **Conjunto de dados:** https://dadosabertos.aneel.gov.br/dataset/siga-sistema-de-informacoes-de-geracao-da-aneel
- **Recorte utilizado:** empreendimentos de geração dos tipos `UFV`, `EOL`, `UHE`, `PCH` e `CGH`, com até 1200 linhas consultadas por tipo, agrupados em três classes: Solar (`UFV`), Eólica (`EOL`) e Hidráulica (`UHE`, `PCH`, `CGH`)
- **Arquivo no repositório:** `datasets/aneel_classificacao_orange.csv`

### Desafio final — Tarefa 2: Regressão da radiação solar

- **Fonte:** API histórica do Open-Meteo (sem token)
- **Portal:** https://open-meteo.com/en/docs/historical-weather-api
- **Recorte utilizado:** dados horários estimados para Petrolina (PE), de 01/04/2025 a 30/06/2025, no fuso `America/Recife`, uma linha por hora local entre 7h e 17h
- **Arquivo no repositório:** `datasets/meteo_regressao_orange.csv`

## Ferramentas utilizadas

- Python (Pandas, NumPy, Matplotlib, Seaborn, scikit-learn)
- Google Colab

## Links dos arquivos no Google Colab

classificacao_estabilidade.ipynb:

https://colab.research.google.com/github/giu-mzx/Checkpoint_02_SERS/blob/main/parte_1_classifica%C3%A7%C3%A3o/classificacao_estabilidade.ipynb

regressao_estabilidade.ipynb:

https://colab.research.google.com/github/giu-mzx/Checkpoint_02_SERS/blob/main/parte_2_regress%C3%A3o/regressao_estabilidade.ipynb

Desafio_Tarefa_1.ipynb:

https://colab.research.google.com/drive/1ICF56ujwC7_A_2NSsl_obaOidQb1L4AK?usp=sharing

Desafio_Tarefa_2.ipynb:

https://colab.research.google.com/github/giu-mzx/Checkpoint_02_SERS/blob/main/parte_4_desafio_final/Desafio_Tarefa_2.ipynb
