# meus álbuns

aplicativo simples desenvolvido com react native e expo para mostrar uma lista dos meus álbuns favoritos.

o projeto foi criado como atividade acadêmica para praticar componentes básicos do react native, criação de componentes próprios, props e renderização de listas.

## como testar o projeto

primeiro, clone o repositório ou faça o download dos arquivos.

depois, abra o terminal dentro da pasta do projeto e instale as dependências:

```bash
npm install
```

instale versao web com 
```bash
npx expo install react-dom react-native-web
```

inicie o expo e clique W para abrir o localhost
```bash
npx expo start
```

o `-c` serve para limpar o cache do projeto. se der erro tira o -c

```bash
npx expo start -c
```

## sobre o projeto

o aplicativo apresenta uma lista com alguns dos meus álbuns favoritos.

cada álbum possui as seguintes informações:

- título;
- artista;
- ano de lançamento;
- duração;
- gênero musical;
- capa do álbum.

os dados ficam armazenados dentro do array `albuns`, localizado no arquivo `App.js`.

a `FlatList` percorre esse array e renderiza um componente `AlbumCard` para cada álbum cadastrado.

## tecnologias utilizadas

- react native;
- expo;
- javascript;
- `View`;
- `Text`;
- `Image`;
- `StyleSheet`;
- `FlatList`;
- componentes;
- props.

## organização do projeto

```text
album-list/
├── assets/
│   ├── albums/
│   ├── adaptive-icon.png
│   ├── favicon.png
│   ├── icon.png
│   └── splash-icon.png
├── components/
│   └── AlbumCard.jsx
├── App.js
├── app.json
├── index.js
├── package.json
└── README.md
```

### App.js

o arquivo `App.js` possui:

- o array com os dados dos álbuns;
- o título e os textos da página;
- o link para o spotify;
- a `FlatList`;
- os estilos principais da tela.

### AlbumCard.jsx

o arquivo `components/AlbumCard.jsx` possui o componente responsável por mostrar cada álbum.

ele recebe os dados através de props e apresenta a capa, o título, o artista, o ano, a duração e o gênero musical.

### assets/albums

a pasta `assets/albums` guarda todas as imagens utilizadas como capas dos álbuns.

## como adicionar outro álbum

primeiro, coloque a imagem da capa dentro da pasta:

```text
assets/albums
```

depois, abra o arquivo `App.js` e adicione um novo objeto dentro do array `albuns`:

```js
{
  id: '10',
  titulo: 'nome do álbum',
  artista: 'nome do artista',
  ano: '2026',
  tempo: '40min',
  genero: 'pop',
  capa: require('./assets/albums/nova-capa.jpg'),
},
```

cada álbum precisa possuir um `id` diferente.

o nome e a extensão da imagem precisam ser exatamente iguais aos utilizados no `require`.

por exemplo, se o arquivo for:

```text
nova-capa.png
```

o código deverá utilizar:

```js
capa: require('./assets/albums/nova-capa.png'),
```

## componentes utilizados

### View

utilizado para organizar os elementos e criar os containers da interface.

### Text

utilizado para mostrar textos como título, artista, ano, duração e gênero.

### Image

utilizado para mostrar as capas dos álbuns.

### StyleSheet

utilizado para criar e organizar os estilos do aplicativo.

### FlatList

utilizado para percorrer o array de álbuns e mostrar um card para cada item.

### AlbumCard

componente criado para evitar a repetição do mesmo código para todos os álbuns.

### props

utilizadas para enviar os dados de cada álbum do `App.js` para o componente `AlbumCard`.

## explicação resumida

o `App.js` possui os dados dos álbuns e utiliza uma `FlatList` para percorrer essa lista.

para cada item, a `FlatList` chama o componente `AlbumCard` e envia as informações por props.

o `AlbumCard` recebe essas informações e monta o card que aparece na tela.