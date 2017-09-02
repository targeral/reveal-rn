# how react native
---# 
## 理解React

--#

| | React | Vue |
|:--:|:--|:--|
| 数据模型 | props, state | prop, data |
| 语法 | JSX | Vue的语法 |
| 复合组件 | 都可以通过不同的(一般为可重用)组件组合生成新的组件 |

--#

```javascript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

--#

```javascript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

--#

```javascript
class HelloMessage extends React.Component {
  constructor(props) {
    super(props);
    this.state = {};
  }
  render() {
    return <div>Hello {this.props.name}</div>;
  }
}

ReactDOM.render(
  <HelloMessage name="John" />,
  document.getElementById('container')
);
```
--#
*React-Native*

```javascript
class HelloMessage extends React.Component {
    render() {
        return (
            <Text>{ this.props.name }</Text>
        )
    }
}
ReactDOM.render(<HelloMessage name="Jane" />, mountNode);
```
--#
那么`<Text>`是什么呢？

---#
## React Native的原生组件
--#

* `<View>`
* `<Text>`
* `<TextInput>`
* `<ListView>`
* `<DatePickerIOS>`
* `<ToolbarAndroid>`
* .....
---#
### Text
--#

```js
import React from 'react';
import { AppRegistry, Text } from 'react-native';
 
const App = () => {
  return (
    <Text>Hello World!</Text>
  );
}
 
// App registration and rendering
AppRegistry.registerComponent('MyApp', () => App);
```
---#
### Image
--#
下面一个现实checkbox图片的简单实例
--#

```js
import React from 'react';
import { AppRegistry, Image } from 'react-native';
 
const App = () => {
  return (
    <Image source={require('./img/check.png')} />
  );
}
 
// App registration and rendering
AppRegistry.registerComponent('MyApp', () => App);
```
---#
### View
--#
```js
import React from 'react';
import { AppRegistry, Text, View } from 'react-native';
 
const App = () => {
  return (
    <View style={{alignItems: 'center'}}>
      <Text>Hello!</Text>
    </View>
  );
}
 
// App registration and rendering
AppRegistry.registerComponent('MyApp', () => App);
```
---#
```js
AppRegistry.registerComponent('MyApp', () => someComponent);
```
--#
Dom is ready！
---#
## StyleSheet对象
--#
```javascript
const styles = StyleSheet.create({
  bigblue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});
```
--#
```javascript
import React, { Component } from 'react';
import { AppRegistry, StyleSheet, Text, View } from 'react-native';

class LotsOfStyles extends Component {
  render() {
    return (
      <View>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigblue}>just bigblue</Text>
        <Text style={[styles.bigblue, styles.red]}>bigblue, then red</Text>
        <Text style={[styles.red, styles.bigblue]}>red, then bigblue</Text>
      </View>
    );
  }
}

AppRegistry.registerComponent('LotsOfStyles', () => LotsOfStyles);
``` 
---#
## flexbox
--#
CSS中的flexbox。
--#
RN Flexbox ≈ CSS Flexbox
--#
* `flexDirection`
* `alignItems`
* `justifyContent`
--#
```javascript
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

class FlexDirectionBasics extends Component {
  render() {
    return (
      <View style={{flex: 1, flexDirection: 'row'}}>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
};

AppRegistry.registerComponent('AwesomeProject', () => FlexDirectionBasics);
```
---#
## React Native的高度和宽度
--#
```javascript
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

class FixedDimensionsBasics extends Component {
  render() {
    return (
      <View>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 100, height: 100, backgroundColor: 'skyblue'}} />
        <View style={{width: 150, height: 150, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
};
AppRegistry.registerComponent('AwesomeProject', () => FixedDimensionsBasics);
```

---#
## React Native API
--#

* Clipboard
* CameraRoll(本地相册)
* PixelRatio(访问设备的像素密度)
* ....