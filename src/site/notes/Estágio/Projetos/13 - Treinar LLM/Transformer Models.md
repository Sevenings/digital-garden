---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/transformer-models/"}
---


#conceito 
# Transformer Models
---
- Aplicações em:
    - Text Generations
    - Semantic Search
- Consegue carregar o contexto do texto
- O que fazem é encontrar a próxima palavra
- Análogos às redes neurais, mas são melhores

## Estrutura de um Transformer
1. Input
2. Tokenization 
3. Embedding
4. Positional encoding
5. Series of transformer blocks: 
    1. Attention
    2. Feedforward
6. Softmax (Output)

### Features de um Transformer
_O que ele consegue fazer / Analisar_
1. **Tokenization:** Consegue ler as palavras, consegue descobrir palavras novas analisando a palavra, tolerância a entender conjugações, 
2. **Embedding:** Consegue encontrar o significado de uma palavra, o sentido, a semântica.
3. **Attention:** Consegue diferenciar o significado de uma palavra baseado no contexto.
4. **Positional encoding:** Consegue diferenciar o significado de uma frase baseado na ordem em que as palavras foram colocadas.

## Diferença para redes neurais
Pelo que entendi, transformers são baseados em redes neurais, mas eles têm camadas de Attention entre as redes neurais, que aumentam significativamente a performance deles.

## Pós-treino
Um dos problemas iniciais com os transformers é que eles foram treinados com dados da internet, e eles vão ter mais chances de repetir o que lhes foi ensinado, e pensando na tarefa de responder perguntas, a maioria das páginas da internet tem perguntas sem respostas, por exemplo: se perguntarmos "Qual é a capital do Brasil?", gostaríamos que ele respondesse "Brasília", mas na internet, poderia ter uma página que diz: "Qual a capital do Brasil?" e depois "Qual a população do Brasil?", então, é necessário que os Transformers passem por algum processo para que sejam treinados para responder perguntas. 

Uma forma de fazer isso é: após o treino principal, eles são passados por um pós-treino, com um dataset com perguntas e suas respostas. Assim como os humanos, eles são mais enviesados pela última coisa que leram, e dessa forma, após esse treinamento eles performam melhor para responder perguntas.

