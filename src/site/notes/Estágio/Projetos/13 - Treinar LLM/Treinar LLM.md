---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/treinar-llm/"}
---


#pesquisa 
# Treinar LLM
---
Essa pesquisa faz parte do projeto de conseguir, até quarta-feira dia 17 de dezembro de 2025, treinar uma LLM, ou especializar uma para alguma tarefa.

O objetivo dessa pesquisa é conseguir reunir informações sobre LLMs, processos de fine tuning, possíveis aplicações, RAG, bibliotecas... para que eu possa decidir o que fazer depois.
## Por onde começar?
- Garanta os fundamentos: Como é feito a [[Estágio/Projetos/13 - Treinar LLM/Tokenização\|Tokenização]]? E o que são [[Estágio/Projetos/13 - Treinar LLM/Embeddings\|Embeddings]]? São conceitos fundamentais para processamento de linguagem natural.
- Dar uma olhada no módulo 1 do [curso da Cohere](https://cohere.com/llmu).
### Recursos de aprendizado online
- **Cursos Introdutórios:**
    - Generative AI for Beginners da Microsoft: Um curso abrangente de 18 lições. 
    - - [LLM University da Cohere](https://www.google.com/url?sa=i&source=web&rct=j&url=https://cohere.com/llmu&ved=2ahUKEwjfnNygurWRAxVtlJUCHQK7DkAQy_kOegYIAQgMEAM&opi=89978449&cd&psig=AOvVaw2cFSHkmpk_H-D712YAGu5-&ust=1765539755027000): Cobre do básico ao avançado em LLMs.
    - Introdução a Modelos de Linguagem Grandes (LLMs) no Google Cloud: Um curso gratuito oferecido pelo Google.
- **Tutoriais Práticos:**
    - [Tutoriais do DataCamp](https://www.datacamp.com/pt/tutorial/how-to-train-a-llm-with-pytorch) sobre como treinar LLMs com PyTorch.
    - O curso de NLP da Hugging Face é fundamental para entender a arquitetura de transformadores e usar suas ferramentas.
- **Comunidades:**
    - Fóruns no Reddit (como [r/LLMDevs](https://www.reddit.com/r/LLMDevs/) e r/brdev) são ótimos para dicas e discussões práticas.

---
## Possíveis aplicações
- [[Estágio/Projetos/13 - Treinar LLM/Criar um serviço MCP\|Criar um serviço MCP]]
- Fazer fine tuning de um modelo

---
## Conceitos fundamentais
- [[Estágio/Projetos/13 - Treinar LLM/Tokenização\|Tokenização]] e [[Estágio/Projetos/13 - Treinar LLM/Embeddings\|Embeddings]]
- [[Estágio/Projetos/13 - Treinar LLM/Similaridade entre frases\|Similaridade entre frases]]
- [[Estágio/Projetos/13 - Treinar LLM/Attention\|Attention]]
- [[Estágio/Projetos/13 - Treinar LLM/Normalização\|Normalização]]
- [[Estágio/Projetos/13 - Treinar LLM/Transformer Models\|Transformer Models]]
- [[Estágio/Projetos/13 - Treinar LLM/Context Size\|Context Size]]
- [[Unembedding Matrix\|Unembedding Matrix]]
- [[Estágio/Projetos/13 - Treinar LLM/Softmax\|Softmax]]
- [[Language models Temperature\|Language models Temperature]]
- [[Query Vector\|Query Vector]]
- [[Value Matrix\|Value Matrix]]
- [[Transfer Learning\|Transfer Learning]]

### Minha trilha de materiais
- [What are word and sentence embeddings?](https://cohere.com/llmu/sentence-word-embeddings)
- [What is Similarity Between Sentences?](https://cohere.com/llmu/what-is-similarity-between-sentences)
- [What Is Attention in Language Models?](https://cohere.com/llmu/what-is-attention-in-language-models)
- [What Are Transformer Models and How Do They Work?](https://cohere.com/llmu/what-are-transformer-models)
- [Mas o que é um GPT? Introdução visual aos Transformadores | Aprendizagem profunda, capítulo 5](https://www.youtube.com/watch?v=wjZofJX0v4M)
- [Atenção em transformadores, explicada visualmente | Capítulo 6, Aprendizado Profundo](https://www.youtube.com/watch?v=eMlx5fFNoYc)
- [RAG vs. Fine Tuning](https://www.youtube.com/watch?v=00Q0G84kq3M)
- [What is Model Context Protocol](https://modelcontextprotocol.io/docs/getting-started/intro)
- [Building an MCP server](https://modelcontextprotocol.io/docs/develop/build-server)
- [Biblioteca spacy](https://spacy.io/api)

Exemplo de uso de um MCP ![Pasted image 20251215085843.png](/img/user/ZX%20Imagens/Pasted%20image%2020251215085843.png)

## Curiosidades:
- [x] Conseguir manipular e fazer operações no espaço semântico
- [ ] Consigo ter acesso a uma função de [[Estágio/Projetos/13 - Treinar LLM/Attention\|Attention]]? 
- [x] Consigo ter acesso a uma [[Estágio/Projetos/13 - Treinar LLM/Softmax\|Softmax]]? 
- [ ] Consigo implementar um MCP?

## Ferramentas
- [Biblioteca Fastai](https://docs.fast.ai/text.learner.html)
- [Biblioteca spaCY](https://spacy.io/api)
