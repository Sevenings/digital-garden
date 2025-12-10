---
{"dg-publish":true,"permalink":"/estagio/projetos/12-pesquisa-git-lab/paginas-auxiliares/sinalizadores-de-funcionalidade/"}
---


# Sinalizadores de Funcionalidade
## O que são?
Os **sinalizadores de funcionalidade** (ou _feature flags_, _feature toggles_, ou _feature switches_) são uma técnica essencial no desenvolvimento de software moderno que permite **ligar ou desligar funcionalidades da aplicação dinamicamente, sem a necessidade de implantar (fazer _deploy_) um novo código**. 

Eles funcionam essencialmente como "interruptores" de controle remoto para partes específicas do seu código. 

## Como Funcionam?
No nível mais básico, um sinalizador de funcionalidade é uma variável booleana (`true` ou `false`) em seu código que determina se um bloco de código específico deve ser executado ou ignorado. 

Imagine que você está desenvolvendo uma nova seção de "Perfil do Usuário 2.0". Em vez de criar um _branch_ de código separado e fundi-lo (merge) apenas quando estiver 100% pronto, você envolve o novo código em um sinalizador:

```
SE sinalizador_perfil_2_0 ESTÁ ATIVO ENTÃO
  MOSTRAR_NOVO_PERFIL()
SENÃO
  MOSTRAR_PERFIL_ANTIGO()
FIM SE
```

Você pode, então, alterar o valor desse sinalizador em tempo real por meio de um painel de controle (como o do GitLab), e o comportamento da aplicação muda imediatamente. 

## Principais Benefícios e Casos de Uso

A separação do _deployment_ (entrega técnica do código para produção) do _release_ (lançamento da funcionalidade para os usuários) oferece várias vantagens: 

- **Redução de Riscos:** Se uma nova funcionalidade causa um problema inesperado em produção, você pode desativá-la instantaneamente com um clique, em vez de realizar um _rollback_ completo do código, que é demorado e disruptivo.
- **Lançamentos Graduais (Rollouts):** Você pode lançar uma funcionalidade para um pequeno subconjunto de usuários (ex: apenas 5% dos usuários, ou apenas usuários internos da empresa) para testar em ambiente real antes de disponibilizar para todos.
- **Testes A/B:** Permite mostrar diferentes versões de uma funcionalidade para diferentes grupos de usuários para determinar qual funciona melhor (otimização e _product discovery_).
- **CI/CD Contínuo:** As equipes podem integrar seu código na linha principal (_main branch_) com mais frequência (integração contínua), pois funcionalidades incompletas ficam "ocultas" por trás de um sinalizador desativado.
- **Desenvolvimento Paralelo:** Múltiplas equipes podem trabalhar em funcionalidades dependentes sem pisar nos pés umas das outras. 

## Sinalizadores de Funcionalidade no GitLab

O GitLab oferece suporte nativo a _feature flags_ (integrando-se com a ferramenta _open source_ Unleash) na seção **Deployments > Feature Flags** do seu projeto. 

Lá, você pode gerenciar facilmente quais sinalizadores estão ativos para quais ambientes (desenvolvimento, staging, produção) e definir estratégias de lançamento específicas (como "para todos os usuários", "para uma porcentagem específica" ou "para usuários com IDs específicos").