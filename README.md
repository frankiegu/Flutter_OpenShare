# Flutter_OpenShare Plugin
Flutter_OpenShare是一款集成OpenShareSDK自动获取邀请码或参数的flutter 插件,可以帮助开发者快速集成

###   产品服务
####  1. 智能传参
```
    智能传递参数，绑定用户关系，高效提升用户转换率
```
####  2. 快速安装和一键唤醒
```
    在各社交平台app中快速下载安装和直接一键唤醒,兼容各移动端浏览器
```
####  3. 渠道统计
```
    追踪用户来源，统计推广效果
```
### 应用场景

1. 免填邀请码，智能绑定用户关系

2. 一键拉起，智能唤醒

3. 快速下载，在社交平台中快速下载

4. 免渠道打包,不用再为推广而渠道打包，快速区分与统计渠道来源

### 推广渠道
    1.邀请码
    2.软文推广
    3.广告营销
    4.商品分销
注:可以自定义推广渠道，上面几个只是简单举例

### 测试Demo

### 
```
扫描二维码下载测试apk (测试demo暂时只有apk，iOS未上架)
```
<img src="https://github.com/An-uking/Flutter_OpenShare/blob/master/images/20191024161016.jpg?raw=true" width="200" height="200">

## APP集成

注：由于google帐号忘记了，所以不能提交到pub上面

### 如何集成到我的flutter项目中？

在项目根目录下建一个plugin目录 下载此库到该目录中去

在包管理文件pubspec.yaml中添加如下：

```
dev_dependencies:
  umengshare:
    path: ./plugin/flutter_openshare 
```

```
提供7天免费接入测试

提供原生SDK接入服务

提供SDK集成技术服务
```
申请appid和appkey需要联系Q:189316826

自建平台联系Q:189316826

### ios

#### 1.appid配置
修改配置文件info.plist
```
	<key>cc.openshare.APPID</key>
	<string>appid</string>
```
#### 2.secheme配置
修改配置文件info.plist
```
	<key>CFBundleURLTypes</key>
	<array>
		<dict>
			<key>CFBundleTypeRole</key>
			<string>Editor</string>
			<key>CFBundleURLName</key>
			<string>平台分配的域名</string>
			<key>CFBundleURLSchemes</key>
			<array>
				<string>平台分配的secheme</string>
			</array>
		</dict>
	</array>
```
#### 3.通用链(Universal Link)
    
### anroid
#### 1.appid配置
修改文件AndroidManifest.xml

```
	<meta-data
            android:name="cc.openshare.APPID"
            android:value="appid"/>
```
#### 2.secheme配置
```         ...
            <intent-filter>
                <action android:name="android.intent.action.VIEW" />
                <category android:name="android.intent.category.DEFAULT" />
                <category android:name="android.intent.category.BROWSABLE" />
                <data android:scheme="平台分配的secheme" host="平台分配的域名"/>
            </intent-filter>
        </activity>
```
#### 3.App Links
注:这个在浏览器中不需要询问就能打开app和ios通用链差不多，表现方式不一样

### 功能函数及事件监听
监听

```
   addEventHandler(
       onInstallMessage:(OSInstall res)=>{},//接收安装参数
       onWakeUpMessage: (OSWakeUp res)=>{}//接收唤醒参数
    );
```

初始化
```
    setup()
```
获取安装参数
```
    getInstallParams(OSInstall res)
```
获取唤醒参数
```
    getWakeupParams(OSWakeup res)
```
### 示例
```
     _openshare = new FlutterOpenshare();
     _openshare.addEventHandler(
         onInstallMessage: (OSInstall res) {
         if(res.ret==0){
             //TODO
         }
     }, onWakeUpMessage: (OSWakeUp res) {
       if(res.ret==0){
             //TODO
         }
     });
     _openshare.setup();
```
