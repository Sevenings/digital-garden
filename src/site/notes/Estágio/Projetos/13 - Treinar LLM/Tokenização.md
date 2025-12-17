---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/tokenizacao/"}
---

#conceito
# Tokenização
---
Tokenização é a forma, ou o processo em que o modelo pega um texto e divide em partes menores, chamados tokens, para poder conseguir "ler" a frase e processar ela. A ideia é que é mais fácil ir lendo a frase pedaço por pedaço e juntando-os para criar um significado maior, do que conseguir pegar um blocão de texto e instantaneamente conseguir adivinhar o significado.

Há várias formas de se tokenizar. Pode-se dividir a frase carácter por carácter, já parece um bom começo, mas parece ser detalhado demais, deixando ineficiente. Então podemos dividir por palavras, que já parece mais robusto e adequado. 

No caso, hoje em dia é feito a divisão em Sub palavras. Eles dividem por palavras, mas se a palavra for maiorzinha, é provável que ela venha a ser dividida em sub-tokens. É uma abordagem bem interessante, pois no português por exemplo, as palavras tem um radical, e muitas variações possíveis, com prefixos, sufixos, número, gênero, conjugação, tempo, modo... de modo que se for catalogar cada uma, o dicionário de tokens deveria ser absurdo de grande. Dividindo em sub-palavras, o modelo fica mais suscetível a "deduzir" o significado de palavras desconhecidas. Um token top que parece que aparece frequentemente é o token "s", que geralmente vem no final e indica que uma palavra está no plural.

## Utilizando função de tokenização em python
```python
import spacy
from spacy.tokenizer import Tokenizer

# Carregue um modelo pré-treinado (certifique-se de tê-lo instalado, por exemplo:
# python -m spacy download en_core_web_md ou pt_core_news_md para português)
# O modelo 'md' (médio) ou 'lg' (grande) inclui vetores de palavras.
nlp = spacy.load("pt_core_news_md")

# Você pode comparar a similaridade:
texto = """Olá, mundo! Este é um exemplo de tokenização usando spaCy. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Vamos ver como o texto é dividido em tokens. SpaCy é uma biblioteca poderosa para processamento de linguagem natural.
Tokenização é o processo de dividir o texto em unidades menores, chamadas tokens. Isto pode incluir palavras, pontuação, números, etc.
"""

tokenizer = Tokenizer(nlp.vocab)

tokens = tokenizer(texto)

print(f"Tokens de '{texto}':")
for token in tokens:
    print(f"Token: {token.text}")
```