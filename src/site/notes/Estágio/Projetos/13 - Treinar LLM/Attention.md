---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/attention/"}
---

#conceito 
# Attention
---
Ver depois: [[Multihead Attention\|Multihead Attention]]

Então, Attention se refere ao processo de poder encontrar qual o significado de uma palavra em determinado contexto. O problema acontece quando temos uma certa palavra que pode ter vários significados diferentes, em contextos diferentes. Dessa forma, fica evidente que o sentido real da palavra não está associado literalmente à escrita dela, ou ao radical, nem nada, é uma combinação elementar entre esses fatores e o contexto em que está sendo empregada. 

> [!Frase chique]
> Cada palavra aponta para um significado, e nosso trabalho é encontrar para qual significado uma palavra está apontando.

Então, pegando um exemplo como manga. Na verdade, não existe "A Manga". Em verdade existem várias Mangas, e no caso temos ao menos 2: a manga da camisa, e a manga fruta. No caso, para os computadores, serão `manga1` e `manga2`. 

Para identificar se `manga` é `manga1` ou `manga2` deve-se analisar o contexto da frase em que ela aparece. 

Um método em que ele nos apresentou é olhar as palavras próximas e encontrar as [[Estágio/Projetos/13 - Treinar LLM/Similaridade entre frases\|similaridades]] entre elas por meio de uma matriz de similaridades. Então, no caso da `manga` podemos comparar a similaridade dela com todas as outras palavras da frase, por exemplo, na frase _"Comi a manga"_ Comi e manga têm uma similaridade. Então podemos dizer que `manga` é igual a `1*manga + 0.09*comi`. Por outro lado,  se a frase fosse `a minha manga da camisa`, então `manga` e `camisa` teriam semelhança, e `manga` seria igual a `1*manga + 0.10*camisa`. 

No entanto, o procedimento de attention mostrado é muito simples, e ele diz que depois deve-se ver o que é [[Multihead Attention\|Multihead Attention]], que é a versão mais moderna.
