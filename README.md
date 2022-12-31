# Guia simplificado React-Native
### Instalção passo a passo (Para Windows)

Recomendamos a instalação do Node via Chocolatey , um gerenciador de pacotes popular para Windows.

O React Native também requer o Java SE Development Kit (JDK) , que também pode ser instalado usando o Chocolatey.

Abra um Prompt de Comando do Administrador (clique com o botão direito do mouse em Prompt de Comando e selecione "Executar como Administrador") e execute o seguinte comando:
```
choco install -y nodejs-lts openjdk11
```
1. Instale o Android Studio
Baixe e instale o Android Studio . Enquanto estiver no assistente de instalação do Android Studio, verifique se as caixas ao lado de todos os itens a seguir estão marcadas:
- Android SDK
- Android SDK Platform
- Android Virtual Device
- Se você ainda não estiver usando o Hyper-V: Performance (Intel ® HAXM)<a href="https://android-developers.googleblog.com/2018/07/android-emulator-amd-processor-hyper-v.html">( Veja aqui para AMD ou Hyper-V )</a>

2. Instale o Android SDK
O Android Studio instala o Android SDK mais recente por padrão. Construir um aplicativo React Native com código nativo, no entanto, requer o Android 12 (S)SDK em particular. SDKs Android adicionais podem ser instalados por meio do SDK Manager no Android Studio.

Selecione a guia "Plataformas SDK" no SDK Manager e marque a caixa ao lado de "Mostrar detalhes do pacote" no canto inferior direito. Procure e expanda a Android 12 (S)entrada e verifique se os seguintes itens estão marcados:

Android SDK Platform 31
Intel x86 Atom_64 System ImageouGoogle APIs Intel x86 Atom System Image
Em seguida, selecione a guia "Ferramentas do SDK" e marque a caixa ao lado de "Mostrar detalhes do pacote" aqui também. Procure e expanda a Android SDK Build-Toolsentrada e verifique se ela 31.0.0está selecionada.

Por fim, clique em "Aplicar" para baixar e instalar o Android SDK e as ferramentas de compilação relacionadas.

3. Configure a variável de ambiente ANDROID_HOME
As ferramentas React Native requerem que algumas variáveis ​​de ambiente sejam configuradas para construir aplicativos com código nativo.

Abra o Painel de Controle do Windows.
Clique em Contas de usuário e, em seguida, clique em Contas de usuário novamente
Clique em Alterar minhas variáveis ​​de ambiente
Clique em Novo... para criar uma nova ANDROID_HOMEvariável de usuário que aponte para o caminho para seu Android SDK:

## Criando um novo aplicativo

>Se você instalou anteriormente um pacote global react-native-cli, remova-o, pois pode causar problemas inesperados:

```
npm uninstall -g react-native-cli @react-native-community/cli
```
O React Native possui uma interface de linha de comando integrada, que você pode usar para gerar um novo projeto. Você pode acessá-lo sem instalar nada globalmente usando npx, que acompanha o Node.js. Vamos criar um novo projeto React Native chamado "AwesomeProject":

```
npx react-native init AwesomeProject
```
## Executando seu aplicativo React Native

#### Passo 1: Inicie o Metro
Primeiro, você precisará iniciar o Metro, o empacotador JavaScript que acompanha o React Native. Metro "recebe um arquivo de entrada e várias opções e retorna um único arquivo JavaScript que inclui todo o seu código e suas dependências." - Metro Docs

Para iniciar o Metro, execute npx react-native startdentro da pasta do projeto React Native:

```
npx react-native start
```
#### Etapa 2: inicie seu aplicativo
Deixe o Metro Bundler rodar em seu próprio terminal. Abra um novo terminal dentro da pasta do projeto React Native. Execute o seguinte:

```
npx react-native run-android
```

><a href="https://reactnative.dev/docs/environment-setup">Necessario verificar a documentação caso tenha mudanças</a>


<p style="color: red ">### Core Components ###</p>

- <a href="https://reactnative.dev/docs/components-and-apis">Core components and APIs</a>
- <a href="https://reactnative.dev/docs/activityindicator">ActivityIndicator</a>
- <a href="https://reactnative.dev/docs/button">Button</a>
- <a href="https://reactnative.dev/docs/flatlist">FlatList</a>
- <a href="https://reactnative.dev/docs/image">Image</a>
- <a href="https://reactnative.dev/docs/imagebackground">ImageBackkground</a>
- <a href="https://reactnative.dev/docs/keyboardavoidingview">KeyboardAvoidingView</a>
- <a href="https://reactnative.dev/docs/modal">Modal</a>
- <a href="https://reactnative.dev/docs/pressable">Pressable</a>
- <a href="https://reactnative.dev/docs/refreshcontrol">RefreshControl</a>
- <a href= "https://reactnative.dev/docs/scrollview">ScrollView</a>
- <a href="https://reactnative.dev/docs/sectionlist">SectionList</a>
- <a href="https://reactnative.dev/docs/statusbar">StatusBar</a>
- <a href="https://reactnative.dev/docs/switch">Switch</a>
- <a href="https://reactnative.dev/docs/text">Text</a>
- <a href="https://reactnative.dev/docs/textinput">TextInput</a>
- <a href="https://reactnative.dev/docs/touchablehighlight">TouchableHighight</a>
- <a href="https://reactnative.dev/docs/touchableopacity">TouchableOpacity</a>
- <a href="https://reactnative.dev/docs/touchablewithoutfeedback">TouchableWithoutFeedback</a>
- <a href="https://reactnative.dev/docs/view">View</a>
- <a href="https://reactnative.dev/docs/virtualizedlist">VirtualizedList</a>

