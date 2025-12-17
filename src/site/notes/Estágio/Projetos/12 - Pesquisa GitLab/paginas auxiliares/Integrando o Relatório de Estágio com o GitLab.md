---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/integrando-o-relatorio-de-estagio-com-o-git-lab/"}
---


# Integrando o Relatório de Estágio com o GitLab
Após ver o grande caso de uso da Pipeline de CI/CD para o LaTeX, não me contive em experimentar.

## Fazendo upload do projeto
Primeiramente, criei um projeto em branco chamado "relatorio-de-estagio":
![Pasted image 20251209111439.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209111439.png)

Usei um bloco de comandos bem conveniente que eles têm apenas para fazer o upload de uma pasta.
![Pasted image 20251209112125.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209112125.png)

E o repositório foi upado com sucesso:
![Pasted image 20251209112354.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209112354.png)
## Configurando o CI/CD do LaTeX
Então, cliquei na aba **"Getting Started > Configure a project > Setup your first CI/CD > LaTeX (Use Template)"**

Apareceu o editor de pipeline e eu apenas dei **Enter** em **Commit changes** para criar o arquivo .yaml kkk

Apareceu uma confirmação
![Pasted image 20251209112812.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209112812.png)

E clicando mais é possível ver o status dentro da máquina virtual
![Pasted image 20251209112914.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209112914.png)

E depois deu esse erro:
![Pasted image 20251209113527.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209113527.png)

### Debugando

Para entender melhor o que aconteceu, vamos analisar o conteúdo do arquivo .yaml:

```yaml
# This file is a template, and might need editing before it works on your project.
# To contribute improvements to CI/CD templates, please follow the Development guide at:
# https://docs.gitlab.com/development/cicd/templates/
# This specific template is located at:
# https://gitlab.com/gitlab-org/gitlab/-/blob/master/lib/gitlab/ci/templates/LaTeX.gitlab-ci.yml

---
variables:
# Feel free to choose the image that suits you best.
# blang/latex:latest ... Former image used in this template. No longer maintained by author.
# listx/texlive:2020 ... The default, referring to TexLive 2020. Current at least to 2021-02-02.
# Additional alternatives with high Docker pull counts:
# thomasweise/docker-texlive-full
# thomasweise/texlive
    LATEX_IMAGE: listx/texlive:2020
  
build:
    image: $LATEX_IMAGE
    script:
        - latexmk -pdf
      
    artifacts:
        paths:
            - "*.pdf"
```

Esse é bem simples. Ele tem uma sessão de variáveis (para colocar as variáveis) e uma de build (para descrever o processo de build). Na sessão de **build**, tem o parâmetro **image** que descreve literalmente uma imagem do docker. Essa `listx/textlive:2020` pode ser encontrada facilmente no [DockerHub](https://hub.docker.com/r/listx/texlive). 

Na seção de build, há o **script** que corresponde ao comando que é executado para **compilar** o documento. 

Por fim, ele tem a seção **artifacts** que está indicando que todos os arquivos terminados em **.pdf** devem ser expostos como um [[O que é um artifact?\|artefato]].

Agora, veja que era apenas um template, e como sempre, ele não funcionou exatamente para meu caso de uso. Felizmente já havia me acontecido antes, e acontece que o compilador que ele usou, não é compatível com a fonte que eu usei no documento, sendo necessário trocar. 

Fiz então a correção:
```yaml
script:
    - latexmk -lualatex
```

Deu problema de ausência da fonte, então também troquei a imagem por uma mais completa:
```yaml
variables:
    LATEX_IMAGE: texlive/texlive:latest
```

Após esses debugs a pipeline funcionou

## Resultado
Então, por fim, o resultado final foi que, automaticamente, quando fiz alguma alteração no projeto e dei push, o gitlab automaticamente executou a pipeline de build, que pode ser visto na tela inicial do projeto.
![Pasted image 20251209124220.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209124220.png)

Por fim, após buildado, podemos encontrar e baixar o documento na aba de Artifacts
![Pasted image 20251209124516.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209124516.png)
![Pasted image 20251209124649.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209124649.png)
De fato, o nome foi alterado para Heitor Vinícius de Lima Oliveira:
![Pasted image 20251209124721.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251209124721.png)
