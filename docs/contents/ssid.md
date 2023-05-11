# SSID 策略

## 版本要求

0.22.23 版本更新后，支持 SSID 策略，General 中部分开关可以根据设定的策略**临时**切换

## 配置

1. 进入 Settings 界面
2. 滚动至 Experimental Features 栏
3. 点击 SSID Strategy 右边 Edit 按钮打开编辑界面，按照格式添加对应策略：
   ```yaml
   strategy: # object
     SSID: # name of your Wi-Fi
       tun: false
       # mixin: false
       system: false
   ```

### 说明

- tun：是否开启 TUN Mode 开关
- mixin：是否开启 Mixin 开关
- system：是否开启 System Proxy 开关

### 注意

1. 如果不写对应的键，则触发 Wi-Fi 连接时，对应开关不会变更，上面例子中`mixin`不会因 Wi-Fi 切换而改变，保持用户原来选择的状态
2. 如果在当前已经连接了包含在策略中的 Wi-Fi，此时在界面中更改以上三个开关的动作会被记录为用户行为，即策略触发时为**临时状态**
