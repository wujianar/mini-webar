# 小程序WebAR 快速入门

技术支持：无间AR

官网: [https://www.wujianar.com](https://www.wujianar.com)


# 小程序WebAR开发说明

## 1. wxml文件中增加 camera 与 canvas

```xml
<camera frame-size="medium" bindinitdone="cameraInitDone" mode="normal" device-position="back" resolution="medium" flash="off" />

<canvas type="2d" id="canvas" style="width:1px; height: 1px;" />

```
            
## 2. js文件中导入WebAr SDK

```javascript
import { WebAr } from "../../utils/WebAr";
```

## 3. 设置认证token等

```javascript
const CONFIG = {
    token: 'YTU5NjgxYz5********', // 认证token, 请从开发者中心获取
    endpoint: 'https://iss-cn1.wujianar.com',
    quantity: 0.7, // 图片压缩质量, 0~1
    interval: 1000, // 识别间隔(毫秒)
}
```

## 4. 在 camera 初始化完成事件中设置WebAr

```javascript
this.webAr = new WebAr(CONFIG, res[0].node);

this.webAr.searchCallback(res => {
    // TODO: 识别成功后的回调
});
```

## 5. 开启与关闭识别

```javascript
this.webAr.startSearch();

this.webAr.stopSearch();
```

*请扫描居民身份证有国徽的那一面来体验*


## 6. 示例下载

[示例下载: https://github.com/wujianar/mini-webar](https://github.com/wujianar/mini-webar)