---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/embeddings/"}
---

#conceito 
# Embeddings
---
Ver também: [[Estágio/Projetos/13 - Treinar LLM/Tokenização\|Tokenização]], [[Estágio/Projetos/13 - Treinar LLM/Similaridade entre frases\|Similaridade entre frases]]

Embeddings são a forma de pegar um [[Estágio/Projetos/13 - Treinar LLM/Tokenização\|token]], e atribuir significado a ele. Basicamente, cada token tem um ID, e achar o embedding, é atribuir a esse ID um vetor de números, que esse vetor, representa a coordenada dele em um espaço vetorial que poderia ser chamado "espaço semântico", nesse espaço, tokens / palavras próximas, tem significados próximos.

## Como calcular os embeddings de uma palavra em python
Em python, existem várias bibliotecas para calcular embeddings de alguma palavra. No geral (naõ sei se há outro método), a função de criação de embeddings geralmente é feita por meio de redes neurais.

Bibliotecas:
- spacy (Utilizei esta nos exemplos)
- genshin

**Imprimindo os pesos de um embedding na tela:**
```python
# Vê a cara de um embedding de palavra usando spaCy
import spacy

# Carregue um modelo pré-treinado (certifique-se de tê-lo instalado, por exemplo:
# python -m spacy download en_core_web_md ou pt_core_news_md para português)
# O modelo 'md' (médio) ou 'lg' (grande) inclui vetores de palavras.
nlp = spacy.load("pt_core_news_md")

palavra = "O rato roeu a roupa do rei de Roma"
token = nlp(palavra)[0]
embedding = token.vector

print(f"O embedding de '{palavra}' é: \n{embedding}")
```

**Vendo as dimensões de um embedding:**
```python
# Vê a dimensão de um embedding de palavra usando spaCy
import spacy

# Carregue um modelo pré-treinado (certifique-se de tê-lo instalado, por exemplo:
# python -m spacy download en_core_web_md ou pt_core_news_md para português)
# O modelo 'md' (médio) ou 'lg' (grande) inclui vetores de palavras.
nlp = spacy.load("pt_core_news_md")

palavra = "exemplo"
token = nlp(palavra)[0]
embedding = token.vector

print(f"O embedding da palavra '{palavra}' tem {len(embedding)} dimensões.")
```
