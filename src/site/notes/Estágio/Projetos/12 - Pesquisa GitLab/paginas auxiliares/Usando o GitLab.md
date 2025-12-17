---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/usando-o-git-lab/"}
---


# Usando o GitLab
## Me familiarizando com a ferramenta
### Criando uma conta e iniciando um novo projeto
Entrei no GitLab, fiz login usando a conta do GitHub, e iniciei um novo projeto.

Pediram para que eu criasse um grupo de projetos e um projeto para esse grupo. 

Havia uma opção para importar um projeto do GitHub. O GitLab aparenta ser pensado com o objetivo de ser fácil de migrar do GitHub.

Assim como eu havia pesquisado, diferente do github em que os projetos ficam associados a uma pessoa ou uma empresa, aqui eles ficam associados a um grupo de projetos. O link do meu projeto é esse:

https://gitlab.com/sevenings-group/Sevenings-project

- Grupo: "sevenings-group"
- Projeto: "Sevenings-project"


Quando o projeto foi criado, tive um pequeno susto com a interface menos amigável que a do github e cheia de botões.
![Pasted image 20251208102748.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208102748.png)

#### Extensão de IA do GitLab para IDEs 
Gostei que tem uma extensão para várias IDEs (inclusive o Neovim) para usar o "Github Copillot" deles para ter inline suggestions, e acesso a comandos de commit de maneira integrada. Não experimentei. 
- VS Code: https://docs.gitlab.com/editor_extensions/visual_studio_code/
- Neovim: https://docs.gitlab.com/editor_extensions/neovim/setup/

### Iniciando no GitLab
Olhando melhor, julguei errado a interface, ele me deu um Quick Start bem organizado de como iniciar. Ele aborda:
- Preparar seu código
    1. Adicionar código a esse repositório
    2. Usar a linha de comando
    3. Upload de arquivos
    4. Abrir o WebIDE
- Configurar um projeto
- Planejar, e trabalhar em colaboração
- Proteger o deploy

![Pasted image 20251208104230.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208104230.png)
Vou seguir o tutorial para aprender.
### Upload do meu código
Então, clicando em "Use the command line" ele me aparece essa interface, mostrando que ele é totalmente compatível com o git, e a experiência de uso é igual, só vai mudar o repositório.
![Pasted image 20251208104725.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208104725.png)

#### Problema: Login pelo GitLab
Então, já começou os problemas, ele me pediu para fazer login pelo gitlab e eu entrei pelo github, e não defini senha.
![Pasted image 20251208105124.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208105124.png)

**Solução:** Fui na página do meu perfil no gitlab, achei o campo para trocar a senha, e redefini minha senha, aí deu certo o login.
![Pasted image 20251208105446.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208105446.png)

#### Criando chave SSH
Percebi que toda hora que dou um push ele me pede para fazer login novamente. 

```bash
➜  Sevenings-project git:(main) git push -u origin main
Username for 'https://gitlab.com': Sevenings
Password for 'https://Sevenings@gitlab.com': 
branch 'main' set up to track 'origin/main'.
Everything up-to-date
```

Para contornar isso:
- Usar um token de autenticação e clonar via HTTPS
- Usar chave SSH e clonar via SSH.

Optei arbitrariamente por usar SSH:
1. Cliquei em **Adicionar chave SSH**:
![Pasted image 20251208113205.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208113205.png)
2. Adicionei a chave
![Pasted image 20251208113504.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208113504.png)
3. Dei o clone e funcionou.
```bash
git clone git@gitlab.com:sevenings-group/Sevenings-project.git
```

### Upload de conteudo
Agora com o setup feito, eu fiz o `git push` como normalmente faria para enviar um ao repositório. Fiz upload de um dashboard que mostra dados de sensores que fiz para aprender vuejs. O repositório ficou assim:
![Pasted image 20251208115733.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208115733.png)

---

# Configurando CI/CD
Agora a jiripoca vai piar! Vou ver como configurar CI/CD por ele.
![Pasted image 20251208115820.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208115820.png)

Após passar por extensivos testes de captcha para verificar a conta, me levaram para essa página:
![Pasted image 20251208120503.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208120503.png)
Novamente me assustei com a quantidade de informações. Pipelines? Arquivos yaml? Fazer curso? Respirei fundo.

Nessa aba de templates, me chamou atenção por curiosidade como funcionaria um CI/CD para LaTeX. Aparentemente, lendo o arquivo .yaml, ele builda o documento PDF automaticamente.
![Pasted image 20251208120809.png](/img/user/Est%C3%A1gio/Projetos/12%20-%20Pesquisa%20GitLab/imagens/Pasted%20image%2020251208120809.png)
Perguntei para a IA do google o que ele faz, e ela me confirmou:

>  O template LaTeX do GitLab é um arquivo de configuração `gitlab-ci.yml` pré-configurado que automatiza o processo de **compilação de documentos LaTeX em arquivos PDF** usando o GitLab CI/CD [1, 2]. 
>  Essencialmente, ele:
> - **Define o ambiente:** Especifica uma imagem Docker (`listx/texlive:2020` por padrão) que já contém todas as ferramentas necessárias para trabalhar com LaTeX, como o compilador `latexmk` [1, 2].
> - **Executa a compilação:** Utiliza o comando `latexmk -pdf` para processar seus arquivos fonte (`.tex`) e gerar o documento final em formato PDF [1, 2].
>  - **Salva o resultado:** Define os arquivos PDF resultantes como "artefatos" do pipeline, o que significa que eles ficam disponíveis para download diretamente na interface do GitLab após a conclusão bem-sucedida do job [1, 2]. 
> 
> Isso permite que você mantenha o código-fonte do seu documento (os arquivos `.tex`) no repositório do GitLab e, a cada _push_ ou alteração, o GitLab automaticamente gere a versão PDF atualizada para você.

Fiquei surpreso, não achei que seria tão útil. É um ótimo caso de estudo. Fui pesquisar também [[O que é um artifact?\|O que é um artifact?]] para ter certeza do que se trata, e basicamente ele é um arquivo que é baixável pelo GitLab, um subproduto do código fonte. Ele resolve um problema que tive antigamente com o LaTeX mesmo ao incluir o PDF no GitHub. O Git é feito para lidar com arquivos de Texto. Se tentar versionar arquivos binários que ficam se atualizando sempre, toda hora dá problema de **merge** ao fazer pull. 

Realmente, não só para o Latex, mas para qualquer linguagem compilada (ex: aplicativos mobile, programas em C/C++, talvez até treino de modelos de IA) isso é perfeito. É uma forma de automatizar a _release_ do projeto. Deixa de ser necessário para o usuário ter que:
1. Clonar o repositório localmente
2. Fazer um comando análogo a um `make build`

Achei tão interessante que precisei testar. 
Veja: [[Estágio/Projetos/12 - Pesquisa GitLab/paginas auxiliares/Integrando o Relatório de Estágio com o GitLab\|Integrando o Relatório de Estágio com o GitLab]]

