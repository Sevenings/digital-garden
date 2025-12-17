---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/similaridade-entre-frases/"}
---

#conceito 
# Similaridade entre Frases
---
Ver também: [[Estágio/Projetos/13 - Treinar LLM/Embeddings\|Embeddings]]

Há métricas para se medir a similaridade entre frases. 
- Dot Product
- Cossine Distance
- Distância

## Calculando a similaridade em python
```python
# Compara a similaridade entre palavras usando embeddings pré-treinados com a biblioteca spaCy.
import spacy

# Carregue um modelo pré-treinado (certifique-se de tê-lo instalado, por exemplo:
# python -m spacy download en_core_web_md ou pt_core_news_md para português)
# O modelo 'md' (médio) ou 'lg' (grande) inclui vetores de palavras.
nlp = spacy.load("pt_core_news_md")

# Você pode comparar a similaridade:
palavra1 = "Homem"
palavra2 = "Mulher"

token1 = nlp(palavra1)[0]
token2 = nlp(palavra2)[0]
print(f"Similaridade entre '{palavra1}' e '{palavra2}': {token1.similarity(token2)}")
```