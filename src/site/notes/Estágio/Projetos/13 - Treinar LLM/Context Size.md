---
{"dg-publish":true,"permalink":"/estagio/projetos/13-treinar-llm/context-size/"}
---

#conceito 
# Context Size
---
No contexto de _transformers_ e modelos de linguagem (LLMs), o **tamanho do contexto** (ou _context size_, frequentemente referido como **janela de contexto** ou _context window_ em inglês) refere-se à ==**quantidade máxima de texto, medida em _tokens_, que o modelo pode processar ou "lembrar" em uma única passagem**==. 

Essa janela de contexto determina quanta informação anterior o modelo pode considerar ao gerar a próxima palavra ou ao responder a uma consulta. 

## Pontos Chave:

- **Tokens:** O texto de entrada é dividido em unidades menores chamadas _tokens_ (que podem ser palavras inteiras, subpalavras ou caracteres). O tamanho do contexto é o número máximo desses _tokens_ que o modelo pode ingerir de uma vez.
- **Mecanismo de Autoatenção (_Self-Attention_):** A arquitetura Transformer usa um mecanismo de autoatenção que permite que cada _token_ na sequência de entrada avalie a relevância dos outros _tokens_, mesmo que estejam distantes.
- **Limitação Computacional:** O principal motivo para a existência de um tamanho de contexto fixo e limitado é o custo computacional. O mecanismo de autoatenção padrão tem uma complexidade que cresce quadraticamente com o comprimento da sequência (O(n²)). Dobrar o tamanho do contexto quadruplica aproximadamente os requisitos de memória e computação.
- **Impacto no Desempenho:** Uma janela de contexto maior permite que o modelo compreenda e raciocine sobre documentos mais longos, conversas mais extensas ou bases de código maiores, incorporando mais informações em sua saída. Modelos com janelas de contexto pequenas tendem a "esquecer" informações do início de um _prompt_ muito longo.
- **Unidades de Medida:** O tamanho do contexto é geralmente especificado em milhares de _tokens_ (ex: 4k, 8k, 32k, 128k, até milhões de _tokens_ em modelos mais recentes).