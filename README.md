<img width="2400" height="1254" alt="LinkedIn horizontal (1200×627)@2x" src="https://github.com/user-attachments/assets/438c71fa-7826-4046-960e-3bd161cf36ec" />
# Mulher no volante, perigo constante?

Análise dos dados abertos de acidentes nas rodovias federais, publicados pela Polícia Rodoviária Federal (PRF), para testar com dados um ditado popular bastante repetido.

**[Acesse o painel interativo](https://alinnebarrozo.github.io/Analise_dados_da_prf/)**

## Pergunta de negócio

Motoristas mulheres se envolvem em mais acidentes, ou em acidentes mais graves, do que motoristas homens?

## Fonte dos dados

* *Origem:* [Dados Abertos da PRF](https://www.gov.br/prf/pt-br/acesso-a-informacao/dados-abertos/dados-abertos-da-prf)
* *Bases usadas:* acidentes agrupados por ocorrência, por pessoa e por causa
* *Período:* janeiro de 2024 a agosto de 2026

## Ferramentas

Python, Pandas, SQL (DuckDB), Plotly, Streamlit e GitHub Pages

## Etapas do projeto

1. *Entendimento das bases:* leitura do dicionário de dados, tipos de variáveis e chaves de ligação entre as tabelas.
2. *ETL:* carga dos arquivos de todos os anos com checagem de colunas, limpeza de nulos e valores inválidos, padronização de categorias e registro de qualidade dos dados exportado em CSV.
3. *Junção das bases:* cruzamento por ocorrência e por pessoa em Pandas, refeito em SQL no DuckDB e conferido entre as duas versões.
4. *Modelagem:* modelo estrela com 2 tabelas fato e 4 dimensões, exportado em parquet, e dicionário de KPIs calculado em SQL.
5. *Análise e painel:* painel de data storytelling em 5 capítulos, do cenário geral até as descobertas.

## Principais achados

* Mulheres são 11,9% dos condutores envolvidos em acidentes e 56,8% dos passageiros.
* A letalidade entre condutores é de 1,73% para mulheres e 3,58% para homens.
* A associação entre sexo e gravidade do acidente é muito pequena (V de Cramér = 0,070).
* Considerando veículo, idade, fase do dia, tipo de trecho e dia da semana, a chance de óbito de um condutor homem cai de 2,09 para 1,76 vez a de uma condutora. A diferença diminui, mas continua existindo.
* Tipo de veículo (moto e bicicleta), madrugada, trecho rural e idade acima de 60 anos pesam mais na gravidade do que o sexo.

*Conclusão:* os dados não sustentam o ditado. As condutoras aparecem em menos acidentes e em acidentes menos letais, e o que mais explica a gravidade é o contexto do acidente, não o sexo de quem dirige.

## Limitações

* A base não informa quantos motoristas de cada sexo circulam nas rodovias nem quantos quilômetros cada um roda. Por isso os números mostram participação nos acidentes, não risco por motorista.
* Os resultados mostram associação, não causa.
* Os registros dependem do preenchimento feito no atendimento da ocorrência.

## Estrutura do repositório

* *Analise_PRF_ETL_SQL_Modelo.ipynb:* ETL, integração em SQL e modelo estrela
* *docs:* versão web do painel, publicada no GitHub Pages
* *painel_streamlit:* versão do painel em Python, com testes que conferem os números com o notebook

## Autora

*Alinne Barrozo*, analista de dados
[GitHub](https://github.com/alinnebarrozo)
