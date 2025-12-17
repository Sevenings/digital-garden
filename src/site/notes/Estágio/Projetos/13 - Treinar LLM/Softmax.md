---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/softmax/"}
---

#conceito 
# Softmax
---
É uma função utilizada para normalizar os chamados "logits", que são os valores em vetores de machine learning. A ideia é pegar os resultados que representam as probabilidades de se obter um valor (que estão em formato bruto, numérico) e ranquear de forma a dar uma distribuição probabilística, de forma que:
- A soma de todos dê 1 (100%).
- Os negativos ganhem sentido
- Os negativos não estraguem a distribuição da função
## Fórmula

$$
\sigma(z)_i = \frac{e^{z_i}}{\sum^K_{j=1}e^{z_j}} \qquad \textrm{para } i = 1, ..., K
$$
Onde:
- $z_i$ é o i-ésimo elemento do vetor de entrada
- $e^{z_i}$ é a função exponencial do elemento de entrada
- O denominador é a soma das exponenciais de todos os elementos no vetor de entrada, garantindo que a soma de todas as saídas seja 1.
## Exemplo de implementação em python
```python
# Exemplo de uso da função softmax em Python

from scipy.special import softmax
import numpy as np
scores = np.array([1.0, 2.0])
print(softmax(scores))
print(np.sum(softmax(scores)))  # Deve ser igual a 1.0
```

