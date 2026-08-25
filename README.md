# Projeto IMDb - Análise de Dados e Dashboard

## 📌 Descrição do Projeto
Este projeto consiste em uma análise exploratória de dados e no desenvolvimento de um dashboard interativo no **Power BI** a partir de uma base de dados do IMDb (`world_imdb_movies`). O objetivo principal é responder a perguntas estratégicas de negócio relacionadas ao desempenho de filmes, faturamento, avaliações dos usuários (IMDb) e resultados financeiros ao longo dos anos.

---

## ❓ Perguntas de Negócio Respondidas

1. **Total de Filmes:** Qual é a quantidade total de filmes analisados na base de dados?
2. **Média IMDB Pós 2000:** Qual é a média das avaliações do IMDb para filmes lançados após o ano 2000?
3. **Resultado Financeiro Total:** Qual o resultado financeiro consolidado (Lucro/Prejuízo) gerado pelos filmes na base?
4. **Desempenho por Gênero:** Como o resultado financeiro total se distribui entre os diferentes gêneros cinematográficos?
5. **Classificação Crítica:** Qual o status de crítica atribuído aos filmes com base em suas pontuações e desempenho?

---

## 📐 Medidas DAX Desenvolvidas

* **Total de Filmes (Ponto 21):**
  ```dax```
  Total de Filmes = COUNTROWS('imdb_movies')
Média IMDB Pós 2000 = 
CALCULATE(
    AVERAGE('imdb_movies'[rating_imdb]),
    'imdb_movies'[ano] > 2000
)Resultado Financeiro Total = 
SUM('imdb_movies'[faturamento]) - SUM('imdb_movies'[orcamento])
