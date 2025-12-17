---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/pesquisa-gitlab/"}
---

#pesquisa 
# Pesquisa GitLab
---
10/12/2025

Esta é a pesquisa básica que fiz acerca do GitLab. Ela responde perguntas básicas sobre: o que é essa plataforma, quais suas aplicações, quais são seus casos de uso e quais suas semelhanças e diferenças com o GitHub, além de exemplificar como utilizá-la para salvar um repositório e como criar uma pipeline de CI/CD.

> [!INFO]
A pesquisa contém alguns hyperlinks para conceitos primitivos que ainda não tinha conhecimento sobre, conceitos como o [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Ciclo de Vida DevOps\|Ciclo de Vida DevOps]] e [[O que é um artifact?\|Artifacts]].
### Conteúdos
- [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Informações gerais sobre o GitLab\|Informações gerais sobre o GitLab]]
    - [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#O que é o GitLab?\|O que é o GitLab]]
    - [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Qual a diferença para o Github?\|Qual a diferença para o Github?]]
    - [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Especialidades do GitLab\|Especialidades do GitLab]]
    - [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Especialidades do GitHub\|Especialidades do GitHub]]
- [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Usando o GitLab\|Minha Experiência com o GitLab]]
- [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Conclusão pessoal Vale a pena?\|Conclusão pessoal: Vale a pena?]]
## Informações gerais sobre o GitLab
### O que é o GitLab?
Gitlab é uma plataforma semelhante ao GitHub, onde pode-se hospedar o código de um repositório Git, mas focado em ser uma ferramenta para operações de DevOps, com suporte a pipelines de CI/CD.

Assim como o GitHub, ele é um sistema de controle de versão (VCS) e permite hospedar repositórios Git online, acessar via um navegador e colaborar usando um workflow baseado em merges. Porém, ele enfatiza CI/CD, permitindo criar pipelines com um simples arquivo .yaml.
### Qual a diferença para o Github?
Ambos são gerenciadores de repositórios Git, e oferecem controle de versão, mas o **ponto chave** reside na abordagem e conjunto de recursos. O GitHub foca primariamente na colaboração e na comunidade de código aberto, enquanto o GitLab oferece uma **plataforma DevOps** completa e integrada, "tudo-em-um".
### Especialidades do GitLab
- **Auto-Hospedagem Gratuita** — O GitLab oferece uma versão de comunidade que nos permite hospedá-la em nossos próprios servidores, sem custo. 
 - **CI/CD Nativo e Integrado** — Aparenta ser o feature mais chamativo do GitLab,
- **Gerenciamento Abrangente do [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Ciclo de Vida DevOps\|Ciclo de Vida DevOps]]:**
    - **Segurança Integrada (DevSecOps)** — Varredura de segurança de aplicações estática e dinâmica ([[SAST/DAAST\|SAST/DAAST]]), gerenciamento de vulnerabilidades e digitalização de infraestrutura como código (IaC) integrados, sem depender de aplicativos de marketplace externos.
    - **[[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Container Registry\|Registro de containers (Container Registry)]] Integrado** — Registro de contêineres nativo embutido na plataforma 
- **Organizar os repositórios em Grupos e Subgrupos** — O GitLab permite organizar os repositórios em Grupos e depois em Subgrupos, criando uma hierarquia de projetos mais granular e organizada. No GitHub, a organização é mais plana, focando em repositórios pertencentes a usuários e organizações.
- **Controle de Implementação e [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Sinalizadores de Funcionalidade\|Sinalizadores de Funcionalidade]]** —
### Especialidades do GitHub
- **Hospedagem colaborativa de código** — O GitHub se destaca no controle de versão e colaboração, com recursos como pull requests, revisões de código e proteção de branches para fluxos de trabalho em equipe.
- **GitHub Actions (CI/CD)** — O GitHub Actions permite que os usuários automatizem fluxos de trabalho, desde testes até implementação, diretamente na plataforma usando configuração baseada em YAML.
- **Amplo ecossistema de integrações** — Ele suporta milhares de integrações e aplicativos de terceiros, tornando-o altamente flexível para diversos ambientes de desenvolvimento.
- **Grande comunidade de desenvolvedores e suporte a código aberto** — O GitHub é a plataforma preferida para código aberto, hospedando milhões de repositórios públicos e promovendo colaboração em larga escala.
## Minha experiência com o GitLab
Após então ter feito essa pesquisa teórica, sabendo um pouco mais do que me espera, fui criar minha conta e usá-lo de fato, registrando aqui [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Usando o GitLab\|Minha experiência com o GitLab]].
## Conclusão pessoal: Vale a pena?
No geral, percebi que o GitLab é uma plataforma profissional e completa para o gerenciamento de projetos de software, onde seu brilho está no foco em prover ferramentas de DevOps, como controle de versão, deployment, monitoramento, trazendo inúmeras facilidades. Para os sistemas internos que nós fazemos, é perfeito, tudo que fizermos ficará privado e bem interligado. Caso desejemos migrar do GitHub, ele fornece diversas facilidades.
### Casos de uso
Fiz a pesquisa de maneira breve, e sei que ainda há muitas outras funcionalidades a serem exploradas, mas pelo pouco que vi, percebo que tem uns recursos dele que realmente valem a pena serem utilizados e fazem bastante sentido para nosso fluxo de trabalho. No geral, são coisas que nós já fazíamos antes, mas que agora podemos continuar fazendo com mais organização, segurança, e principalmente com mais confiança e conforto, o que nos trás mais prazer de desenvolver.
#### Artifacts para versionamento de linguagens compiladas
Um caso de uso que encontrei foi o uso de [[O que é um artifact?\|Artifacts]] para o desenvolvimento com linguagens compiladas, no nosso caso, para o desenvolvimento mobile e embarcados.
- Com o uso dos , é possível versionar de maneira automática os APK s, vai aparecer uma lista com uma build de cada versão do aplicativo pronta para download, relacionando a versão ao commit. 
- Além do Kotlin, também pode ser utilizado para salvar versões de códigos de Arduino / ESP32, que necessitam de serem compilados, poderíamos facilmente armazenar versões dos códigos já compilados, caso seja necessário um rollback.
#### Registro de Containers buffando o deployment 
Certa vez considerei fazer o deployment por meio do DockerHub, que serviria como um lugar para guardar as imagens do Análise de Processos por exemplo. Mas não gostei da ideia de ter o projeto fragmentado em plataformas: código no GitHub, imagem no DockerHub, e nem de ter que lidar com controle de acesso em mais uma plataforma. 

Quando vi do que se trata o [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Container Registry\|Registro de Containers]] do GitLab, vi que era perfeito. Podemos salvar as imagens customizadas no GitLab de maneira totalmente privada e segura, e depois fazer pull delas no servidor para deployment. Além disso, é possível combar com uma pipeline de CI/CD para realizar o pull e automatizar o deploy. Seria uma alternativa ao AutoUpdate. Assim como os Artifacts, teríamos um registro das imagens de cada versão de nossos softwares.

#### Pipeline de CI/CD
É possível automatizar o repositório para detectar quando é feito um commit na main, e automaticamente realizar o deploy para a produção. Usando as ferramentas que o GitLab provê, essa implementação pode ficar muito tranquila de ser feita, valendo muito a pena.

> [!INFO]
> **Menção Honrosa** aos [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Sinalizadores de Funcionalidade\|Sinalizadores de Funcionalidade]] que são bastante interessantes e podem eventualmente serem úteis, especialmente se puder ser adicionado automaticamente através de IA.

