---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/container-registry/"}
---

# Container Registry
Resumo feito por IA:
## O que é
O Registro de Contêineres (Container Registry) do GitLab é um repositório seguro e privado, totalmente integrado à plataforma GitLab, que permite armazenar e gerenciar imagens de contêineres (como imagens Docker) diretamente em seus projetos. 

Ele funciona como um local centralizado onde os desenvolvedores podem fazer upload (push) e download (pull) das imagens que contêm o código do aplicativo e todas as suas dependências, garantindo que a versão correta da aplicação esteja disponível sempre que necessário. 

## Principais Características e Benefícios
- **Integração Nativa:** Sendo parte integrante da solução DevOps do GitLab, ele compartilha o mesmo sistema de gerenciamento de usuários e permissões, simplificando o controle de acesso e eliminando a necessidade de ferramentas de terceiros.
- **Fluxo de CI/CD Integrado:** É frequentemente usado em conjunto com o GitLab CI/CD para automatizar a criação (build), o envio (push) e a implantação (deployment) de imagens de contêineres, agilizando o processo de desenvolvimento de software.
- **Gerenciamento de Imagens:** Permite visualizar, organizar, filtrar e excluir imagens e tags (versões) diretamente na interface do usuário do GitLab.
- **Segurança:** Oferece um ambiente privado e seguro para suas imagens, com a possibilidade de verificar vulnerabilidades e problemas de conformidade nas imagens.
- **Eficiência e Portabilidade:** Promove a iteração rápida de aplicativos, garantindo a portabilidade e consistência das aplicações em diferentes ambientes de computação. 

## Resumo
Em resumo, o Registro de Contêineres do GitLab é uma peça fundamental para o gerenciamento eficiente e seguro de aplicações conteinerizadas dentro do ecossistema GitLab. Você pode encontrar mais informações na [documentação oficial do GitLab sobre o Registro de Contêineres](https://docs.gitlab.com/user/packages/container_registry/).

## Como integrar com o docker? 
É perfeitamente possível fazer _pull_ das imagens armazenadas no Registro de Contêineres do GitLab usando comandos padrão do Docker. O procedimento envolve autenticação e o uso do endereço completo da imagem no registro.

Aqui está um exemplo de como fazer isso:

```bash
# 1. Faça login no registro do GitLab
$ docker login registry.gitlab.com

Username: meu_username
Password: (cole seu PAT/Token aqui)
Login Succeeded

# 2. Puxe a imagem específica que você precisa
$ docker pull registry.gitlab.com

# 3. Verifique se a imagem foi baixada localmente
$ docker images

REPOSITORY                                                      TAG
registry.gitlab.com         1.0.0
...
```



**Veja: ** [[Estágio/Projetos/12 - Pesquisa GitLab/Pesquisa Gitlab#Registro de Containers buffando o deployment\|Pesquisa Gitlab#Registro de Containers buffando o deployment]]