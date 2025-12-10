---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/ciclo-de-vida-dev-ops/"}
---


# Ciclo de Vida DevOps
Um software passa por diversas etapas desde a idealização até chegar em produção, e em produção, essas etapas vão se repetindo em loop para manter o software disponível e quando vão corrigir bugs ou adicionar features. 

## As fases do ciclo de vida DevOps
1. **Planejamento**: Definir a visão do projeto, priorizar tarefas, gerenciar issues, [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Épico\|épicos]] e o _[[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Backlog\|backlog]]_.
2. **Codificação**: A fase onde os desenvolvedores escrevem o código, realizam revisões de código e gerenciam repositórios Git (através de _Merge Requests_ ou _Pull Requests_).
3. **Build**: Compilar o código-fonte em um artefato executável (como uma imagem Docker ou binário de aplicação).
4. **Teste**: Execução automatizada de testes (unitários, de integração, de segurança) para garantir a qualidade e a segurança do código antes da implantação.
5. **Lançamento (Releases)**: Gerenciamento do lançamento do código em ambientes de produção, incluindo aprovações e orquestração de pipelines.
6. **Deploy**: A fase onde o artefato é instalado e configurado em um ambiente de produção ou _staging_.
7. **Operação**: Manter o ambiente em funcionamento, gerenciar a infraestrutura, garantir a estabilidade e a disponibilidade do sistema.
8. **Monitoramento**: Coletar dados sobre o desempenho da aplicação, a saúde do sistema e a experiência do usuário. O feedback obtido aqui alimenta a fase de **Planejamento**, reiniciando o ciclo.