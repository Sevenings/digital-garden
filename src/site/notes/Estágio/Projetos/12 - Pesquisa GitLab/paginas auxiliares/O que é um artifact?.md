---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/o-que-e-um-artifact/"}
---


# O que é um artifact?

No GitLab, um artefato (ou artifact) é um conjunto de arquivos e diretórios gerados por um job (tarefa) em um pipeline de CI/CD após sua execução. Esses arquivos são armazenados no servidor do GitLab e ficam disponíveis para download ou uso por jobs subsequentes no mesmo pipeline. 
Principais características e usos

- Resultados de jobs: Os artefatos são essencialmente os subprodutos concretos do seu processo de CI/CD. Eles podem incluir:
    - Binários compilados ou pacotes de distribuição (como arquivos .zip, .jar, .war).
    - Arquivos de log gerados durante a execução.
    - Relatórios de testes, cobertura de código ou segurança.
    - Documentação gerada automaticamente.
- Compartilhamento entre jobs: A principal função dos artefatos é permitir que os resultados de um job (por exemplo, o job de "build" ou compilação) sejam automaticamente passados para jobs em estágios posteriores (como o job de "teste" ou "deploy"). Isso evita a necessidade de refazer o trabalho em cada etapa.
- Acesso e download: Você pode acessar e baixar os artefatos de um job diretamente na interface do usuário do GitLab, na página de detalhes do job. Eles são geralmente empacotados em um único arquivo comprimido (como .zip ou .tar).
- Expire_in: É possível definir um tempo de expiração para os artefatos usando a palavra-chave artifacts:expire_in no arquivo .gitlab-ci.yml, o que ajuda a gerenciar o espaço de armazenamento.
- Diferença do Cache: Diferente do cache, que é usado principalmente para armazenar dependências de projeto (como pacotes baixados da internet) e otimizar a velocidade de execução do runner em diferentes execuções de pipeline, os artefatos são os resultados gerados pelo próprio job e são gerenciados pelo servidor do GitLab. 

Em resumo, os artefatos são cruciais para a eficiência e funcionalidade dos pipelines de CI/CD no GitLab, garantindo que os resultados intermediários sejam persistidos e compartilhados conforme necessário. 