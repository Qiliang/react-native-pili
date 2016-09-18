#Pili Streaming Cloud React Native SDK

##Introduction

这*可能*是**第一个**在 React Native 上实现全功能的直播 SDK 了，底层基于 [Pili-SDK](https://github.com/pili-engineering)，把 iOS 和 Android 的 API 尽量统一。

2.0 版本为了更容易集成第三方 SDK ，对原有的 React Native 项目进行了改造，iOS 的依赖采用了 Cocoapod 进行管理，当然你也可以采用原来的方式，毕竟是可以共存的。为此准备了一个 [Starter Kit](https://github.com/buhe/pili-startkit) 可以查看如何进行集成。


##Installation

```bash
git clone https://github.com/buhe/pili-startkit YourPorjectName

cd YourPorjectName/js && npm install

cd ../ios && pod install
```

###Javascript

```bash
cd YourPorjectName/js
npm start
```

###iOS
1. Open ios/YourPorjectName.xcworkspace
2. Just run your project (Cmd+R)

###Android
1. Open android use Android Studio
2. Just run your project

##TODO
- [x] Android Player
- [x] Android Streaming
- [x] iOS Player
- [x] iOS Streaming
- [ ] 美颜和水印支持

##Usage
###1. 推流
```javascript
<Streaming
    rtmpURL={"rtmp://pili-publish.pilitest.qiniucdn.com/pilitest/demo_test?key=6eeee8a82246636e"}
    style={{
        height:400,
        width:400,
    }}
    zoom={1} //zoom 
    muted={true} //muted
    focus={false} //focus
    profile={{  //video and audio profile
       video:{
         fps:30,
         bps:1000 * 1024,
         maxFrameInterval:48
       },
       audio:{
         rate:44100,
         bitrate:96 * 1024
       },
    started={false} //streaming status
    onReady={()=>{}} //onReady event
    onConnecting={()=>{}} //onConnecting event
    onStreaming={()=>{}} //onStreaming event
    onShutdown={()=>{}} //onShutdown event
    onIOError={()=>{}} //onIOError event
    onDisconnected={()=>{}} //onDisconnected event
    />
```
###2. 直播播放
```javascript
<Player
  source={{
    uri:"rtmp://pili-live-rtmp.pilitest.qiniucdn.com/pilitest/xxx",
    timeout: 10 * 1000, //live streaming timeout (ms) Android only
    live:true, //live streaming ? Android only
    hardCodec:false, //hard codec [recommended false]  Android only
    }}
    started={true} //iOS only
    muted={false} //iOS only
    style={{
      height:200,
      width:200,
    }}
    onLoading={()=>{}} //loading from remote or local
    onPaused={()=>{}} //pause event
    onShutdown={()=>{}} //stopped event
    onError={()=>{}} //error event
    onPlaying={()=>{}} //play event
    />
```
##Release Note
##2.1.1
- [x] Android Player
- [x] Android Streaming
- [x] iOS Player
- [x] iOS Streaming 
