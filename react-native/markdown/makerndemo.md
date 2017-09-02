# let`s make a demo!
---#
## 搭建环境(以Android的为例)

---#
### Node
--#
React Native目前需要NodeJS 5.0或更高版本。
---#
### Yarn、react-native-cli
--#

```
npm install -g yarn react-native-cli
```
---#
### Android环境
--#
Android Studio2.0或更高版本
--#
Android的SDK
--#
![example](./img/example10.jpg)

---#
### 测试安装
--#
打开开发者选项->USB调试。
--#

```
react-native init AwesomeProject
cd AwesomeProject
react-native run-android
```
--#
It`s OK!
---#
### 修改项目
--#

1. 在`index.android.js`上进行修改。
2. 摇晃你的手机，会有一个弹窗，点击reload。
3. 最后就可以看到修改后的效果。

---#
## 来写点什么。。
--#
![example](./img/example11.png)

--#
![example](./img/example12.jpg) <!-- .element: class="imgH" -->
--#

```js
return (
    <View style={styles.box}>
        <Image source={require('./img/06.png')} style={styles.img} />
        <Text style={styles.text}>休闲娱乐</Text>
    </View>
)
```

--#
```js
return (
    <View style={[styles.row, {marginTop: 10}]}>
        <View style={styles.box}>...</View>
        <View style={styles.box}>...</View>
        <View style={styles.box}>...</View>
        <View style={styles.box}>...</View>
        <View style={styles.box}>...</View>
        <View style={styles.box}>...</View>        
    </View>
)
```
--#
```js
return (
    <View style={styles.container}>
        <View style={styles.row}>...</View>
        <View style={styles.row}>...</View>
    </View>
)
```

--#

```js
const styles = StyleSheet.create({
  container: {
    marginLeft: 5,
    marginTop: 10,
    marginRight: 5,
  },
  row: {
    flexDirection: 'row'
  },
  box: {
    width: 70,
  },
  img: {
    alignSelf:'center',width:45,height:45
  },
  text: {
    marginTop: 5,
    textAlign: 'center',
    fontSize: 11,
    color: '#555555'
  }
})
```

--#
最后别忘了，要注册组件。

```js
import React, { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  Text,
  View,
  Image,
} from 'react-native';

export default class LookGithub extends Component {
  render() {
    return (
        //省略。。。
    )
  }
}

AppRegistry.registerComponent('Demo', () => Demo);
```

--#
It`s OK!
---#
## end