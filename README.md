# rn-wheel-picker-china-region

IOS & 安卓都兼容的中国地区选择器.

a modal picker(wheel) of china province & city & region.

## propTypes

```
isVisible: PropTypes.bool,
isShowArea: PropTypes.bool,
provincesToIgnore: PropTypes.shape({
    provinceName: PropTypes.bool,
}),
selectedProvince: PropTypes.string,
selectedCity: PropTypes.string,
selectedArea: PropTypes.string,
navBtnColor: PropTypes.string,
animationType: PropTypes.string,
transparent: PropTypes.bool,
onSubmit: PropTypes.func,
onCancel: PropTypes.func,
androidPickerHeight: PropTypes.number   // 安卓手机下可以由该属性来设置picker区域的高度,
navStyle: ViewStyle,
leftNavBtnStyle: ViewStyle,
rightNavBtnStyle: ViewStyle,
leftNavTextStyle: TextStyle,
rightNavTextStyle: TextStyle,
```

## Install

npm install rn-wheel-picker-china-region --save

## Usage

```javascript
import ChinaRegionWheelPicker from 'rn-wheel-picker-china-region';

// ios用法一
<ChinaRegionWheelPicker
  onSubmit={(params) => this.setState({ region1: `${params.province},${params.city},${params.area}` })}
  onCancel={() => console.log('cancel')}
>
  <TextInput
    editable={false}
    placeholder="点击去选择地区"
    value={this.state.region1}
  />
</ChinaRegionWheelPicker>

// android用法一
<ChinaRegionWheelPicker
  onSubmit={(params) => this.setState({ region1: `${params.province},${params.city},${params.area}` })}
  onCancel={() => console.log('cancel')}
>
  <Text
    style={{ backgroundColor: '#FFF', width: 200, paddingVertical: 20, textAlign: 'center', color: 'black' }}
  >{this.state.region1 || '点击去选择地区'}</Text>
</ChinaRegionWheelPicker>

// 用法二(参考Example目录index.ios.js/android.ios.js)
<ChinaRegionWheelPicker
  isVisible={this.state.isPickerVisible}
  navBtnColor={'red'}
  selectedProvince={'广东'}
  selectedCity={'深圳'}
  selectedArea={'福田区'}
  transparent
  animationType={'fade'}
  onSubmit={this._onPressSubmit.bind(this)} // 点击确认_onPressSubmit
  onCancel={this._onPressCancel.bind(this)} // 点击取消_onPressCancel
  androidPickerHeight={100}   // 安卓手机下可以设置picker区域的高度
/>

<TouchableOpacity
  onPress={this._onPress2Show.bind(this)}
>
  <Text style={{ color: 'white' }}>{this.state.region2 || '点击去选择地区' }</Text>
</TouchableOpacity>

```

## Show

![rn-wheel-picker-china-region1](./screens/regionpicker1.png)

![rn-wheel-picker-china-region2](./screens/regionpicker2.png)

![rn-wheel-picker-china-region3](./screens/picker3.png)

![rn-wheel-picker-china-region4](./screens/picker4.png)