[Documentação do core components completa](https://reactnative.dev/docs/text)

### <p style="color:#eb9534">Primeiras dicas de estilização</p> 

No inicio do código se faz a importação do **StyleSheet**

---

```js
import { StyleSheet, Text, View } from 'react-native';
```
>Um padrão comum é fazer com que seu componente aceite um styleprop que, por sua vez, é usado para estilizar subcomponentes. Você pode usar isso para fazer estilos "em cascata" do jeito que eles fazem em CSS.

```js
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

const LotsOfStyles = () => {
    return (
      <View style={styles.container}>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigBlue}>just bigBlue</Text>
        <Text style={[styles.bigBlue, styles.red]}>bigBlue, then red</Text>
        <Text style={[styles.red, styles.bigBlue]}>red, then bigBlue</Text>
      </View>
    );
};

const styles = StyleSheet.create({
  container: {
    marginTop: 50,
  },
  bigBlue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});

export default LotsOfStyles;
```
>O Exemplo  abaixo mostra sóo trexo da criação do estilo que fica em uma váriavel do tipo **const** onde se pode usar o estilo criado em todo o código, utlizando o padrão a seguir:

```js
 <Text style={styles.red}>Aqui está usando a chave red</Text>

 ```
  ##### Obs: Aposta para variavél Styles e depois para sua chave de seu objeto onde esta o estilo desejado, por ex: styles.red ou styles.bigBlue.

```js
const styles = StyleSheet.create({
  container: {
    marginTop: 50,
  },
  bigBlue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});
```
👉[Documentação CSS do React-Native](https://reactnative.dev/docs/style)👈
- <a href="https://reactnative.dev/docs/style">Style</a>
- <a href="https://reactnative.dev/docs/height-and-width">Height and Width(Largura e Altura)</a>
- <a href="https://reactnative.dev/docs/flexbox">Layout with Flebox</a>
- <a href="https://reactnative.dev/docs/images">Images</a>
- <a href="https://reactnative.dev/docs/colors">Color Reference</a>

### Javascript Runtime

- <a href="https://reactnative.dev/docs/javascript-environment#javascript-syntax-transformers">Javascript Environment</a>
- <a href="https://reactnative.dev/docs/timers">Timers</a>
- <a href="https://reactnative.dev/docs/hermes">Using Hermes</a>


### O que são Hooks?

Hooks são um conjunto de novas funcionalidades que dentre outras coisa permitem ao desenvolvedor controlar o state de uma forma mais simples, mais rápida e mais intuitiva.

Sua implementação deu-se a partir da versão 16.7.0-alpha.0 e a promessa é que o desenvolvedor consiga transitar gradativamente do padrão utilizado atualmente para o hooks sem Breaking Changes e sem quebra muito a cabeça, podendo no inicio até utilizar as duas formas.

Os Hooks são classificados em básicos e adicionais da seguinte forma:

### Hooks básicos:

>Para saber detalhes click no Hook que esta lincado com a documentação.

- <a href="https://reactjs.org/docs/hooks-reference.html#usestate">useState</a>
```js 
const [state, setState] = useState(initialState);
```
- <a href="https://reactjs.org/docs/hooks-reference.html#useeffect">useEffect</a>
```js
useEffect(didUpdate);
```
- <a href="https://reactjs.org/docs/hooks-reference.html#usecontext">useContext</a>
```js
const value = useContext(MyContext);
```

### Hooks adicionais:

- <a href="https://reactjs.org/docs/hooks-reference.html#usereducer">useReducer</a>
 

- <a href="https://reactjs.org/docs/hooks-reference.html#usecallback">useCallback</a>
- <a href="https://reactjs.org/docs/hooks-reference.html#usememo">useMemo</a>
- <a href="https://reactjs.org/docs/hooks-reference.html#useref">useRef</a>
- <a href="https://reactjs.org/docs/hooks-reference.html#useimperativehandle">useImperativeHandle</a>
- <a href="">useMutationEffect</a>
- <a href="https://reactjs.org/docs/hooks-reference.html#uselayouteffect">useLayoutEffect</a>
- <a href="https://reactjs.org/docs/hooks-reference.html#usedebugvalue">useDebugValue</a>
- <a href="https://17.reactjs.org/docs/concurrent-mode-reference.html#usedeferredvalue">useDeferredValue</a>
- <a href="https://17.reactjs.org/docs/concurrent-mode-reference.html#usetransition">useTransition</a>
- <a href="https://reactnative.dev/docs/usewindowdimensions">useWindowDimensions</a>