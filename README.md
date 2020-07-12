[![issues](https://img.shields.io/github/issues/luizcsbh/pokemon-vue)](https://github.com/luizcsbh/pokemon-vue/issues)
![forks](https://img.shields.io/github/forks/luizcsbh/pokemon-vue)
![stars](https://img.shields.io/github/stars/luizcsbh/pokemon-vue)
[![lincença](https://img.shields.io/github/license/luizcsbh/pokemon-vue)](https://github.com/luizcsbh/pokemon-vue/blob/master/LICENSE)
![code-size](https://img.shields.io/github/languages/code-size/luizcsbh/pokemon-vue)
[![commit activity](https://img.shields.io/github/commit-activity/m/luizcsbh/pokemon-vue)](https://github.com/luizcsbh/pokemon-vue/commits)
[![last commit](https://img.shields.io/github/last-commit/luizcsbh/pokemon-vue)](https://github.com/luizcsbh/pokemon-vue/commits)
[![CodeFactor](https://www.codefactor.io/repository/github/luizcsbh/pokemon-vue/badge)](https://www.codefactor.io/repository/github/luizcsbh/pokemon-vue)
[![version](https://img.shields.io/github/package-json/v/luizcsbh/pokemon-vue)](https://github.com/luizcsbh/pokemon-vue/blob/master/package.json)
[![Netlify Status](https://api.netlify.com/api/v1/badges/385c1e14-b004-4927-ae22-aea2bbc2acea/deploy-status)](https://app.netlify.com/sites/pokemon-vue/deploys)
[![twwiter follow](https://img.shields.io/twitter/follow/luizcs?style=social)](https://twitter.com/luizcs)


# Pokemon-vue 
Um projeto feito com Vue.js consumindo api do Pokemon

Para acessar a aplicação inserir um usuário qualquer e a senha para login: mestrepokemon


## Porque o framework Vue.js?
Comunidade ativa com muito apoio interno, escalabilidade porque no Vue.js há possibilidade de começar com poucos componentes sem utilizar ferramentas adicionais.

## Quais os três principais benefícios em relação ao React?


| Framework   |      React      |Vue |
|:----------|:-------------:|:------:|
|Linguagem padrão |  Focada no ES6 | ES6 ou ES5  |
| Criação de Interfaces |    Arquivos de estilo separados por componentes JSX   |   Usa os chamados Single-File Components, que agregam o JS puro, HTML e os estilos no mesmo lugar |
| Liberdade de Criação | Completamente liberal, sem um caminho específico e com diversas possibilidades de implementação |    Balanceada, uma vez que há equilíbrio entre o que o desenvolvedor precisa fazer e o que framework já faz pelo desenvolvedor |
|Arquitetura|MVW|MVVM|
|Tamanho da biblioteca|43kb|23kb|
|Ambiente de testes|Jest|Karma|
|Produção Nativa de Apps|React Native|Weex|
|Renderização Serve-side|Next.js|Nuxt.js|
    

## Quais possíveis problemas poderemos enfrentar na utilização desse framework?
#### Acessando Instância Raiz
Em cada subcomponente de uma instância new Vue, a instância raiz pode ser acessada com a propriedade $root.
Isso pode ser conveniente para demonstrações ou aplicações muito pequenas, com apenas um punhado de componentes. Porém, o padrão não se adapta bem a aplicações de média ou larga escala, de modo que nós recomendamos fortemente a utilização do Vuex para gerenciar o estado, na maioria dos casos.
#### Acessando Instância do Componente Pai
Semelhantemente a $root, a propriedade $parent pode ser utilizada para acessar a instância pai, a partir de um componente filho. Isso é uma alternativa, preguiçosa e tentadora, ao invés de passar os dados via propriedades.

Na maioria dos casos, alcançar o interior dos componentes pais torna sua aplicação muito difícil de depurar e entender, especiamente se você modifica dados no componente pai. Ao olhar para o componente posteriormente, será muito difícil de compreender onde aquela mutação de dados se originou.
$refs são populados somente depois que o componente foi renderizado, e não são reativos. É somente uma escotilha para manipulação direta dos filhos - evite usar $refs de dentro de templates ou de dados computados.

#### Acessando Instâncias de Componentes e Elementos Filhos
Apesar da existência de propriedades e eventos, algumas vezes você ainda pode precisar acessar diretamente um componente filho em JavaScript. Para isso, você pode atribuir um identificador de referência ao componente filho, usando o atributo ref

### Instalação do projeto
```
npm install
```

### Ambiente de Desenvolvimento
```
npm run serve
```

### Ambiente de Produção
```
npm run build
```

### Ambiente de testes
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

## Integrante

Luiz Carlos dos Santos

[Link do projeto](https://pokemon-vue.netlify.app/)