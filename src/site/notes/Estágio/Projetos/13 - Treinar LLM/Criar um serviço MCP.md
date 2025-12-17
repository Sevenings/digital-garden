---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/criar-um-servico-mcp/"}
---

#conceito 
# Model Context Protocol
---
É um protocolo usado para criar serviços que podem ser consumidos pelas LLMs como ferramentas de consultas externas.

Um serviço MCP é bem fácil de ser construído utilizando a biblioteca que eles provém, muito semelhante à uma API Flask.

## Tool Calling
Alguns dos modelos recentes vêm com a capacidade de Tool Calling, que é a capacidade de entregar a resposta na forma de um JSON que simboliza a chamada de uma função. Dessa forma, a IA consegue interagir com um sistema.

Pensando na implementação, esse recurso é implementado direto no treinamento do modelo. É feito um treinamento que ensina o modelo a como responder as coisas no formato JSON.
## Referências
- [What is the Model Context Protocol](https://modelcontextprotocol.io/docs/getting-started/intro)
- [Build an MCP server](https://modelcontextprotocol.io/docs/develop/build-server)
- [Build an MCP client](https://modelcontextprotocol.io/docs/develop/build-server#test-with-commands)