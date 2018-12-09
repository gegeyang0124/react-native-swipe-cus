# react-native-swipe-cus
自定义滑动切换组件

###  安装组件：
npm i --save react-native-swipe-cus

### 展示ui图
![滑动展示图](./showImg/show.gif)

### 使用
```javascript
import React, { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  Text,
  View
} from 'react-native';

import Swiper from 'react-native-swipe-cus';

const styles = StyleSheet.create({
  wrapper: {
  },
  slide1: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#9DD6EB',
  },
  slide2: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#97CAE5',
  },
  slide3: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#92BBD9',
  },
  text: {
    color: '#fff',
    fontSize: 30,
    fontWeight: 'bold',
  }
})

export default class Test extends Component {
  render(){
    return (
      <Swiper style={styles.wrapper} showsButtons={true}>
        <View style={styles.slide1}>
          <Text style={styles.text}>Hello Swiper</Text>
        </View>
        <View style={styles.slide2}>
          <Text style={styles.text}>Beautiful</Text>
        </View>
        <View style={styles.slide3}>
          <Text style={styles.text}>And simple</Text>
        </View>
      </Swiper>
    );
  }
}
```

### 属性

#### 基本属性

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| horizontal | true | `bool` | If `true`, the scroll view's children are arranged horizontally in a row instead of vertically in a column. |
| loop | true | `bool` | Set to `false` to disable continuous loop mode. |
| index | 0 | `number` | Index number of initial slide. |
| showsButtons | false | `bool` | Set to `true` make control buttons visible. |
| autoplay | false | `bool` | Set to `true` enable auto play mode. |
| onIndexChanged | (index) => null | `func` | Called with the new index when the user swiped |

#### 自定义样式和内容

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| width | - | `number` | If no specify default enable fullscreen mode by `flex: 1`. |
| height | - | `number` | If no specify default fullscreen mode by `flex: 1`. |
| style | {...} | `style` | See default style in source. |
| containerStyle | {...} | `style` | See default container style in source. |
| loadMinimal | false | `bool` | Only load current index slide , `loadMinimalSize` slides before and after. |
| loadMinimalSize | 1 | `number` | see `loadMinimal`   |
| loadMinimalLoader | `<ActivityIndicator />` | `element` | Custom loader to display when slides aren't loaded

#### 标记页码

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| showsPagination | true | `bool` | Set to `true` make pagination visible. |
| paginationStyle | {...} | `style` | Custom styles will merge with the default styles. |
| renderPagination | - | `function` | Complete control how to render pagination with three params (`index`, `total`, `context`) ref to `this.state.index` / `this.state.total` / `this`, For example: show numbers instead of dots. |
| dot | `<View style={{backgroundColor:'rgba(0,0,0,.2)', width: 8, height: 8,borderRadius: 4, marginLeft: 3, marginRight: 3, marginTop: 3, marginBottom: 3,}} />` | `element` | Allow custom the dot element. |
| activeDot | `<View style={{backgroundColor: '#007aff', width: 8, height: 8, borderRadius: 4, marginLeft: 3, marginRight: 3, marginTop: 3, marginBottom: 3,}} />` | `element` | Allow custom the active-dot element. |
| dotStyle | - | `object` | Allow custom the active-dot element. |
| dotColor | - | `string` | Allow custom the active-dot element. |
| activeDotColor | - | `string` | Allow custom the active-dot element. |
| activeDotStyle | - | `object` | Allow custom the active-dot element. |

#### 自动滚动

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| autoplay | true | `bool` | Set to `true` enable auto play mode. |
| autoplayTimeout | 2.5 | `number` | Delay between auto play transitions (in second). |
| autoplayDirection | true | `bool` | Cycle direction control. |

#### 控制按钮

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| showsButtons | true | `bool` | Set to `true` make control buttons visible. |
| buttonWrapperStyle | `{backgroundColor: 'transparent', flexDirection: 'row', position: 'absolute', top: 0, left: 0, flex: 1, paddingHorizontal: 10, paddingVertical: 10, justifyContent: 'space-between', alignItems: 'center'}` | `style` | Custom styles. |
| nextButton | `<Text style={styles.buttonText}>›</Text>` | `element` | Allow custom the next button. |
| prevButton | `<Text style={styles.buttonText}>‹</Text>` | `element` | Allow custom the prev button. |

#### 子内容属性

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| style | {...} | `style` | Custom styles will merge with the default styles. |
| title | {<Text numberOfLines={1}>...</Text>} | `element` | If this parameter is not specified, will not render the title. |

#### 关于使用`<ScrollView />`的一些属性

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| horizontal | true | `bool` | If `true`, the scroll view's children are arranged horizontally in a row instead of vertically in a column. |
| pagingEnabled | true | `bool` | If true, the scroll view stops on multiples of the scroll view's size when scrolling. This can be used for horizontal pagination.  |
| showsHorizontalScrollIndicator | false | `bool` | Set to `true` if you want to show horizontal scroll bar. |
| showsVerticalScrollIndicator | false | `bool` |  Set to `true` if you want to show vertical scroll bar. |
| bounces | false | `bool` | If `true`, the scroll view bounces when it reaches the end of the content if the content is larger then the scroll view along the axis of the scroll direction. If `false`, it disables all bouncing even if the alwaysBounce* props are true.  |
| scrollsToTop | false | `bool` | If true, the scroll view scrolls to top when the status bar is tapped.  |
| removeClippedSubviews | true | `bool` | If true, offscreen child views (whose overflow value is hidden) are removed from their native backing superview when offscreen. This canimprove scrolling performance on long lists.  |
| automaticallyAdjustContentInsets | false | `bool` | Set to `true` if you need adjust content insets automation. |
| scrollEnabled | true | `bool` | Enables/Disables swiping |

> @see: http://facebook.github.io/react-native/docs/scrollview.html

#### 滚动响应事件

| 属性  | 默认值  | 类型 | 描述 |
| :------------ |:---------------:| :---------------:| :-----|
| onScrollBeginDrag | `e` / `state` / `context` | `function` | When animation begins after letting up |
| onMomentumScrollEnd | `e` / `state` / `context` | `function` | Makes no sense why this occurs first during bounce |
| onTouchStartCapture | `e` / `state` / `context` | `function` | Immediately after `onMomentumScrollEnd` |
| onTouchStart | `e` / `state` / `context` | `function` | Same, but bubble phase |
| onTouchEnd | `e` / `state` / `context` | `function` | You could hold the touch start for a long time |
| onResponderRelease | `e` / `state` / `context` | `function` | When lifting up - you could pause forever before * lifting |

> Note: each ScrollResponder be injected with two params: `state` and `context`, you can get `state` and `context`(ref to swiper's `this`) from params, for example:

```javascript
var swiper = React.createClass({
  _onMomentumScrollEnd: function (e, state, context) {
    console.log(state, context.state)
  },
  render: function() {
    return (
      <Swiper style={styles.wrapper}
      onMomentumScrollEnd ={this._onMomentumScrollEnd}
     ...
      </Swiper>
    )
  }
})
```

> More ScrollResponder info, see: https://github.com/facebook/react-native/blob/master/Libraries/Components/ScrollResponder.js

### 方法

#### scrollBy(index, animated)

Scroll by relative index.

参数:

| 属性  | 默认值  | 类型 | 描述 |
| :---- | :------: | :------: | :--- |
| index | `number`   | `undefined` | offset index |
| animated | `bool`   | `true` | offset index |

### [我的博客](http://blog.sina.com.cn/s/articlelist_6078695441_0_1.html)
