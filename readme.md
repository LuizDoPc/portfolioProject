# Portfolio project

Leia com atenção antes de contribuir.

## Pré requisitos

### Node.js

[https://nodejs.org/en/](https://nodejs.org/en/)
O node é um Javascript runtime feito encima da engine V8 do Chrome.
Apesar de não trabalhar diretamente com o node o mesmo já possui o NPM incluso. Todavia, ele pode ser de grande ajuda para rodar javascript localmente se necessário.

### NPM

[https://www.npmjs.com/](https://www.npmjs.com/)
O NPM é o gerenciador de pacotes do node.
Além de utilizar pacotes públicos, também temos pacotes privados.
Para isso, entre em contato com seu líder para cadastro no registry local.

### Yarn (recomendado)

[https://yarnpkg.com/pt-BR/](https://yarnpkg.com/pt-BR/)
O yarn é uma opção em relação a utilizar somente o NPM como convêncional. Apesar de rodar encima do NPM ele possui alguns pontos que podem trazer benefícios ao desenvolvedor e o gerenciamento consistente e performático de pacotes.

---

## Idioma

Você deve usar o inglês como o idioma do projeto.
O idioma escolhido deve ser mantido em todo o projeto, ou seja:

- Nome dos arquios;
- Nome de variavel;
- Nome de função/método;
- Comentários;
- Readme;
- Commit;
- Branch;
- Pull-requests;

Você deve manter consistência em todo o projeto.

---

## GIT

Nós usamos o [GIT](https://pt.wikipedia.org/wiki/Git) como sistema de controle de versão e o nosso repositório fica no [Github](https://github.com/LuizDoPc/portfolioProject).
É importante que você saiba o básico do GIT. Para isso, você pode ver a [documentação oficial](https://git-scm.com/doc).

### Programas

Alguns programas para executar o GIT:

- [GIT Oficial](https://git-scm.com/download/)
- [Sourcetree](https://www.sourcetreeapp.com/)
- [Gitkraken](https://www.gitkraken.com/)

### GIT Flow

É utilizado como padrão para a utilização do GIT.
As seguintes _branches_ são utilizadas:

| Nome da _branch_ | Descrição                                  |
| ---------------- | ------------------------------------------ |
| master           | para versões de produção                   |
| develop          | para o desenvolvimento da "próxima versão" |
| feature          | para nova feature                          |
| bugfix           | para conserto de bug                       |
| release          | para nova versão                           |
| hotfix           | para conserto de bug em produção           |
| support          | para conserto de bug em versões antigas    |

Para conhecer melhor sobre o GIT Flow acesse [esse artigo.](https://medium.com/trainingcenter/utilizando-o-fluxo-git-flow-e63d5e0d5e04)

Você pode usar o [git-flow](<[https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html)>), uma especie de extensão do GIT, para te ajudar a configurar e usar esse padrão.

### Commit

Você deve seguir o seguinte padrão de _commit_:

```bash
# <tipo>: (Se aplicado, este commit será...) <assunto> (Max 50 letras)
```

**Tipo pode ser**:

- _feat_ (nova feature)
- _fix_ (bug fix)
- _refactor_ (refatoração de código)
- _style_ (formatação, falta de ponto e vírgula, etc; sem alteração de código)
- _docs_ (mudanças na documentação)
- _test_ (adicionar ou refatorar testes; nenhuma mudança de código de produção)

**Lembre-se de**:

- Comece o assunto com letra maiúscula;
- Use o imperativo na linha de assunto;
- Não termine a linha de assunto com período;

## Tecnologias

### React

O **[React](https://pt.wikipedia.org/wiki/React_%28JavaScript%29)** é uma biblioteca para criação de interfaces de usuário interativas. Ele rederiza e atualiza os componentes certos com eficiência e tem códigos previsíveis e fáceis de depurar.
Um dos pontos mais fortes do react é sua grande comunidade/adoção.

[Como começar](https://reactjs.org/docs/getting-started.html)

### Redux

O [Redux](https://redux.js.org/) é um container de estado previsível para aplicações javascript. Ele tem uma fonte verdadeira única de informação, reduz o caminho entre passagem de informação entre os componentes e é ótimo para gerenciar uma maior volume de dados que mudam constantemente.

[Entenda o Redux](https://medium.com/@hliojnior_34681/entenda-react-e-redux-de-uma-vez-por-todas-c761bc3194ca)

---

## Bibliotecas

### Axios

[https://github.com/axios/axios](https://github.com/axios/axios)
O Axios é uma biblioteca que funciona como um cliente HTTP baseado em promises. Ele pode criar objetos pré definidos para os servidores que serçao consumidos, pode interceptar requests e resopnses assim como o conteúdo dos mesmos e oferece algumas proteções básicas embutidas.

### Bibliotecas de ações assícronas

#### Saga

[https://redux-saga.js.org/docs/introduction/BeginnerTutorial.html](https://redux-saga.js.org/docs/introduction/BeginnerTutorial.html)

---

## Codificação

### ESlint

[ESLint](https://eslint.org/) é uma ferramenta de [lint](https://en.wikipedia.org/wiki/Lint_%28software%29) plugável para JavaScript e [JSX](https://en.wikipedia.org/wiki/React_%28web_framework%29#JSX).

Ao usar o `create-react-app`( mais detalhes a frente), você terá o eslint instalado em seu projeto, bastando apenas a configuração.
Para isso, crie o arquivo `eslintrc.js` ( se não existir) na raiz do projeto e adicione o seguinte conteúdo:

```javascript
module.exports = {
  extends: ['airbnb'],
  plugins: ['react', 'prettier'],
  parser: 'babel-eslint',
  rules: {
    'comma-dangle': 'off',
    'react/jsx-filename-extension': [1, { extensions: ['.js', '.jsx'] }],
    'import/prefer-default-export': 'off',
    'react/jsx-one-expression-per-line': 'off'
  },
  settings: {
    'import/resolver': {
      'babel-module': {}
    }
  }
};
```

Usamos o ESlint junto com o Prettier e para o perfeito funcionamento deles você precisa instalar dois _packages_:

**Usando yarn**

     yarn add  eslint-config-prettier eslint-plugin-prettier

**Usando npm**

     npm install eslint-config-prettier eslint-plugin-prettier

O nosso ESlint está configurado para seguir o padrão [Airbnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb).

### Ordenação de imports

Ao início do arquivo, quando existir a importação dos pacotes, bibliotecas e estilos, deve-se seguir a seguinte ordem:

- packages
- libs
- constants
- components
- components from the same folder
- style (se aplicar)
- style from the same folder (se aplicar)

A ordem nesse caso cria uma uniformidade e organização que pode ser vista entre os projetos de maneira simples.
Não é necessário adicionar comentários as seções de importações;

---

## Extensões

### Recomendação: Prettier

[https://prettier.io/](https://prettier.io/)
O prettier é um formatador do código, ele segue os padrões definidos pelo eslint e o ídeal, é que ao salvar o arquivo de desenvolvimento ele rode automáticamente, formatando qualquer bloco de código que possa ter passado despercebido pelo desenvolvedor, assim como realizar este trabalho automaticamente para o mesmo.

### Recomendação: React snippets

[es7-react-js-snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
Atalhos no editor de texto para criação de componentes e outras estruturas clássicas utilizadas pelo react.

---

## Práticas recomendadas

### Funções assíncronas: async e await

[https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/funcoes_assincronas](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/funcoes_assincronas)
(WIP)

### React Hooks

[https://pt-br.reactjs.org/docs/hooks-reference.html](https://pt-br.reactjs.org/docs/hooks-reference.html)
(WIP)

### Redux Hooks

[https://react-redux.js.org/next/api/hooks#hooks](https://react-redux.js.org/next/api/hooks#hooks)
(WIP)

---
