# Guia simplificado React-Native

### Core Components
<p style="color: red">Todos compenentes a serem estudado por lista</p>

- <a href="https://reactnative.dev/docs/components-and-apis target=_blank">Core components and APIs</a>
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

### Primeiras dicas de estilização 

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
- CSS inline
  - css
- CSS 
- CSS

