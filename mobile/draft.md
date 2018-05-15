## Rap.json/config

> 设置头部切换按钮，用户切换官方和三方插件

```json
  pages": [
    {
      "isDefault": true,
      "capability": "orderList",
      "url": "rap:///page1",
      "config": { // 设置头部切换按钮
        "title": {
          "text": "订单管理",
          "url": "https://air.1688.com/apps/alim/open/commodity-management.html?wh_weex=true&categoryName=trade",
          "subText": "交易",
          "subTextColor": "#999999",
          "subLeftIconImage": "https://gw.alicdn.com/tfs/TB1tj6hawmTBuNjy1XbXXaMrVXa-40-40.png",
          "subRightIconImage": "https://gw.alicdn.com/tfs/TB1Mx_qaAyWBuNjy0FpXXassXXa-30-40.png",
          "subUrl": "https://air.1688.com/apps/alim/open/commodity-management.html?wh_weex=true&categoryName=trade"
        }
      }
    },
    {
      "url": "rap:///page2"
    },
  }
```
![](https://gw.alicdn.com/tfs/TB1Ssy1qKSSBuNjy0FlXXbBpVXa-750-1334.png)

## 入端类型

* 数字
* 卡片
* 插件

![](https://gw.alicdn.com/tfs/TB1c2Beq_tYBeNjy1XdXXXXyVXa-750-1334.png)

* 旺旺顶部
* 旺旺底部
* 旺旺插件
![](https://gw.alicdn.com/tfs/TB1_f8eq_tYBeNjy1XdXXXXyVXa-750-1334.png)