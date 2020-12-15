# GB-canvas-turntable

>

---

## 简介

基于 Canvas 绘制、可配置奖项的转盘抽奖

## 演示 & 文档

https://blog.givebest.cn/GB-canvas-turntable.html

## 使用

### Browser

```html
<link rel="stylesheet" href="css/GB-canvas-turntable.css" />
<script src="js/GB-canvas-turntable.js"></script>
```

### 普通

```js
gbTurntable.init({
  id: "turntable",
  config: function (callback) {
    // 获取奖品信息
    // 奖项 text 属性不能为空，用于显示或抽中奖品提示
    // img 为奖品图片地址，如果不为空则转盘奖品按图片方式显示
    callback &&
      callback([
        {
          text: "1元红包",
          img: "images/redpacket.png",
        },
        {
          text: "2元红包",
        },
        {
          text: "3元红包",
        },
        {
          text: "显示器",
          img: "images/display.png",
        },
        {
          text: "5元红宝",
        },
        {
          text: "6元红宝",
        },
      ]);
  },
  getPrize: function (callback) {
    // 获取中奖信息
    var num = (Math.random() * 6) >>> 0, //奖品ID
      chances = num; // 可抽奖次数
    callback && callback([num, chances]);
  },
  gotBack: function (data) {
    alert("恭喜抽中" + data);
  },
});
```

## 支持我

![微信扫码支付](./images/QR/wechat.jpg)
![支付宝扫码支付](./images/QR/alipay.jpg)

## 感谢他们

演示网页排版来自： [https://github.com/sofish/typo.css](https://github.com/sofish/typo.css)

## License

[MIT & Anti 996](./LICENSE) © 2019 [givebest](https://github.com/givebest)
