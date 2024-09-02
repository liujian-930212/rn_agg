# 代码仓库: /Users/thunder/mycode/rn

## /Users/thunder/mycode/rn/App.tsx

```
/**
 * Sample React Native App
 * https://github.com/facebook/react-native
 *
 * @format
 */

import React from "react";
import {
    StatusBar
} from "react-native";
import { Provider } from "react-redux";

import store from "./store";
import Main from "./pages/Main";
import { RootSiblingParent } from "react-native-root-siblings";

function App(): JSX.Element {
    StatusBar.setHidden(true);
    return (<Provider store={store}>
            <RootSiblingParent>
                <Main />
            </RootSiblingParent>
        </Provider>
    );
}

// export default App
export default App;

```
## /Users/thunder/mycode/rn/README.md

```
This is a new [**React Native**](https://reactnative.dev) project, bootstrapped using [`@react-native-community/cli`](https://github.com/react-native-community/cli).

# Getting Started

>**Note**: Make sure you have completed the [React Native - Environment Setup](https://reactnative.dev/docs/environment-setup) instructions till "Creating a new application" step, before proceeding.

## Step 1: Start the Metro Server

First, you will need to start **Metro**, the JavaScript _bundler_ that ships _with_ React Native.

To start Metro, run the following command from the _root_ of your React Native project:

```bash
# using npm
npm start

# OR using Yarn
yarn start
```

## Step 2: Start your Application

Let Metro Bundler run in its _own_ terminal. Open a _new_ terminal from the _root_ of your React Native project. Run the following command to start your _Android_ or _iOS_ app:

### For Android

```bash
# using npm
npm run android

# OR using Yarn
yarn android
```

### For iOS

```bash
# using npm
npm run ios

# OR using Yarn
yarn ios
```

If everything is set up _correctly_, you should see your new app running in your _Android Emulator_ or _iOS Simulator_ shortly provided you have set up your emulator/simulator correctly.

This is one way to run your app — you can also run it directly from within Android Studio and Xcode respectively.

## Step 3: Modifying your App

Now that you have successfully run the app, let's modify it.

1. Open `App.tsx` in your text editor of choice and edit some lines.
2. For **Android**: Press the <kbd>R</kbd> key twice or select **"Reload"** from the **Developer Menu** (<kbd>Ctrl</kbd> + <kbd>M</kbd> (on Window and Linux) or <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> (on macOS)) to see your changes!

   For **iOS**: Hit <kbd>Cmd ⌘</kbd> + <kbd>R</kbd> in your iOS Simulator to reload the app and see your changes!

## Congratulations! :tada:

You've successfully run and modified your React Native App. :partying_face:

### Now what?

- If you want to add this new React Native code to an existing application, check out the [Integration guide](https://reactnative.dev/docs/integration-with-existing-apps).
- If you're curious to learn more about React Native, check out the [Introduction to React Native](https://reactnative.dev/docs/getting-started).

# Troubleshooting

If you can't get this to work, see the [Troubleshooting](https://reactnative.dev/docs/troubleshooting) page.

# Learn More

To learn more about React Native, take a look at the following resources:

- [React Native Website](https://reactnative.dev) - learn more about React Native.
- [Getting Started](https://reactnative.dev/docs/environment-setup) - an **overview** of React Native and how setup your environment.
- [Learn the Basics](https://reactnative.dev/docs/getting-started) - a **guided tour** of the React Native **basics**.
- [Blog](https://reactnative.dev/blog) - read the latest official React Native **Blog** posts.
- [`@facebook/react-native`](https://github.com/facebook/react-native) - the Open Source; GitHub **repository** for React Native.

```
## /Users/thunder/mycode/rn/android/app/src/debug/AndroidManifest.xml

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>

    <application
        android:usesCleartextTraffic="true"
        tools:targetApi="28"
        tools:ignore="GoogleAppIndexingWarning" />
</manifest>

```
## /Users/thunder/mycode/rn/android/app/src/main/AndroidManifest.xml

```
<manifest xmlns:android="http://schemas.android.com/apk/res/android" >
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.MANAGE_EXTERNAL_STORAGE" />
    <!--  一般来说，允许用户自定义头像的app都需要这个权限  -->
    <uses-permission android:name="android.permission.READ_MEDIA_IMAGES"
                     android:minSdkVersion = "33"/>
    <!--  如果你想开发音乐播放器之类需要获取音频的app，加上这个权限  -->
    <uses-permission android:name="android.permission.READ_MEDIA_AUDIO"
                     android:minSdkVersion = "33"/>
    <!--  如果你想开发视频编辑器之类需要获取视频的app，加上这个权限  -->
    <uses-permission android:name="android.permission.READ_MEDIA_VIDEO"
                     android:minSdkVersion = "33"/>
    <uses-permission android:name="android.permission.DOWNLOAD_WITHOUT_NOTIFICATION" />
    <uses-permission android:name="android.permission.ACCESS_DOWNLOAD_MANAGER" />
    <uses-permission android:name="android.permission.CHANGE_COMPONENT_ENABLED_STATE"/>
    <uses-permission android:name="android.permission.RECORD_AUDIO" />
    <application
        android:largeHeap="true"
      android:name=".MainApplication"
      android:label="@string/app_name"
      android:icon="@mipmap/ic_launcher"
      android:roundIcon="@mipmap/ic_launcher_round"
        android:requestLegacyExternalStorage="true"
        android:networkSecurityConfig="@xml/network_security_config"
        android:theme="@style/AppTheme"
    >
      <activity
              android:screenOrientation="landscape"
        android:name=".MainActivity"
        android:label="@string/app_name"
        android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|screenSize|smallestScreenSize|uiMode"
        android:launchMode="singleTask"
        android:windowSoftInputMode="adjustResize"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
            <action android:name="android.intent.action.DOWNLOAD_COMPLETE"/>
        </intent-filter>
      </activity>
        <meta-data
                android:name="TD_APP_ID"
                android:value="d2627f1ba7c85e684cb65a353d5fe0a8" />
        <meta-data
                android:name="TD_APP_KEY"
                android:value="f951932fe113977a38e501ff075eca16" />
    </application>
</manifest>

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/AnalyticsModule.java

```
package com.thunder.ktvplayer;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import org.json.JSONObject;
import org.json.JSONException;
import java.util.Iterator;

import com.facebook.react.bridge.Callback;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.bridge.ReactContextBaseJavaModule;
import com.facebook.react.bridge.ReactMethod;
import com.facebook.react.bridge.ReadableArray;
import com.facebook.react.bridge.ReadableMap;
import com.facebook.react.bridge.ReadableMapKeySetIterator;
import com.facebook.react.bridge.ReadableNativeMap;
import com.facebook.react.bridge.ReadableType;
import com.umeng.analytics.MobclickAgent;

/**
 * 示例： SDK 接口桥接封装类，并未封装SDK所有API(仅封装常用API接口)，设置配置参数类API应在Android原生代码
 * 调用，例如：SDK初始化函数，Log开关函数，子进程自定义事件埋点使能函数，异常捕获功能使能/关闭函数等等。
 * 如果还需要封装其它SDK API，请参考本例自行封装
 * Created by wangfei on 17/8/28.
 * -- 适配海棠版(common 2.0.0 + analytics 8.0.0) modify by yujie on 18/12/28
 */

public class AnalyticsModule extends ReactContextBaseJavaModule {
    private ReactApplicationContext context;

    public AnalyticsModule(ReactApplicationContext reactContext) {
        super(reactContext);
        context = reactContext;
    }

    @Override
    public String getName() {
        return "UMAnalyticsModule";
    }

    /********************************U-App统计*********************************/
    @ReactMethod
    public void onPageStart(String pageName) {
        //android.util.Log.e("xxxxxx","onPageStart="+mPageName);

        MobclickAgent.onPageStart(pageName);
    }

    @ReactMethod
    public void onPageEnd(String pageName) {
        //android.util.Log.e("xxxxxx","onPageEnd="+mPageName);

        MobclickAgent.onPageEnd(pageName);

    }
    @ReactMethod
    public void onEvent(String eventId) {
        MobclickAgent.onEvent(context, eventId);
    }
    @ReactMethod
    public void onEventWithLable(String eventId, String eventLabel) {
        MobclickAgent.onEvent(context, eventId, eventLabel);
    }
    @ReactMethod
    public void onEventWithMap(String eventId, ReadableMap map) {
        Map<String, String> rMap = new HashMap<String, String>();
        ReadableMapKeySetIterator iterator = map.keySetIterator();
        while (iterator.hasNextKey()) {
            String key = iterator.nextKey();
            if (ReadableType.Array == map.getType(key)) {
                rMap.put(key, map.getArray(key).toString());
            } else if (ReadableType.Boolean == map.getType(key)) {
                rMap.put(key, String.valueOf(map.getBoolean(key)));
            } else if (ReadableType.Number == map.getType(key)) {
                rMap.put(key, String.valueOf(map.getInt(key)));
            } else if (ReadableType.String == map.getType(key)) {
                rMap.put(key, map.getString(key));
            } else if (ReadableType.Map == map.getType(key)) {
                rMap.put(key, map.getMap(key).toString());
            }
        }
        MobclickAgent.onEvent(context, eventId, rMap);
    }
    @ReactMethod
    public void onEventWithMapAndCount(String eventId,ReadableMap map,int value) {
        Map<String, String> rMap = new HashMap();
        ReadableMapKeySetIterator iterator = map.keySetIterator();
        while (iterator.hasNextKey()) {
            String key = iterator.nextKey();
            if (ReadableType.Array == map.getType(key)) {
                rMap.put(key, map.getArray(key).toString());
            } else if (ReadableType.Boolean == map.getType(key)) {
                rMap.put(key, String.valueOf(map.getBoolean(key)));
            } else if (ReadableType.Number == map.getType(key)) {
                rMap.put(key, String.valueOf(map.getInt(key)));
            } else if (ReadableType.String == map.getType(key)) {
                rMap.put(key, map.getString(key));
            } else if (ReadableType.Map == map.getType(key)) {
                rMap.put(key, map.getMap(key).toString());
            }
        }
        MobclickAgent.onEventValue(context, eventId, rMap, value);
    }

    @ReactMethod
    public void onEventObject(String eventID, ReadableMap property) {
        Map<String, Object> map = new HashMap();
        ReadableMapKeySetIterator iterator = property.keySetIterator();
        while (iterator.hasNextKey()) {
            String key = iterator.nextKey();
            if (ReadableType.Array == property.getType(key)) {
                map.put(key, property.getArray(key).toString());
            } else if (ReadableType.Boolean == property.getType(key)) {
                map.put(key, String.valueOf(property.getBoolean(key)));
            } else if (ReadableType.Number == property.getType(key)) {
                map.put(key, String.valueOf(property.getInt(key)));
            } else if (ReadableType.String == property.getType(key)) {
                map.put(key, property.getString(key));
            } else if (ReadableType.Map == property.getType(key)) {
                map.put(key, property.getMap(key).toString());
            }
        }

        MobclickAgent.onEventObject(context, eventID, map);

    }
    @ReactMethod
    public void registerPreProperties(ReadableMap map) {
        ReadableNativeMap map2 = (ReadableNativeMap) map;
        Map<String, Object> map3  = map2.toHashMap();
        Iterator entries = map3.entrySet().iterator();
        JSONObject json = new JSONObject();
        while (entries.hasNext()) {
            Map.Entry entry = (Map.Entry) entries.next();
            String key = (String)entry.getKey();
            String value = (String)entry.getValue();
            try {
                json.put(key,value);
            }catch (JSONException e){

            }
        }
        MobclickAgent.registerPreProperties(context,json);
    }
    @ReactMethod
    public void unregisterPreProperty(String propertyName) {
        MobclickAgent.unregisterPreProperty(context, propertyName);

    }

    @ReactMethod
    public void getPreProperties(Callback callback) {
        String result = MobclickAgent.getPreProperties(context).toString();
        callback.invoke(result);
    }
    @ReactMethod
    public void clearPreProperties() {
        MobclickAgent.clearPreProperties(context);

    }
    @ReactMethod
    public void setFirstLaunchEvent(ReadableArray array) {
        List<String> list = new ArrayList();
        for (int i = 0; i < array.size(); i++) {
            if (ReadableType.Array == array.getType(i)) {
                list.add(array.getArray(i).toString());
            } else if (ReadableType.Boolean == array.getType(i)) {
                list.add(String.valueOf(array.getBoolean(i)));
            } else if (ReadableType.Number == array.getType(i)) {
                list.add(String.valueOf(array.getInt(i)));
            } else if (ReadableType.String == array.getType(i)) {
                list.add(array.getString(i));
            } else if (ReadableType.Map == array.getType(i)) {
                list.add(array.getMap(i).toString());
            }
        }
        MobclickAgent.setFirstLaunchEvent(context, list);
    }
    /********************************U-Dplus*********************************/
    @ReactMethod
    public void profileSignInWithPUID(String puid) {
        MobclickAgent.onProfileSignIn(puid);
    }

    @ReactMethod
    @SuppressWarnings("unused")
    public void profileSignInWithPUIDWithProvider(String provider, String puid) {
        MobclickAgent.onProfileSignIn(provider, puid);
    }

    @ReactMethod
    @SuppressWarnings("unused")
    public void profileSignOff() {
        MobclickAgent.onProfileSignOff();
    }

}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/DownloadSongModule.java

```
package com.thunder.ktvplayer;

import android.os.Handler;
import android.os.HandlerThread;
import android.os.Message;
import android.os.Bundle;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.bridge.ReactContextBaseJavaModule;
import com.facebook.react.modules.core.DeviceEventManagerModule;
import com.facebook.react.bridge.ReactMethod;
import com.facebook.react.bridge.Promise;
import com.facebook.react.uimanager.ThemedReactContext;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.bridge.Arguments;
import com.thunder.android.stb.util.download.IDownloadController;
import com.thunder.android.stb.util.interfaces.DownloadListener;
import com.thunder.android.stb.util.log.Logger;
import com.thunder.android.stb.util.model.DownloadBean;
import com.thunder.ktv.player.mediaplayer.video.SongDownloader;
import javax.annotation.Nullable;
import android.util.Log;
import androidx.annotation.NonNull;
import java.io.File;

import org.json.JSONException;
import org.json.JSONObject;

public class DownloadSongModule extends ReactContextBaseJavaModule {
    private static final String TAG = "DownloadSongModule";
    private static final int MESSAGE_UPDATE_UI = 1;
    private IDownloadController downloadController;
    private  String songName;
    private String songid;
    private Message reStartMessage = new Message();//下载重试缓存
    private HandlerThread handlerThread;
    private Handler backgroundHandler;
    private int resetNumber = 0;
    public DownloadSongModule(ReactApplicationContext reactContext) {
        super(reactContext);
        // 创建并启动HandlerThread
        handlerThread = new HandlerThread("MyHandlerThread");
        handlerThread.start();
         // 创建后台线程的Handler
        backgroundHandler = new Handler(handlerThread.getLooper()) {
            @Override
            public void handleMessage(@NonNull Message msg) {
                if (msg.what == MESSAGE_UPDATE_UI) {
                    reStartMessage.copyFrom(msg);
                    DownloadBean obj = (DownloadBean) msg.obj;
                    String videoOpt = msg.getData().getString("videoOpt");
                    Log.d(TAG, videoOpt + "videoOpt");
                    if (downloadController != null) {
                        downloadController.stop();
                    }
                    try {
                        downloadController = SongDownloader.getInstance().download(
                                videoOpt,
                                obj,
                                downloadListener
                        );
                    } catch (Exception e) {
                        e.printStackTrace();
                    }
                }
            }
        };
    }
    @Override
    public String getName() {
        return "DownloadSongModule";
    }
    @ReactMethod
    public void addListener(String eventName) {
      // Set up any upstream listeners or background tasks as necessary
    }
    @ReactMethod
    public void removeListeners(Integer count) {
      // Remove upstream listeners, stop unnecessary background tasks
    }
    final DownloadListener downloadListener = new DownloadListener() {

        @Override
        public void onStart(String s, String s1, String s2, long l) {
            Log.d(TAG, "songNo:" + s + "songName" + s1 + ", download start");
            WritableMap params = Arguments.createMap();
            params.putString("type", "onStart");
            params.putString("songid", s);
            params.putString("songName", s1);
            sendEvent("downloadListener", params);
        }

        @Override
        public void onProgress(String s, int progress) {
            Log.d(TAG, "songNo:" + s + ", progress:" + progress);
            WritableMap params = Arguments.createMap();
            params.putString("type", "onProgress");
            params.putString("songid", s);
            params.putString("songName", songName);
            params.putInt("progress", progress);
            sendEvent("downloadListener", params);
        }

        @Override
        public void onDownloaded(String songNo, String path, String mediaFileName, int mediaFileLength) {
            resetNumber = 0;
            Log.d(TAG, "songNo:" + songNo + ", download complete:" + path);
            int lastDotIndex = path.lastIndexOf('.');
            String filePath = path.substring(0, lastDotIndex);
            try {
                File oldFile = new File(path);
                File newFile = new File(filePath);
                if (oldFile.exists()) {
                    if (oldFile.renameTo(newFile)) {
                         Log.d(TAG, "File renamed successfully");
                         WritableMap params = Arguments.createMap();
                         params.putString("type", "onCompleted");
                         params.putString("songid", songNo);
                         params.putString("songName", songName);
                         params.putString("path", filePath);
                         sendEvent("downloadListener", params);
                    } else {
                        Log.d(TAG,"Rename Error File rename failed");
                    }
                } else {
                    Log.d(TAG,"File Not Found The specified file does not exist");
                }
            } catch (Exception e) {
                Log.d(TAG,"Exception"+ e.getMessage());
            }

        }

        @Override
        public void onFail(String s, int errorType, int errorCode, String msg) {
            Log.e(TAG, "songNo:" + s + "errorType=" + errorType + ", error code:" + errorCode + ", msg:" + msg);
            WritableMap params = Arguments.createMap();
             params.putString("type", "onError");
             params.putString("songName", songName);
             params.putString("songid", songid);
             sendEvent("downloadListener", params);
//             if(resetNumber == 5) {
//                  WritableMap params = Arguments.createMap();
//                  params.putString("type", "onError");
//                  params.putString("songName", songName);
//                  sendEvent("downloadListener", params);
//                  resetNumber = 0;
//             } else {
//                 if(errorCode == -1 || errorCode == -2 || errorType == -1 || errorType == -2) {
//                     if (reStartMessage.getData() != null) {
//                         resetNumber++;
//                         backgroundHandler.sendMessage(reStartMessage);
//                     }
//                 }
//             }

        }


    };
    // 发送事件到 JavaScript 侧
      private void sendEvent(String eventName, @Nullable WritableMap params) {
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
            .emit(eventName, params);
      }
    @ReactMethod
    public void downloadSong(String songname,String songNo, String path, String resolution) {
        Log.d(TAG, "downloadSong" + songname + songNo + path);
        songName = songname;
        songid = songNo;
        Message obtain = Message.obtain();
//         String resolution = "720";//设置分辨率 值为 "1080","720","480","320","240"
        JSONObject jsonObject = new JSONObject();//设置播放源options
        try {
            jsonObject.put("musicno", songNo);
            jsonObject.put("is265", "0");
            jsonObject.put("resolution", resolution);
            jsonObject.put("ls", "0");
        } catch (JSONException e) {
            e.printStackTrace();
        }
        Bundle data = new Bundle();
        data.putString("videoOpt", jsonObject.toString());
        obtain.setData(data);
        String jsonString = jsonObject.toString();
        final DownloadBean bean = new DownloadBean(songName, songNo, path);//下载路径
        obtain.obj = bean;
        obtain.what = MESSAGE_UPDATE_UI;
         backgroundHandler.sendMessage(obtain);
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/DplusReactPackage.java

```
package com.thunder.ktvplayer;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.List;

import com.facebook.react.ReactPackage;
import com.facebook.react.bridge.JavaScriptModule;
import com.facebook.react.bridge.NativeModule;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.shell.MainReactPackage;
import com.facebook.react.uimanager.ViewManager;

/**
 * Created by wangfei on 17/8/28.
 */

public class DplusReactPackage implements ReactPackage {

    @Override
    public List<ViewManager> createViewManagers(ReactApplicationContext reactContext) {
        return Collections.emptyList();
    }

    /**
     * 如需要添加本地方法，只需在这里add
     *
     * @param reactContext
     * @return
     */
    @Override
    public List<NativeModule> createNativeModules(
        ReactApplicationContext reactContext) {
        List<NativeModule> modules = new ArrayList<>();
//         modules.add(new ShareModule(reactContext));
//         modules.add(new PushModule(reactContext));
        modules.add(new AnalyticsModule(reactContext));
        return modules;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/HandInputDrawingPad.java

```
package com.thunder.ktvplayer;

import android.content.Context;
import android.content.res.TypedArray;
import android.graphics.Canvas;
import android.graphics.Paint;
import android.os.SystemClock;
import android.util.AttributeSet;
import android.view.MotionEvent;
import android.view.View;
// import com.thunder.lib_base.R;
import java.util.ArrayList;
import java.util.List;
import android.util.Log;

// import com.thunder.ktv.thunderndk.thunderapi.TDHandInput;
import com.thunder.ktv.thunderjni.thunderapi.TDHandInput;
import com.thunder.ktv.thunderjni.thunderapi.TDLocal;
import com.facebook.react.bridge.Arguments;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.uimanager.events.RCTEventEmitter;
import com.facebook.react.uimanager.ThemedReactContext;
import com.facebook.react.bridge.ReactContext;

import android.view.MotionEvent;

import android.graphics.Path;

import java.io.File;
/**
 * Created by zhangshichuan on 2016/12/12.
 */

public class HandInputDrawingPad extends View {

  private static final int DEFAULT_STROKE_COLOR = 0xff2089dc;
  private static final int DEFAULT_STROKE_WIDTH = 4;
  private static final int WRITE_STOP_TIMEOUT = 500;
  private static final int DRAW_PATH_MOVE_TOLERANCE = 4;
  private static final int MAX_POINT_COUNT = 5120;

  private Paint mPaint;
  private Path mPath;
  private List<Integer> mTmpPointList;
  private List<Integer> mFinalPointList = new ArrayList<>(5120 * 2);
  private int mStrokeColor = DEFAULT_STROKE_COLOR;
  private int mStrokeWidth = DEFAULT_STROKE_WIDTH;
  private TDHandInput sTDHandInput;

  // 表示DrawingPad两次reset之间的存在状态，识别任务的提交、回调不能跨session
  private long mSession;

  private ThemedReactContext reactContext;  // 保存 reactContext

  public HandInputDrawingPad(ThemedReactContext context) {
    super(context, null);
    this.reactContext = context;
    init();
  }

  public HandInputDrawingPad(ThemedReactContext context, AttributeSet attrs) {
    super(context, attrs, 0);
    this.reactContext = context;
    init();
  }

  public HandInputDrawingPad(ThemedReactContext context, AttributeSet attrs, int defStyleAttr) {
    super(context, attrs, defStyleAttr);
    this.reactContext = context;
    init();
  }

  private void init() {
    setWillNotDraw(false);
    mPaint = new Paint();
    mPaint.setAntiAlias(true);
    mPaint.setDither(true);
    mPaint.setStyle(Paint.Style.STROKE);
    mPaint.setStrokeJoin(Paint.Join.ROUND);
    mPaint.setStrokeCap(Paint.Cap.ROUND);
    mPaint.setColor(mStrokeColor);
    mPaint.setStrokeWidth(mStrokeWidth);
    mPath = new Path();
    // 确保目录存在
    File directory = new File(this.reactContext.getExternalFilesDir(null), "handwrite");
    File outFile = new File(directory, "PC_HSDic.dat");
     TDLocal.native_init(outFile.getAbsolutePath());
//     int intTotal = TDLocal.native_init("/storage/emulated/0/Android/data/com.ktvplayer/files/handwrite/PC_HSDic.dat");
//     Log.d("intTotal", String.valueOf(intTotal));
  }
  @Override
  protected void onDraw(Canvas canvas) {
    if (mPath == null) {
      return;
    }
    canvas.drawPath(mPath, mPaint);
  }

  private boolean mDrawingLine;
  private boolean mWriting;
  private boolean mRecognizing;


  private float mX;
  private float mY;

  private void onTouchStart(float x, float y) {
    mDrawingLine = true;
    mWriting = true;
    removeCallbacks(postToRecognizeRunnable);
    mPath.moveTo(x, y);
    mX = x;
    mY = y;
    mTmpPointList = new ArrayList<>();
    mTmpPointList.add(Math.round(x));
    mTmpPointList.add(Math.round(y));
    invalidate();
  }

  private void onTouchMove(float x, float y) {
    if (Math.abs(x - mX) > DRAW_PATH_MOVE_TOLERANCE
        || Math.abs(y - mY) > DRAW_PATH_MOVE_TOLERANCE) {
      mPath.quadTo(mX, mY, (x + mX) / 2, (y + mY) / 2);
      mX = x;
      mY = y;
    }
    mTmpPointList.add(Math.round(x));
    mTmpPointList.add(Math.round(y));
    invalidate();
  }

  private void onTouchEnd(float x, float y) {
    mDrawingLine = false;
    mTmpPointList.add(Math.round(x));
    mTmpPointList.add(Math.round(y));
    if (mTmpPointList.size() == 4) {
      return;
    }
    mTmpPointList.add(-1);
    mTmpPointList.add(0);
    mFinalPointList.addAll(mTmpPointList);
    postDelayed(postToRecognizeRunnable, WRITE_STOP_TIMEOUT);
  }

  @Override
  public boolean onTouchEvent(MotionEvent event) {
    float x = event.getX();
    float y = event.getY();
    switch (event.getAction()) {
      case MotionEvent.ACTION_DOWN:
        if (mRecognizing) {
          return true;
        }
        if (isInBound(x, y)) {
          onTouchStart(x, y);
        }
        break;
      case MotionEvent.ACTION_MOVE:
        if (isInBound(x, y)) {
          if (!mDrawingLine) {
            if (mRecognizing) {
              return true;
            }
            onTouchStart(x, y);
          } else {
            onTouchMove(x, y);
          }
        } else {
          if (mDrawingLine) {
            onTouchEnd(x, y);
          }
        }
        break;
      case MotionEvent.ACTION_UP:
        if (mDrawingLine) {
          onTouchEnd(x, y);
        }
        break;
    }
    return true;
  }

  private boolean isInBound(float x, float y) {
    return x > 0 && x < getWidth() && y > 0 && y < getHeight();
  }

  private void clear() {
    mPath.reset();
    invalidate();
  }

  private Runnable postToRecognizeRunnable = new Runnable() {
    @Override
    public void run() {
      clear();
      if (mFinalPointList.size() == 0) {
        return;
      }
      mFinalPointList.add(-1);
      mFinalPointList.add(-1);
      mWriting = false;
      mRecognizing = true;
      onFinishWriting(mFinalPointList);
    }
  };

  /**
   * 识别完成后调用此方法
   */
  public void reset() {
    mRecognizing = false;
    mDrawingLine = false;
    mWriting = false;
    mFinalPointList.clear();
    mTmpPointList = null;
    clear();
    removeCallbacks(postToRecognizeRunnable);
    mSession = SystemClock.uptimeMillis();
  }

  public long getSession() {
    return mSession;
  }

  public void setBackgroundColor(int color) {
      super.setBackgroundColor(color);
      invalidate(); // 重新绘制，以显示新的颜色
  }

  public void onFinishWriting(List<Integer> pointList) {
   Log.e("pointList", String.valueOf(pointList));
      char[] points = new char[MAX_POINT_COUNT * 2];
      int sampleCount = pointList.size() / 2;

      int pointCount = Math.min(MAX_POINT_COUNT, pointList.size() / 2);

      //转换
      for (int i = 0; i < pointCount; i++) {
          points[i * 2] = (char) pointList.get(i * 2).intValue();
          points[i * 2 + 1] = (char) pointList.get(i * 2 + 1).intValue();
      }

      if (sampleCount > pointCount) {
          points[MAX_POINT_COUNT * 2 - 4] = (char) -1;
          points[MAX_POINT_COUNT * 2 - 3] = (char) 0;
          points[MAX_POINT_COUNT * 2 - 2] = (char) -1;
          points[MAX_POINT_COUNT * 2 - 1] = (char) -1;
      }
      if (sTDHandInput == null) {
          sTDHandInput = new TDHandInput();
      }
      String result = null;
      if(sTDHandInput.getHandInputCandidates(points, pointCount) != null) {
            result = new String(sTDHandInput.getHandInputCandidates(points, pointCount));
      } else {
          Log.e("pointsresult", String.valueOf(sTDHandInput.getHandInputCandidates(points, pointCount)));
      }

      WritableMap event = Arguments.createMap();
        event.putString("result", result);
        ReactContext reactContext = (ReactContext)getContext();
        reactContext.getJSModule(RCTEventEmitter.class).receiveEvent(getId(), "change", event);
      reset();
  }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/HandwritingViewManager.java

```
package com.thunder.ktvplayer;

import android.view.View;

import com.facebook.react.uimanager.SimpleViewManager;
import com.facebook.react.uimanager.ThemedReactContext;
import com.facebook.react.bridge.ReactContext;
import com.facebook.react.uimanager.annotations.ReactProp;
import android.graphics.Color;
import com.facebook.react.bridge.Callback;
// import com.thunder.lib_keyboard.input.keyboard.HandKeyBoard;
// import com.thunder.lib_base.base.view.keyboard.ui.view.HandInputDrawingPad;
import java.util.Map;

import com.facebook.react.bridge.Arguments;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.uimanager.events.RCTEventEmitter;
import com.facebook.react.modules.core.DeviceEventManagerModule;
import com.facebook.react.common.MapBuilder;
import android.os.Environment;

public class HandwritingViewManager extends SimpleViewManager<View> {

    public static final String REACT_CLASS = "HandInputDrawingPad";
        private ThemedReactContext reactContext;  // 保存 reactContext
        private View view;

    @Override
    public String getName() {
        return REACT_CLASS;
    }
    @Override
    protected HandInputDrawingPad createViewInstance(ThemedReactContext reactContext) {
        this.reactContext = reactContext;
        // 创建 HandInputDrawingPad 实例
//          copyDatData();
        HandInputDrawingPad handInputDrawingPad = new HandInputDrawingPad(reactContext);
        this.view = handInputDrawingPad;
        return handInputDrawingPad;
    }
    public Map getExportedCustomBubblingEventTypeConstants() {
        return MapBuilder.builder()
            .put(
                "change",
                MapBuilder.of(
                    "phasedRegistrationNames",
                    MapBuilder.of("bubbled", "onChange")))
                    .build();
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/MainActivity.java

```
package com.thunder.ktvplayer;

import com.facebook.react.ReactActivity;
import com.facebook.react.ReactActivityDelegate;
import com.facebook.react.defaults.DefaultNewArchitectureEntryPoint;
import com.facebook.react.defaults.DefaultReactActivityDelegate;
import com.umeng.analytics.MobclickAgent;
import android.os.Bundle;
import org.devio.rn.splashscreen.SplashScreen;
import android.view.KeyEvent;
import android.util.Log;
import com.facebook.react.ReactInstanceManager;
import com.facebook.react.bridge.ReactContext;
import com.facebook.react.modules.core.DeviceEventManagerModule;
import android.content.Intent;

public class MainActivity extends ReactActivity {

  /**
   * Returns the name of the main component registered from JavaScript. This is used to schedule
   * rendering of the component.
   */
  @Override
  protected String getMainComponentName() {
    return "ktvPlayer";
  }

  /**
   * Returns the instance of the {@link ReactActivityDelegate}. Here we use a util class {@link
   * DefaultReactActivityDelegate} which allows you to easily enable Fabric and Concurrent React
   * (aka React 18) with two boolean flags.
   */
  @Override
  protected ReactActivityDelegate createReactActivityDelegate() {
    return new DefaultReactActivityDelegate(
        this,
        getMainComponentName(),
        // If you opted-in for the New Architecture, we enable the Fabric Renderer.
        DefaultNewArchitectureEntryPoint.getFabricEnabled());
  }
   @Override
  public void onResume() {
      super.onResume();
      MobclickAgent.onResume(this);
  }
  @Override
  protected void onPause() {
      super.onPause();
      MobclickAgent.onPause(this);
  }
  @Override
    public boolean onKeyDown(int keyCode, KeyEvent event) {
         ReactInstanceManager reactInstanceManager = getReactInstanceManager();
         ReactContext reactContext = reactInstanceManager.getCurrentReactContext();
        reactContext.getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
          .emit("onKeyDown", keyCode);
        return super.onKeyDown(keyCode, event);
    }
    @Override
   protected void onCreate(Bundle savedInstanceState) {
       SplashScreen.show(this);  // here
       super.onCreate(null);
       MobclickAgent.setSessionContinueMillis(1000);
       // 获取启动 Intent
       Intent intent = getIntent();
       if (intent != null) {
           // 获取字符串参数
           if(intent.hasExtra("m1")) {
               String m0 = intent.getStringExtra("m0");
               String m1 = intent.getStringExtra("m1");
                Log.d("22222222222", m0 + m1);
                RnUtilsModule.m0= m0;
                RnUtilsModule.m1= m1;
           }

       }
   }


}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/MainApplication.java

```
package com.thunder.ktvplayer;

import android.app.Application;
import android.content.Context;
import com.facebook.react.PackageList;
import com.facebook.react.ReactApplication;
import com.facebook.react.ReactNativeHost;
import com.facebook.react.ReactPackage;
import com.facebook.react.defaults.DefaultNewArchitectureEntryPoint;
import com.facebook.react.defaults.DefaultReactNativeHost;
import com.facebook.soloader.SoLoader;
import java.util.List;
import com.thunder.ktvplayer.RnUtilsPackage;
import com.umeng.commonsdk.UMConfigure;
import com.thunder.ktvplayer.RNUMConfigure;
import com.thunder.ktvplayer.DplusReactPackage;

public class MainApplication extends Application implements ReactApplication {

  private final ReactNativeHost mReactNativeHost =
      new DefaultReactNativeHost(this) {
        @Override
        public boolean getUseDeveloperSupport() {
          return BuildConfig.DEBUG;
        }

        @Override
        protected List<ReactPackage> getPackages() {
          @SuppressWarnings("UnnecessaryLocalVariable")
          List<ReactPackage> packages = new PackageList(this).getPackages();
          // Packages that cannot be autolinked yet can be added manually here, for example:
          // packages.add(new MyReactNativePackage());
            packages.add(new RnUtilsPackage());
            packages.add(new DplusReactPackage());
          return packages;
        }

        @Override
        protected String getJSMainModuleName() {
          return "index";
        }

        @Override
        protected boolean isNewArchEnabled() {
          return BuildConfig.IS_NEW_ARCHITECTURE_ENABLED;
        }

        @Override
        protected Boolean isHermesEnabled() {
          return BuildConfig.IS_HERMES_ENABLED;
        }
      };

  @Override
  public ReactNativeHost getReactNativeHost() {
    return mReactNativeHost;
  }
  @Override
  public void onCreate() {
    super.onCreate();
    SoLoader.init(this, /* native exopackage */ false);
    RNUMConfigure.init(this, "653b4518b2f6fa00ba6d68e6", "tuobu_maiduan", UMConfigure.DEVICE_TYPE_PHONE,
                "");
    if (BuildConfig.IS_NEW_ARCHITECTURE_ENABLED) {
      // If you opted-in for the New Architecture, we load the native entry point for this app.
      DefaultNewArchitectureEntryPoint.load();
    }
//     ReactNativeFlipper.initializeFlipper(this, getReactNativeHost().getReactInstanceManager());
  }
}


```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/MyPresentation.java

```
package com.thunder.ktvplayer;

import android.app.Presentation;
import android.content.Context;
import android.os.Bundle;
import android.view.Display;
import android.widget.ImageView;
import android.widget.FrameLayout;
import android.widget.RelativeLayout;
import com.thunder.ktvplayer.video.PlayerView;
import android.widget.FrameLayout;
import android.graphics.Bitmap;
import android.view.ViewTreeObserver;
import android.widget.TextView;
import android.widget.LinearLayout;
import android.view.View;

import com.google.zxing.BarcodeFormat;
import com.google.zxing.EncodeHintType;
import com.google.zxing.WriterException;
import com.google.zxing.common.BitMatrix;
import com.google.zxing.qrcode.QRCodeWriter;
import com.google.zxing.qrcode.decoder.ErrorCorrectionLevel;
import com.youth.banner.Banner;
import com.thunder.ktvplayer.video.CustomMarqueeTextAdapter;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;
import android.util.Log;
import android.os.Handler;
import android.os.Looper;

public class MyPresentation extends Presentation {

    private PlayerView playerView;
    private int QR_CODE_WIDTH = 150;
    private int QR_CODE_HEIGHT = 150;
    private static final int MARGIN = 0; // 边距设置（以像素为单位）
    private String qrcodeUrl;
    ImageView qrCodeImageView;
    RelativeLayout frameLayout;
    ArrayList<String> titleList;
    Banner banner;
    Handler handler;

    public MyPresentation(Context context, Display display, PlayerView playerView) {
        super(context, display);
        this.playerView = playerView;
    }
    public void setQrcodeUrl(String url) {
        qrcodeUrl = url;
        setQrcode();
    }
    private void setQrcode() {

        if(frameLayout == null) {
            return;
        }
        handler.post(new Runnable() {
            @Override
            public void run() {
                try {
                    Bitmap bitmap = generateQRCode(qrcodeUrl);
                    qrCodeImageView.setImageBitmap(bitmap);
                } catch (WriterException e) {
                    e.printStackTrace();
                }
            }
        });
    }
    public void setTitle(String title) {
        handler.post(new Runnable() {
            @Override
            public void run() {
                if(title.indexOf("&_&") != -1) {
                     titleList = new ArrayList<String>(Arrays.asList(title.split("&_&")));
                } else {
                    titleList = new ArrayList<>(Arrays.asList("未点歌"));
                }
                CustomMarqueeTextAdapter customMarqueeTextAdapter = new CustomMarqueeTextAdapter(titleList);
                banner = findViewById(R.id.banner_marquee_text);
                banner.setAdapter(customMarqueeTextAdapter)
                                .isAutoLoop(true)
                                .setLoopTime(10000)
                                .setOrientation(Banner.VERTICAL);
                if(titleList.size() > 1) {
                    banner.start();
                } else {
                    banner.stop();
                }
            }
        });

    }
    public void setName(String name) {
        handler.post(new Runnable() {
            @Override
            public void run() {
                ArrayList<String> list = new ArrayList<String>(Arrays.asList(name.split("&_&")));
                TextView songName = findViewById(R.id.song_name);
                TextView singerName = findViewById(R.id.singer_name);
                if(songName != null) {
                    songName.setText(list.get(1));
                }
                if(singerName != null) {
                    singerName.setText(list.get(0));
                }
            }
        });


    }
    public void setLoading(boolean loading) {
        handler.post(new Runnable() {
            @Override
            public void run() {
                LinearLayout linearLayout = findViewById(R.id.loading_show);

                if(loading) {
                    linearLayout.setVisibility(View.VISIBLE);
                } else {
                    linearLayout.setVisibility(View.GONE);
                }
            }
        });

    }
    private Bitmap generateQRCode(String text) throws WriterException {
        // 设置边距和其他参数
        Map<EncodeHintType, Object> hints = new HashMap<>();
        hints.put(EncodeHintType.MARGIN, MARGIN); // 设置边距
        hints.put(EncodeHintType.ERROR_CORRECTION, ErrorCorrectionLevel.L);
        QRCodeWriter qrCodeWriter = new QRCodeWriter();
        QR_CODE_WIDTH = (int)qrCodeImageView.getWidth();
        QR_CODE_HEIGHT = (int) qrCodeImageView.getHeight();
        BitMatrix bitMatrix = qrCodeWriter.encode(text, BarcodeFormat.QR_CODE, QR_CODE_WIDTH, QR_CODE_HEIGHT, hints);
        int width = bitMatrix.getWidth();
        int height = bitMatrix.getHeight();
        Bitmap bitmap = Bitmap.createBitmap(width, height, Bitmap.Config.RGB_565);
        for (int x = 0; x < width; x++) {
            for (int y = 0; y < height; y++) {
                bitmap.setPixel(x, y, bitMatrix.get(x, y) ? 0xFF000000 : 0xFFFFFFFF);
            }
        }
        return bitmap;
    }
    public void destroyBanner() {
        if(banner != null) {
            banner.destroy();
            banner = null;
        }
    }
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        handler = new Handler(Looper.getMainLooper());
        setContentView(R.layout.video_fullscreen);
        FrameLayout.LayoutParams layoutParams = new FrameLayout.LayoutParams(
                        FrameLayout.LayoutParams.MATCH_PARENT,
                        FrameLayout.LayoutParams.MATCH_PARENT);
        frameLayout = findViewById(R.id.video_fullscreen_layout);
        qrCodeImageView = findViewById(R.id.qrCodeImageView);
        frameLayout.addView(playerView, 0, layoutParams);
        frameLayout.getViewTreeObserver().addOnGlobalLayoutListener(new ViewTreeObserver.OnGlobalLayoutListener() {
            @Override
            public void onGlobalLayout() {
                setQrcode();

            }
        });
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/RNUMConfigure.java

```
package com.thunder.ktvplayer;

import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

import android.annotation.TargetApi;
import android.content.Context;
import android.os.Build.VERSION_CODES;
import com.umeng.commonsdk.UMConfigure;

/**
 * Created by wangfei on 17/9/14.
 */

public class RNUMConfigure {
    public static void init(Context context, String appkey, String channel, int type, String secret){
        initRN("react-native","2.0");
        UMConfigure.init(context,appkey,channel,type,secret);
    }
    @TargetApi(VERSION_CODES.KITKAT)
    private static void initRN(String v, String t){
        Method method = null;
        try {
            Class<?> config = Class.forName("com.umeng.commonsdk.UMConfigure");
            method = config.getDeclaredMethod("setWraperType", String.class, String.class);
            method.setAccessible(true);
            method.invoke(null, v,t);
        } catch (NoSuchMethodException | InvocationTargetException | IllegalAccessException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/RnUtilsModule.java

```
package com.thunder.ktvplayer;

import android.app.Activity;

import android.content.Context;
import android.content.BroadcastReceiver;
import android.content.Intent;
import android.content.IntentFilter;
import android.net.Uri;
import android.net.wifi.WifiInfo;
import android.net.wifi.WifiManager;
import android.util.Log;
import android.os.storage.StorageManager;
import android.os.storage.StorageVolume;
import android.os.Build;
import android.os.StatFs;
import android.os.Environment;
import android.os.UserHandle;
import android.view.View;
import android.view.Window;
import android.os.Handler;
import android.media.AudioManager;

import java.lang.reflect.Method;
import java.lang.reflect.Constructor;
import java.io.File;
import java.io.FileOutputStream;
import java.io.FileInputStream;
import java.io.InputStream;
import java.io.OutputStream;
import java.io.ByteArrayOutputStream;
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.Arrays;
import java.util.List;
import java.util.Set;
import java.net.HttpURLConnection;
import java.net.URL;
import java.security.MessageDigest;
import javax.crypto.Cipher;
import javax.crypto.spec.SecretKeySpec;
import javax.annotation.Nullable;

import org.apache.commons.codec.binary.Hex;
import com.facebook.react.bridge.Promise;
import com.facebook.react.bridge.NativeModule;
import com.facebook.react.bridge.ReactContext;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.bridge.WritableArray;
import com.facebook.react.bridge.Arguments;
import com.facebook.react.modules.core.DeviceEventManagerModule;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.bridge.ReactContextBaseJavaModule;
import com.facebook.react.bridge.ReactMethod;
import com.facebook.react.uimanager.ThemedReactContext;
import net.sourceforge.pinyin4j.PinyinHelper;
import com.thunder.ktv.player.mediaplayer.callback.InitPlayerCallback;
import com.thunder.ktv.player.mediaplayer.callback.SimpleVodCallBack;
import com.thunder.ktv.player.mediaplayer.config.Config;
import com.thunder.ktv.player.mediaplayer.video.FactoryMediaPlayer;
import com.thunder.ktv.player.vod.VodReponseAction;
import com.thunder.ktv.player.vod.VodRequestAction;
import com.thunder.ktv.player.vod.VodAction;
import android.media.AudioManager;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.lang.reflect.Method;

public class RnUtilsModule extends ReactContextBaseJavaModule {
    private static final String TAG = "RnUtilsModule";
    private static final String VOICE_ACTION = "com.thunder.ktvplayer.VOICE_ACTION";
    public static String m0 = null;
    public static String m1 = null;

    private long downloadId = -1;
    private final ReactApplicationContext reactContext;
    SimpleVodCallBack vodCallback = new SimpleVodCallBack() {
        @Override
        public void onDealAction(VodRequestAction vodAction, VodReponseAction vodReponseAction) {
            if (vodAction != null) {
                Log.i(TAG, "action is " + vodAction.getAction());
                switch (vodAction.getAction()) {
                    case VodAction.ACTION_ADD:
                        // 点歌成功

                        break;
                    case VodAction.ACTION_LIST:
                        // 获取点歌列表
                        break;
                    case VodAction.ACTION_CUT:
                        // 控制指令切歌操作
                        break;
                    case VodAction.ACTION_REPLAY:
                        // 控制指令重唱操作
                        break;
                    case VodAction.ACTION_TRACK_CHANGE:
                        // 控制指令原伴唱切换
                        break;
                    case VodAction.ACTION_STATE_CHANGE:
                        // 控制指令切换歌曲播放状态
                        break;
                    case VodAction.ACTION_VOL_UP:
                        // 控制指令增加音量
                        break;
                    case VodAction.ACTION_VOL_DOWN:
                        // 控制指令减少音量
                        break;
                }
            }
        }
    };

    public RnUtilsModule(ReactApplicationContext reactContext) {
        super(reactContext);
        this.reactContext = reactContext;
        // 创建一个 BroadcastReceiver 来监听 SD 卡插入事件
        BroadcastReceiver receiver = new BroadcastReceiver() {
            @Override
            public void onReceive(Context context, Intent intent) {
                WritableMap params = Arguments.createMap();
                if (intent.getAction().equals(Intent.ACTION_MEDIA_MOUNTED)) {
                    // SD 卡插入
                    Log.d("SDCardReceiver", "TF 卡已插入");
                    String path = intent.getDataString();
                    String pathString = path.split("file://")[1];// U盘路径
                    Log.e("TAG", "U盘插入" + pathString);
                    Log.e("getExternalPath--", pathString);
                    params.putBoolean("status", true);
                    params.putString("path", pathString);
                } else if (intent.getAction().equals(Intent.ACTION_MEDIA_EJECT)) {
                    Log.d("SDCardReceiver", "TF 卡已拔出");
                    params.putBoolean("status", false);
                }
                sendEvent("sdCardChange", params);
            }
        };
        BroadcastReceiver voiceReceiver = new BroadcastReceiver() {
            @Override
            public void onReceive(Context context, Intent intent) {
                if (intent.getAction().equals(VOICE_ACTION)) {
                    WritableMap params = Arguments.createMap();
                    String url = intent.getStringExtra("uri");
                    Uri uri = Uri.parse(url);
                    if (uri.getScheme().equals("leishikge")) {
                        String action = uri.getQueryParameter("action");
                        params.putString("action", action);
                        Set<String> parameterNames = uri.getQueryParameterNames();
                        if (parameterNames.contains("m0")) {
                            params.putString("m0", uri.getQueryParameter("m0"));
                        }
                        if (parameterNames.contains("m1")) {
                            params.putString("m1", uri.getQueryParameter("m1"));
                        }
                        sendEvent("voiceEvent", params);
                    }
                }
            }
        };
        // 注册 BroadcastReceiver
        IntentFilter filter = new IntentFilter();
        filter.addAction(Intent.ACTION_MEDIA_MOUNTED);
        filter.addAction(Intent.ACTION_MEDIA_EJECT);
        filter.addDataScheme("file");
        IntentFilter voiceFilter = new IntentFilter(VOICE_ACTION);
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.TIRAMISU) {
            reactContext.registerReceiver(receiver, filter, Context.RECEIVER_EXPORTED);
            reactContext.registerReceiver(voiceReceiver, voiceFilter, Context.RECEIVER_EXPORTED);

        } else {
            reactContext.registerReceiver(receiver, filter);
            reactContext.registerReceiver(voiceReceiver, voiceFilter);

        }
    }

    @ReactMethod
    public void initComplete() {
        if (m1 != null) {
            WritableMap params = Arguments.createMap();
            params.putString("action", "order_song");
            params.putString("m0", m0);
            params.putString("m1", m1);
            sendEvent("voiceEvent", params);
        }
    }

    @ReactMethod
    public void addListener(String eventName) {
        // Set up any upstream listeners or background tasks as necessary
    }

    @ReactMethod
    public void removeListeners(Integer count) {
        // Remove upstream listeners, stop unnecessary background tasks
    }

    // 发送事件到 JavaScript 侧
    private void sendEvent(String eventName, @Nullable WritableMap params) {
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit(eventName, params);
    }

    @Override
    public String getName() {
        return "RnUtilsModule";
    }

    @ReactMethod
    public void getSDCardPath(Promise promise) {
        StorageManager storageManager = (StorageManager) getReactApplicationContext()
                .getSystemService(Context.STORAGE_SERVICE);
        // 获取所有挂载的存储设备
        String path = null;
        WritableArray pathArray = Arguments.createArray();
        try {
            Class<?>[] parameterTypes = {};
            Method getVolumePathsMethod = StorageManager.class.getMethod("getVolumePaths", parameterTypes);
            Method getVolumeState = StorageManager.class.getMethod("getVolumeState", String.class);
            Object[] parameters = {};
            String[] paths = (String[]) getVolumePathsMethod.invoke(storageManager, parameters);
            // second element in paths[] is secondary storage path
            // 遍历存储设备，查找外置 USB 存储设备
            for (int i = 1; i < paths.length; i++) {
                String state = (String) getVolumeState.invoke(storageManager, paths[i]);
                if (state.equals(Environment.MEDIA_MOUNTED)) {
                    path = paths[i];
                    pathArray.pushString(path);
                }
            }
        } catch (Exception e) {

        }
        Log.e("getExternalPath----", "getExternalPath----" + path);
        promise.resolve(pathArray);

    }

    @ReactMethod
    public void getSDCardPathSpace(String path, Promise promise) {
        StatFs statFs = new StatFs(path);
        // 获取每个块的大小和可用块的数量
        long blockSize = statFs.getBlockSizeLong();
        long availableBlocks = statFs.getAvailableBlocksLong();
        promise.resolve(Long.toString(blockSize * availableBlocks));
    }

    @ReactMethod
    public void downloadDecryptAndSave(String urlString, Promise promise) {
        new Thread(new Runnable() {
            @Override
            public void run() {
                try {
                    // URL url = new URL(urlString);
                    String fileName = urlString.substring(urlString.lastIndexOf('/') + 1);
                    // String md_key = fileName.substring(0, fileName.lastIndexOf('.'));
                    byte[] md5Key = md5(fileName);
                    // HttpURLConnection connection = (HttpURLConnection) url.openConnection();
                    // InputStream input = connection.getInputStream();
                    InputStream input = new FileInputStream(new File(urlString));

                    // byte[] buffer = new byte[1024];
                    // int bytesRead;
                    // ByteArrayOutputStream baos = new ByteArrayOutputStream();

                    // while ((bytesRead = input.read(buffer)) != -1) {
                    // baos.write(buffer, 0, bytesRead);
                    // }
                    // input.close();
                    // byte[] encryptedData = baos.toByteArray();

                    // 设置解密模式和密钥
                    Cipher cipher = Cipher.getInstance("AES/ECB/NoPadding");
                    SecretKeySpec secretKey = new SecretKeySpec(md5Key, "AES");
                    cipher.init(Cipher.DECRYPT_MODE, secretKey);

                    // 解密操作
                    // byte[] decryptedPaddedData = cipher.doFinal(encryptedData);
                    // byte[] decryptedData = removePadding(decryptedPaddedData); //
                    // 使用新的removePadding方法
                    // 创建目录并保存文件
                    // File targetFile = new File(reactContext.getExternalFilesDir(null), "jiemi");
                    File targetFile = new File(reactContext.getFilesDir(), "temp");

                    // File directory =
                    // Environment.getExternalStoragePublicDirectory(Environment.DIRECTORY_MOVIES);
                    // File targetFile = new File(directory, "jiemi");
                    if (!targetFile.exists()) {
                        targetFile.mkdirs();
                    }

                    // File outputFile = new File(targetFile, fileName);
                    // try (FileOutputStream output = new FileOutputStream(outputFile)) {
                    // output.write(decryptedData);
                    // }

                    // File outputFile = new File(targetFile, fileName);
                    File outputFile = File.createTempFile("xxx", "");
                    try (FileOutputStream output = new FileOutputStream(outputFile)) {
                        byte[] buffer = new byte[1024 * 1024 * 5]; // 加密块的大小 可以改2048 4096 这种
                        int bytesRead;

                        while ((bytesRead = input.read(buffer)) != -1) {
                            byte[] decryptedBlock = cipher.update(buffer, 0, bytesRead);
                            if (decryptedBlock != null) {
                                output.write(decryptedBlock);
                                output.flush();
                            }
                        }

                        byte[] finalBlock = cipher.doFinal();
                        if (finalBlock != null) {
                            output.write(finalBlock);
                            output.flush();
                        }
                        output.close();
                        input.close();
                    }

                    promise.resolve(outputFile.getAbsolutePath());

                } catch (Exception e) {
                    promise.reject("ERROR", "An error occurred", e);
                }
            }
        }).start();
    }

    private byte[] md5(String s) throws Exception {
        MessageDigest digest = MessageDigest.getInstance("MD5");
        digest.update(s.getBytes());
        // byte[] hash = digest.digest();
        return digest.digest();
    }

    @ReactMethod
    public void hideNavigationBar(boolean status) {
        Activity activity = getReactApplicationContext().getCurrentActivity();
        if (activity == null) {
            return;
        }

        Window window = activity.getWindow();
        View decorView = window.getDecorView();
        int uiOptions;
        if (status) {
            uiOptions = View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
                    | View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY;
        } else {
            uiOptions = View.SYSTEM_UI_FLAG_VISIBLE;
        }
        activity.runOnUiThread(new Runnable() {
            public void run() {
                decorView.setSystemUiVisibility(uiOptions);
            }
        });
    }

    @ReactMethod
    public void hideSystemVolume() {
        AudioManager audioManager = (AudioManager) getReactApplicationContext().getSystemService(Context.AUDIO_SERVICE);
        if (audioManager != null) {
            audioManager.setStreamVolume(AudioManager.STREAM_MUSIC, 0, 0);
        }
    }

    @ReactMethod
    public void toPinyinInitials(String chinese, Promise promise) {
        new Thread(new Runnable() {
            @Override
            public void run() {
                StringBuilder initials = new StringBuilder();
                char[] chars = chinese.toCharArray();

                for (char ch : chars) {
                    try {
                        String[] pinyinArray = PinyinHelper.toHanyuPinyinStringArray(ch);
                        // 取第一个读音的首字母
                        if (pinyinArray != null && pinyinArray.length > 0) {
                            initials.append(pinyinArray[0].charAt(0));
                        } else {
                            initials.append(ch);
                        }
                    } catch (Exception e) {
                        initials.append(ch);
                    }
                }
                promise.resolve(initials.toString());

            }
        }).start();

    }

    @ReactMethod
    public void moveFile(String dir, String fileName, Promise promise) {
        Context context = getReactApplicationContext();
        try {
            // 确保目录存在
            File directory = new File(context.getExternalFilesDir(null), dir);
            if (!directory.exists()) {
                directory.mkdirs();
            }

            // 设置目标文件路径
            File outFile = new File(directory, fileName);

            // 如果文件已存在，直接返回，不再执行复制
            if (outFile.exists()) {
                promise.resolve(outFile.getAbsolutePath());
                return;
            }

            // 获取assets中的文件
            InputStream in = context.getAssets().open(fileName);

            // 执行文件复制
            OutputStream out = new FileOutputStream(outFile);
            byte[] buffer = new byte[1024];
            int read;
            while ((read = in.read(buffer)) != -1) {
                out.write(buffer, 0, read);
            }
            in.close();
            out.flush();
            out.close();
            promise.resolve(outFile.getAbsolutePath());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public String getMacAddress() {
        WifiManager wifiManager = (WifiManager) getReactApplicationContext().getSystemService(Context.WIFI_SERVICE);
        WifiInfo wifiInfo = wifiManager.getConnectionInfo();
        String macAddress = wifiInfo == null ? null : wifiInfo.getMacAddress();
        return macAddress;
    }

    public boolean isStringEmpty(String str) {
        return str == null || str.trim().isEmpty();
    }

    /**
     * 获取mac地址
     *
     * @return
     */
    @ReactMethod
    public void getMac(Promise promise) {
        String macAddress = null;
         String path = "/sys/class/net/wlan0/address";
        StringBuilder macAddressBuilder = new StringBuilder();
        BufferedReader reader = null;
        try {
            reader = new BufferedReader(new FileReader(path));
            String line;
            while ((line = reader.readLine()) != null) {
                macAddressBuilder.append(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (reader != null) {
                try {
                    reader.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
        macAddress = macAddressBuilder.toString();
        Log.d(TAG, macAddress + "--------------");
        if (isStringEmpty(macAddress)) {
            macAddress = getMacAddress();
        }
        promise.resolve(macAddress);
    }

    @ReactMethod
    public void initPlayerSdk(String sn, Promise promise) {
        Config.getSdkConfig().setLogLevel(1).setHttpTimeout(60, 60, 60);
        Config.getSdkConfig().setDeviceType(1);
        // 初始化创建的播放器类型
        FactoryMediaPlayer.getInstance().initPlayer(getReactApplicationContext(), FactoryMediaPlayer.PLAYER_IJK, sn,
                vodCallback, new InitPlayerCallback() {
                    @Override
                    public void onComplete() {
                        Log.d(TAG, "initPlayer = success");
                    }

                    @Override
                    public void onError(int errorCodeType, int errorCode, String errorMsg) {
                        Log.d(TAG, "onError: errorCodeType =" + errorCodeType + " errorCode = " + errorCode
                                + " errorMsg=" + errorMsg);
                    }

                    @Override
                    public void reInitComplete() {
                    }
                });
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/RnUtilsPackage.java

```
package com.thunder.ktvplayer;
import com.facebook.react.ReactPackage;
import com.facebook.react.bridge.NativeModule;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.uimanager.ViewManager;
import com.thunder.ktvplayer.video.ReactTdplayerViewManager;
import com.thunder.ktvplayer.VideoManagerModule;
import com.thunder.ktvplayer.DownloadSongModule;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class RnUtilsPackage implements ReactPackage {

    @Override
    public List<ViewManager> createViewManagers(ReactApplicationContext reactContext) {
         List<ViewManager> modules = new ArrayList<>();
                modules.add(new HandwritingViewManager());
                modules.add(new ReactTdplayerViewManager());
                return modules;
    }

    @Override
    public List<NativeModule> createNativeModules(
            ReactApplicationContext reactContext) {
        List<NativeModule> modules = new ArrayList<>();

        modules.add(new RnUtilsModule(reactContext));
        modules.add(new RnXiaoAiModule(reactContext));
        modules.add(new VideoManagerModule(reactContext));
        modules.add(new DownloadSongModule(reactContext));
        return modules;
    }

}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/RnXiaoAiModule.java

```
package com.thunder.ktvplayer;

import android.util.Log;
import android.os.Handler;
import android.os.HandlerThread;
import android.os.Looper;
import android.os.CountDownTimer;
import android.os.Message;
import android.os.Build;
import android.content.Context;
import android.content.BroadcastReceiver;
import android.content.Intent;
import android.content.IntentFilter;
import android.net.Uri;
import javax.annotation.Nullable;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.bridge.ReactContextBaseJavaModule;
import myaudiorecord.RecordStream.RecorderXiaoAIOutputStream;
import com.facebook.react.bridge.ReactMethod;
import java.io.IOException;
import com.thunder.miaimedia.actionresponse.action.LightAction;
import com.thunder.miaimedia.recoder.RecorderData;
import com.thunder.plugin.MiBrainPlugin;
import com.thunder.plugin.MiPluginParam;
import com.thunder.plugin.XiaoAISkillConstant;
import com.facebook.react.bridge.Arguments;
import com.facebook.react.modules.core.DeviceEventManagerModule;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.bridge.Arguments;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;
import android.media.AudioManager;

public class RnXiaoAiModule extends ReactContextBaseJavaModule implements MiBrainPlugin.IClient4App {
    private static final String TAG = "RnXiaoAiModule";
    private static final String VOICE_ACTION = "com.thunder.ktvplayer.VOICE_ACTION";
    private final ReactApplicationContext reactContext;
    private EventHandler handler;
    private static HandlerThread handlerThread;
    private final static int EVENT_HIDE_TEXT = 1;
    private final Lock lock = new ReentrantLock();
    private boolean isAsring = false;
    private boolean networkStatus = true;
    private RecorderXiaoAIOutputStream xiaoAIWakeupOutputStream;
    private CountDownTimer timer;
    private String company = null;

    private class EventHandler extends Handler {
        public EventHandler(Looper looper) {
            super(looper);
        }

        @Override
        public void handleMessage(Message msg) {
            switch (msg.what) {
                case EVENT_HIDE_TEXT:
                    Log.d(TAG, " EVENT_HIDE_TEXT ");
                    // TODO 隐藏OSD小爱显示
                    // TVXiaoAI.getIstance().hide();
                    if (!isAsring) {
                        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                                .emit("doSpeakShow", "");
                        // startWakeup();
                    }
                    break;
            }
        }
    }

    public RnXiaoAiModule(ReactApplicationContext reactContext) {
        super(reactContext);
        this.reactContext = reactContext;
        BroadcastReceiver voiceReceiver = new BroadcastReceiver() {
            @Override
            public void onReceive(Context context, Intent intent) {
                if (intent.getAction().equals(VOICE_ACTION)) {
                    String url = intent.getStringExtra("uri");
                    Uri uri = Uri.parse(url);
                    if (uri.getScheme().equals("leishikge")) {
                        String action = uri.getQueryParameter("action");
                        if (action.equals("record_start")) {
                            miAiManualWakeUp();
                        } else if (action.equals("record_stop")) {
                            miAiStopSpeech();

                        }
                    }
                }
            }
        };
        IntentFilter voiceFilter = new IntentFilter(VOICE_ACTION);
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.TIRAMISU) {
            reactContext.registerReceiver(voiceReceiver, voiceFilter, Context.RECEIVER_EXPORTED);
        } else {
            reactContext.registerReceiver(voiceReceiver, voiceFilter);
        }
        if (handlerThread == null) {
            handlerThread = new HandlerThread("XIAOAI_TVSHOW");
            handlerThread.start();
        }
        handler = new EventHandler(handlerThread.getLooper());
    }

    @Override
    public String getName() {
        return "RnXiaoAiModule";
    }

    /**
     * 启动小爱操作
     */
    @ReactMethod
    public void initMiAi(String company) {
        this.company = company;
        startXiaoAiWakeup();
        init(false, "192.168.3.201", false);
    }
    @ReactMethod
    public void networkChange(boolean state) {
        networkStatus = state;
    }
    public void miAiManualWakeUp() {
        if(networkStatus) {
            miAiStopSpeech();
            try {
                xiaoAIWakeupOutputStream.open(null);
            } catch (IOException e) {
                e.printStackTrace();
            }
            MiBrainPlugin.getInstance().miAiStopSpeech();
            MiBrainPlugin.getInstance().miAiManualWakeUp();
            isAsring = true;
            getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                    .emit("onAsr", "start");
        } else {
            getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                        .emit("doSpeakShow", "网络出错啦，小爱需要网络正常才能给您更好的体验呢");
            timer = new CountDownTimer(3000, 1000) {
                @Override
                public void onTick(long millisUntilFinished) {

                }
                @Override
                public void onFinish() {
                    // 3 秒后触发
                    getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                                            .emit("doSpeakShow", "");
                    if (timer != null) {
                        timer.cancel();
                    }
                }
            }.start();
        }
    }

    public void miAiStopSpeech() {
        // MiBrainPlugin.getInstance().miAiStopSpeech();
        try {
            xiaoAIWakeupOutputStream.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    /**
     * 小爱初始化动作
     *
     * @param isOauth       是否是MIOT场景。非特殊情况，false
     * @param localServerIp MIOT场景下需要提供服务地址
     * @param isDebug       是否是debug模式，日志debug
     */
    public void init(boolean isOauth, String localServerIp, boolean isDebug) {
        // 设置Action监听
        MiBrainPlugin.getInstance().setIClient4App(this);
        // 设置默认参数
        // MiBrainPlugin.getInstance().miAiTtsPcmVol(100);
        MiPluginParam param = MiPluginParam.getInstance();
        // TODO 设置mac地址
        String mac = "";
        param.setDeviceMac(mac);
        Log.d(TAG, " initMiXiaoAi device mac =  " + mac);
        Log.d(TAG, " initMiXiaoAi server ip =  " + localServerIp);
        Log.d(TAG, " initMiXiaoAi isOauth  =  " + isOauth);
        // if (StringUtils.isNotEmpty(mac) || StringUtils.isNotEmpty(localServerIp)) {
        // try {
        // throw new Exception(" MiBrainPlugin init Fail !!! mac or ip is null ; mac ="
        // + mac + "; serverIp =" + localServerIp);
        // } catch (Exception e) {
        // e.printStackTrace();
        // }
        // }

        param.setOauth(isOauth);
        param.setServerIp(localServerIp);
        param.setDebug(isDebug);

        // TODO 小爱初始化参数依据实际情况设置
        MiBrainPlugin.getInstance().setParamData(param);
        // 录音初始化
        RecorderData.getInstance().init();
        // TODO 启动音频数据传输
        // AudioRecorder.getIstance().setXiaoAiInitOver(true);
        // 启动小爱
        try {
            MiBrainPlugin.getInstance().init(getReactApplicationContext(), new MiBrainPlugin.AiEngineCallBack() {
                @Override
                public void initSuccess() {
                    Log.d(TAG, " ======> Mi AI initSuccess");
                    HandlerThread handlerThread = new HandlerThread("setMiAIEnableWakeUp");
                    handlerThread.start();
                    new Handler(handlerThread.getLooper()).postDelayed(new Runnable() {
                        @Override
                        public void run() {
                            setMiAIEnableWakeUp(true);
                        }
                    }, 500);
                }

                @Override
                public void initFail(int errorCode, String msg) {
                    Log.d(TAG, " ======> Mi AI initFail");
                }
            }, isDebug);
        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    /**
     * 延迟时间后，发送消息， 用于自己隐藏OSD小爱显示
     *
     * @param delayTime
     */
    private void resetMessageDelayClearTVShow(long delayTime) {
        Log.d(TAG, " resetMessageDelayClearTVShow   delayTime =  " + delayTime);
        if (handler.hasMessages(EVENT_HIDE_TEXT)) {
            handler.removeMessages(EVENT_HIDE_TEXT);

        }
        // TODO 小爱还原音量大小。
        if (delayTime > 0) {
            handler.sendEmptyMessageDelayed(EVENT_HIDE_TEXT, delayTime);
        }
    }

    /**
     * 小爱播报显示
     *
     * @param display 显示内容
     */
    public void doSpeakShow(String display) {
        doSpeakShow(display, true, true, MiBrainPlugin.XIAOAI_SHOW_TIME.DEFUALT_SHOWTIME, 1);
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit("doSpeakShow", display);
    }

    /**
     * 小爱播报显示
     * ps: 只负责播报，显示部分自己实现。
     *
     * @param display    显示内容
     * @param needSpeak  是否播报
     * @param showTime   是否展示
     * @param repeatTime 重复次数
     */
    public void doSpeakShow(String display, boolean needSpeak, boolean needShow, long showTime, int repeatTime) {
        Log.d(TAG, " doSpeakShow  display = " + display + "; needSpeak =" + needSpeak + "; showTime =" + showTime);
        lock.lock();
        // TODO 根据播放器你音量设置小爱tts播报音量. 0 ~ 1.0
        MiBrainPlugin.getInstance().miAiVol(100);
        try {
            MiBrainPlugin.getInstance().miAiSpeakContent(removeErrorCode(display), needSpeak, showTime, repeatTime);
        } finally {
            lock.unlock();
        }

        resetMessageDelayClearTVShow(showTime);
    }

    /**
     * 小爱错误信息会在文字末尾携带如<-23>内容。播报时需要移除
     *
     * @param display
     * @return
     */
    private String removeErrorCode(String display) {
        String result = display.replaceAll("<[^>]*>", "");
        return result;
    }

    /**
     * 是否可以唤醒
     *
     * @param needWakeUp
     */
    public void setMiAIEnableWakeUp(boolean needWakeUp) {
        if (needWakeUp) {
            MiBrainPlugin.getInstance().enableXiaoAiWakeup();
        } else {
            MiBrainPlugin.getInstance().unEnableXiaoAiWakeup();
        }
    }

    public void startXiaoAiWakeup() {
        AudioManager audioManager = (AudioManager) getReactApplicationContext().getSystemService(Context.AUDIO_SERVICE);
        audioManager.setMode(AudioManager.MODE_IN_COMMUNICATION);
        audioManager.setSpeakerphoneOn(true);
        xiaoAIWakeupOutputStream = new RecorderXiaoAIOutputStream();
        if(company.equals("dangbei")) {
            try {
                xiaoAIWakeupOutputStream.open(null);
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }

    // 发送事件到 JavaScript 侧
    private void sendEvent(String eventName, @Nullable WritableMap map) {
        WritableMap writableMap = Arguments.createMap();
        writableMap.putString("type", eventName);
        if (map != null) {
            writableMap.putMap("params", map);
        }
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit("xiaoAiEvent", writableMap);
    }

    @Override
    public void doNext() {
        Log.d(TAG, " xiaoAI action doNext");
        doSpeakShow("为您切换下一首");
        sendEvent("doNext", null);
    }

    @Override
    public void doPause() {
        Log.d(TAG, " xiaoAI action doPause");
        doSpeakShow("已为您暂停播放");
        sendEvent("doPause", null);
    }

    @Override
    public void doPlay() {
        Log.d(TAG, " xiaoAI action doPlay");
        doSpeakShow("已为您开始播放");
        sendEvent("doPlay", null);
    }

    @Override
    public void doMute() {
        Log.d(TAG, " xiaoAI action doMute");
        doSpeakShow("已为您静音");
        sendEvent("doMute", null);
    }

    @Override
    public void doRecovery() {
        Log.d(TAG, " xiaoAI action doRecovery");
        doSpeakShow("已为您开启声音");
        sendEvent("doRecovery", null);
    }

    @Override
    public void doReplay() {
        Log.d(TAG, " xiaoAI action doReplay");
        doSpeakShow("已为您重唱");
        sendEvent("doReplay", null);
    }

    @Override
    public void doOriginal() {
        Log.d(TAG, " xiaoAI action doOriginal");
        doSpeakShow("已为您切换原唱");
        sendEvent("doOriginal", null);
    }

    @Override
    public void doAccompany() {
        Log.d(TAG, " xiaoAI action doAccompany");
        doSpeakShow("已为您切换伴唱");
        sendEvent("doAccompany", null);
    }

    @Override
    public int doTuneUp() {
        Log.d(TAG, " xiaoAI action doTuneUp");

        return 0;
    }

    @Override
    public int doTuneDown() {
        Log.d(TAG, " xiaoAI action doTuneDown");

        return 0;
    }

    @Override
    public int doBGMUp() {
        Log.d(TAG, " xiaoAI action doBGMUp");
        doSpeakShow("音量升高");
        sendEvent("doBGMUp", null);

        return 0;
    }

    @Override
    public int doBGMDown() {
        Log.d(TAG, " xiaoAI action doBGMDown");
        doSpeakShow("音量降低");
        sendEvent("doBGMDown", null);
        return 0;
    }

    @Override
    public int setVolume(final int volume) {
        WritableMap params = Arguments.createMap();
        params.putInt("volume", volume);
        Log.d(TAG, "xiaoAI action setVolume  volume = " + volume);
        doSpeakShow("设置音量为" + volume);
        sendEvent("setVolume", params);
        return volume;
    }

    @Override
    public void addSong(final String mediaName, final String mediaSerialNo, final String starName) {
        WritableMap params = Arguments.createMap();
        Log.d(TAG, " xiaoAI action addSong mediaName = " + mediaName + " ; mediaSerialNo = " + mediaSerialNo);
        doSpeakShow("为您添加" + starName + "的" + mediaName);
        params.putString("mediaName", mediaName);
        params.putString("mediaSerialNo", mediaSerialNo);
        params.putString("starName", starName);
        params.putString("type", "addSong");
        sendEvent("addSong", params);
    }

    @Override
    public boolean topSong() {
        Log.d(TAG, " xiaoAI action topSong ");
        doSpeakShow("歌曲置顶");
        sendEvent("topSong", null);
        return true;
    }

    @Override
    public void doXiaoAiPlayStart(String speak, long showTime) {
        Log.d(TAG, " xiaoai start speek ");
        // TODO 实现自己的播放器音量降低
        sendEvent("doXiaoAiPlayStart", null);
    }

    @Override
    public void doXiaoAiPlayStop() {
        Log.d(TAG, " xiaoai Stop speek ");
        // TODO 实现自己的播放器音量还原
        sendEvent("doXiaoAiPlayStop", null);
    }

    @Override
    public void updateLightOper(final String lightOper) {
        Log.d(TAG, " xiaoAI action updateLightOper light = " + lightOper);
        String displayText = "";
        switch (lightOper) {
            case XiaoAISkillConstant.LightAction.LIGHT_CHANGE: {
                displayText = LightAction.LIGHT_CHANGE_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_SOFT: {
                displayText = LightAction.LIGHT_SOFT_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_LYRIC: {
                displayText = LightAction.LIGHT_LYRIC_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_DYNAMIC: {
                displayText = LightAction.LIGHT_DYNAMIC_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_BRIGHT: {
                displayText = LightAction.LIGHT_BRIGHT_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_SAD_TWO:
            case XiaoAISkillConstant.LightAction.LIGHT_SAD: {
                displayText = LightAction.LIGHT_SAD_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_ARTISTIC_TWO:
            case XiaoAISkillConstant.LightAction.LIGHT_ARTISTIC: {
                displayText = LightAction.LIGHT_ARTISTIC_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_HAZY_TWO:
            case XiaoAISkillConstant.LightAction.LIGHT_HAZY: {
                displayText = LightAction.LIGHT_HAZY_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_SLOW_ROCK_TWO:
            case XiaoAISkillConstant.LightAction.LIGHT_SLOW_ROCK: {
                displayText = LightAction.LIGHT_SLOW_ROCK_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_BACK:
            case XiaoAISkillConstant.LightAction.Go_BACK: {
                displayText = LightAction.LIGHT_BACK_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHTDOWN:
            case XiaoAISkillConstant.LightAction.LIGHT_TURN_OFF: {
                displayText = LightAction.LIGHTDOWN_TEXT;
                break;
            }
            case XiaoAISkillConstant.LightAction.LIGHT_TURN_ON: {
                displayText = LightAction.LIGHT_TURN_ON_TEXT;
                break;
            }
            default:
                return;
        }
        doSpeakShow(displayText);
    }

    @Override
    public void updateAirPurifier(String display, boolean open) {
        Log.d(TAG, " xiaoAI action updateAirPurifier  open = " + open);
        doSpeakShow(display);
    }

    @Override
    public int doMicUp() {
        Log.d(TAG, "  doMicUp ");
        doSpeakShow("麦克音量+");
        sendEvent("doMicUp", null);
        return 0;
    }

    @Override
    public int doMicDown() {
        Log.d(TAG, "  doMicDown ");
        doSpeakShow("麦克音量-");
        sendEvent("doMicDown", null);
        return 0;
    }

    @Override
    public void onSpeechErr(String error, int errorCode) {
        isAsring = false;
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit("onAsr", "end");
        Log.d(TAG, "  onSpeechErr  error = " + error + "; errorCode " + errorCode);
        doSpeakShow(error);
    }

    @Override
    public void onNlpDealFail(String error, String key) {
        Log.d(TAG, "  onNlpDealFail  error = " + error + "; key " + key);
        doSpeakShow(error);
    }

    @Override
    public void onMiChat(String result) {
        Log.d(TAG, "  onMiChat  result " + result);
        String temp = (result.replaceAll("＂", "")).trim();
        doSpeakShow(temp);
    }

    @Override
    public void onHelp() {
        Log.d(TAG, "  onHelp  ");
        doSpeakShow("help");
    }

    @Override
    public void doGotoBroadcast() {
        Log.d(TAG, " xiaoai  doGotoBroadcast");
        // doSpeakShow("已为您切换到大厅转播");
    }

    @Override
    public void onStation(String url, String starName, String mediaName) {
        doSpeakShow("为您播放" + starName + "的" + mediaName);
    }

    @Override
    public void whereIsMe() {
        Log.d(TAG, " xiaoai  whereIsMe");
    }

    @Override
    public void controlAirConditioner(final boolean open) {
        Log.d(TAG, " xiaoAI action controlAirConditioner  open = " + open);
    }

    /**
     * 呼叫/取消呼叫 服务生
     *
     * @param action true 呼叫； false 取消呼叫
     * @return
     */
    @Override
    public boolean doCallWaiter(boolean action) {
        Log.d(TAG, " doCallWaiter == > " + action);
        return true;
    }

    /**
     * 模式变更
     *
     * @param mode @{@link XiaoAISkillConstant.PatternAction}
     */
    @Override
    public void doChangePatternMode(String mode) {
        Log.d(TAG, " doChangePatternMode == > " + mode);
    }

    public static final String TXT_CALLWAITER = "需要服务生为您做什么？";
    public static final String TXT_CALLWAITER_END = "已为您呼叫，服务生正快马加鞭赶来，稍等一下哦！";

    @Deprecated
    @Override
    public void doHummingSong() {

    }

    @Override
    public void doFunctionControl(String functionKey) {
        Log.d(TAG, " xiaoAI action doFunctionControl  functionKey = " + functionKey);
        try {
            String diplayText = "";
            switch (functionKey) {
                case XiaoAISkillConstant.FunctionControlAction.CLOSE_TV_SCREEN:
                    diplayText = "开启息屏";
                    break;
                case XiaoAISkillConstant.FunctionControlAction.OPEN_TV_SCREEN:
                    diplayText = "关闭息屏";
                    break;
                case XiaoAISkillConstant.FunctionControlAction.OPEN_SCORE:
                    diplayText = "开启评分";
                    break;
                case XiaoAISkillConstant.FunctionControlAction.CLOSE_SCORE:
                    diplayText = "关闭评分";
                    break;
            }
            doSpeakShow(diplayText);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    @Override
    public void doListSelect(int num) {
        Log.d(TAG, " xiaoAI action doListSelect  num = " + num);
        // TODO 列表选择返回的index
    }

    @Override
    public void doListRefresh() {
        Log.d(TAG, " xiaoAI action doListRefresh ");
        // TODO 列表刷新
    }

    @Override
    public void doFusionChange(String model) {
        Log.d(TAG, " xiaoAI action doFusionChange  model = " + model);
        // TODO 巨幕融合，切换场景
    }

    @Override
    public void doGoodsDistribute(String goods, int count) {
        Log.d(TAG, " xiaoAI action doGoodsDistribute  goods = " + goods + "; count " + count);
        // TODO xiaoai 小爱技能实现，服务生配送功能，前提需要小爱呼叫服务生。

    }

    /**
     * 唤醒回调
     *
     * @param wakeType 唤醒类型
     */
    @Override
    public void onWakeUpSpeak(int wakeType) { // 唤醒第一步回调到这
        Log.d(TAG, " onWakeUpSpeak  wakeType =" + wakeType);
        boolean speak = false;
        boolean display = false;
        switch (wakeType) {
            case MiBrainPlugin.XIAOAI_WAKE_TYPE.WAKE_UP_VOICE:
                speak = true;
                display = true;
                break;
            case MiBrainPlugin.XIAOAI_WAKE_TYPE.WAKE_UP_MIC:
                speak = true;
                display = true;
                break;
            case MiBrainPlugin.XIAOAI_WAKE_TYPE.WAKE_UP_MANUAL:
            case MiBrainPlugin.XIAOAI_WAKE_TYPE.WAKE_TYPE_FOLLOW_SKILL:
                speak = false;
                display = false;
                break;
        }
        if(company.equals("dangbei")) {
            int wakeTextIndex = (int) (Math.random() * MiBrainPlugin.wakeText.length);
            doSpeakShow(MiBrainPlugin.wakeText[wakeTextIndex]);
        }
        MiBrainPlugin.getInstance().miAiStartSpeech(wakeType);
    }

    /**
     * 识别开始
     */
    @Override
    public void onAsrBegin() {
        Log.d(TAG, " onAsrBegin ==>  ");
        if(company.equals("dangbei")) {
            isAsring = true;
            getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                            .emit("onAsr", "start");
        }
    }

    @Override
    public void onAsrContent(String content) {
        WritableMap params = Arguments.createMap();
        params.putString("value", content);
        Log.d(TAG, " onAsrContent ==>  " + content);
        if (content != null && !content.trim().isEmpty()) {
            getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                    .emit("doSpeakShow", content);
        }

        sendEvent("content", params);
    }

    @Override
    public void onAsrOver() {
        Log.d(TAG, " onAsrOver  ");
        isAsring = false;
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit("onAsr", "end");
    }

    @Override
    public void setSpeakTimbre(boolean mm) {
        MiPluginParam.getInstance().setFemaleVoice(mm);
    }

    @Override
    public void resetSpeakState() {
        Log.d(TAG, " resetSpeakState ");
        isAsring = false;
        getReactApplicationContext().getJSModule(DeviceEventManagerModule.RCTDeviceEventEmitter.class)
                .emit("onAsr", "end");
    }

    @ReactMethod
    public void addListener(String eventName) {

    }

    @ReactMethod
    public void removeListeners(Integer count) {

    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/VideoManagerModule.java

```
package com.thunder.ktvplayer;

import com.thunder.ktvplayer.video.ReactTdplayerView;
import com.facebook.react.bridge.Promise;
import com.facebook.react.bridge.ReactApplicationContext;
import com.facebook.react.bridge.ReactContextBaseJavaModule;
import com.facebook.react.bridge.ReactMethod;
import com.facebook.react.bridge.ReadableMap;
import com.facebook.react.bridge.UiThreadUtil;
import com.facebook.react.uimanager.UIManagerHelper;
import com.facebook.react.uimanager.common.UIManagerType;
import com.facebook.react.uimanager.UIManagerModule;
import android.view.View;

class VideoManagerModule extends ReactContextBaseJavaModule {
    private final ReactApplicationContext reactContext;
    @Override
    public String getName() {
        return "VideoManagerModule";
    }
    public VideoManagerModule (ReactApplicationContext reactContext) {
        super(reactContext);
        this.reactContext = reactContext;
    }
    private void performOnPlayerView(int reactTag, Callback callback) {
        UiThreadUtil.runOnUiThread(new Runnable() {
            @Override
            public void run() {
                try {
                    UIManagerModule uiManager = reactContext.getNativeModule(UIManagerModule.class);;

                    View view = uiManager.resolveView(reactTag);

                    if (view instanceof ReactTdplayerView) {
                        callback.onResult((ReactTdplayerView) view);
                    } else {
                        callback.onResult(null);
                    }
                } catch (Exception e) {
                    callback.onResult(null);
                }
            }
        });
    }

    public interface Callback {
        void onResult(ReactTdplayerView view);
    }
    @ReactMethod
    public void setPlayerPauseState(boolean paused, int reactTag) {
        performOnPlayerView(reactTag, new Callback() {
            @Override
            public void onResult(ReactTdplayerView view) {
                if (view != null) {
                    view.setPausedModifier(paused);
                }
            }
        });
    }
    @ReactMethod
    public void reset(int reactTag) {
        performOnPlayerView(reactTag, new Callback() {
            @Override
            public void onResult(ReactTdplayerView view) {
                if (view != null) {
                    view.reset();
                }
            }
        });
    }
    @ReactMethod
    public void resume(int reactTag) {
        performOnPlayerView(reactTag, new Callback() {
            @Override
            public void onResult(ReactTdplayerView view) {
                if (view != null) {
                    view.resume();
                }
            }
        });
    }
    @ReactMethod
    public void setSelectedAudioTrack(int trackIndex, int reactTag) {
        performOnPlayerView(reactTag, new Callback() {
            @Override
            public void onResult(ReactTdplayerView view) {
                if (view != null) {
                    view.setSelectedAudioTrack(trackIndex);
                }
            }
        });
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/CustomMarqueeTextAdapter.java

```
package com.thunder.ktvplayer.video;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;

import com.thunder.ktvplayer.R;
import com.youth.banner.adapter.BannerAdapter;

import java.util.List;

public class CustomMarqueeTextAdapter extends BannerAdapter<String, CustomMarqueeTextHolder> {
    public CustomMarqueeTextAdapter(List<String> datas) {
        super(datas);
    }

    @Override
    public CustomMarqueeTextHolder onCreateHolder(ViewGroup parent, int viewType) {
        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.custom_marquee_item, parent, false);
        return new CustomMarqueeTextHolder(view);
    }

    @Override
    public void onBindView(CustomMarqueeTextHolder holder, String data, int position, int size) {
        holder.textView.setText(data);
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/CustomMarqueeTextHolder.java

```
package com.thunder.ktvplayer.video;

import android.view.View;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import com.thunder.ktvplayer.R;

public class CustomMarqueeTextHolder extends RecyclerView.ViewHolder {
    public TextView textView;
    public CustomMarqueeTextHolder(@NonNull View view) {
        super(view);
        textView = view.findViewById(R.id.marquee_text);
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/PlayerView.java

```
package com.thunder.ktvplayer.video;
import android.content.Context;
import android.util.Log;

import androidx.annotation.NonNull;
import androidx.core.content.ContextCompat;
import com.thunder.ktv.player.mediaplayer.video.IMediaPlayer;
import com.thunder.ktv.player.utils.TextureViewUtil;
import com.thunder.android.stb.util.model.SurfaceFrameInfo;

import android.util.AttributeSet;
import android.util.TypedValue;
import android.view.Gravity;
import android.view.SurfaceView;
import android.view.TextureView;
import android.view.View;
import android.view.Surface;
import android.view.SurfaceHolder;
import android.view.ViewGroup;
import android.widget.FrameLayout;
import android.view.ViewTreeObserver;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import com.facebook.react.uimanager.ThemedReactContext;


import java.util.List;

public final class PlayerView extends FrameLayout {

    TextureViewUtil textureViewUtil;
    Surface mTextureSurface;
    private final FrameLayout layout;
    private IMediaPlayer player;
    private final ThemedReactContext context;
    private final ViewGroup.LayoutParams layoutParams;
    SurfaceFrameInfo surfaceFrameInfo;
    public PlayerView(ThemedReactContext context) {
        this(context, null);
    }

    public PlayerView(ThemedReactContext context, AttributeSet attrs) {
        this(context, attrs, 0);
    }

    public PlayerView(ThemedReactContext context, AttributeSet attrs, int defStyleAttr) {
        super(context, attrs, defStyleAttr);

        this.context = context;

        layoutParams = new ViewGroup.LayoutParams(
                ViewGroup.LayoutParams.MATCH_PARENT,
                ViewGroup.LayoutParams.MATCH_PARENT);

        FrameLayout.LayoutParams aspectRatioParams = new FrameLayout.LayoutParams(
                FrameLayout.LayoutParams.MATCH_PARENT,
                FrameLayout.LayoutParams.MATCH_PARENT);
        aspectRatioParams.gravity = Gravity.CENTER;
        layout = new FrameLayout(context);
        layout.setLayoutParams(aspectRatioParams);

        updateSurfaceView();
        addViewInLayout(layout, 0, aspectRatioParams);
    }
    public void clearVideoView() {
        if (mTextureSurface != null) {
            textureViewUtil.releaseSurface();
            textureViewUtil.detachViewFromParent();
            textureViewUtil=null;
            mTextureSurface=null;
        }
        if(player != null) {
            player.removeSurfaceFrame(surfaceFrameInfo);
        }
    }

    private void setVideoView() {
        if (player != null) {
            surfaceFrameInfo = new SurfaceFrameInfo(mTextureSurface);
            player.addSurfaceFrame(surfaceFrameInfo);
        }
    }

    public boolean isPlaying() {
        return player != null && player.isPlaying();
    }
    private void reLayout(View view) {
        if (view == null) return;
        view.measure(MeasureSpec.makeMeasureSpec(getMeasuredWidth(), MeasureSpec.EXACTLY),
                MeasureSpec.makeMeasureSpec(getMeasuredHeight(), MeasureSpec.EXACTLY));
        view.layout(view.getLeft(), view.getTop(), view.getMeasuredWidth(), view.getMeasuredHeight());
    }
    public void updateSurfaceView() {
        textureViewUtil = new TextureViewUtil();
        textureViewUtil.detachViewFromParent();
          textureViewUtil.attachViewToParent(layout);
          reLayout(layout);
          textureViewUtil.setCallback(new TextureViewUtil.Callback() {
              @Override
              public void onSurfaceCreate(Surface surface) {
                  mTextureSurface = surface;
                  if (player != null) {
                      setVideoView();
                  }
              }
              @Override
              public void onSurfaceChanged(Surface surface, int i, int i1) {
                  Log.d("PlayerView", "measureAndLayout" + i + "-" + i1);
                  if(player != null) {
                        if(player.isPlaying()) {
                            player.notifyRefreshSurface();
                        }
                  }

              }
          });
//         Log.d("PlayerView", "measureAndLayout" + textureViewUtil.getSurface());
    }
    // AdsLoader.AdViewProvider implementation.


    public void setPlayer(IMediaPlayer player) {
        if (this.player == player) {
            return;
        }
        if (this.player != null) {
            clearVideoView();
        }
        this.player = player;
        if (player != null) {
            setVideoView();
        }
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/ReactTdplayerView.java

```
package com.thunder.ktvplayer.video;

import android.content.Context;
import android.annotation.SuppressLint;
import android.view.View;
import android.widget.FrameLayout;
import android.util.Log;
import android.media.AudioManager;
import android.view.Display;
import android.hardware.display.DisplayManager;
import java.util.Timer;
import java.util.TimerTask;


import android.os.HandlerThread;
import com.thunder.android.stb.util.log.Logger;
import com.thunder.android.stb.util.model.DownloadBean;
import com.thunder.ktv.player.mediaplayer.video.IMediaPlayer;
import com.thunder.ktv.player.mediaplayer.video.FactoryMediaPlayer;
import com.thunder.ktv.player.mediaplayer.callback.PlayerCreatedCallback;
import com.thunder.ktv.thunderextension.jni.thunderapi.TDFileUtils;

import com.facebook.react.bridge.LifecycleEventListener;
import com.facebook.react.bridge.Promise;
import com.facebook.react.bridge.UiThreadUtil;
import com.facebook.react.uimanager.ThemedReactContext;
import com.thunder.ktvplayer.MyPresentation;
import android.app.Activity;

import java.util.ArrayList;
import java.io.File;


@SuppressLint("ViewConstructor")
public class ReactTdplayerView extends FrameLayout implements LifecycleEventListener {
    private static final String TAG = "ReactTdplayerView";
    private PlayerView playerView;
    private PlayerView playerView1;
    private final ThemedReactContext themedReactContext;
    private IMediaPlayer mPlayer;
    private final VideoEventEmitter eventEmitter;
    private boolean playRunning;
    private boolean hasAudioFocus = false;
    private TimerTask timerTask;
    private String reStartMessage = null;//重唱数据缓存
    private DownloadBean restartBean = null;
    private final AudioManager audioManager;
    private final AudioManager.OnAudioFocusChangeListener audioFocusChangeListener;
    //当前设置的原伴唱。
    private int currentChannel = 1; //先默认1为原唱，2为伴唱。
    private int volume = 100;

    //音轨个数，音轨为1时，切换原伴唱时要切换声道。
    private int audioChannelCount = 0;
    TimerTaskManager timerTaskManager = new TimerTaskManager(300);
    private MyPresentation mPresentation;
    private Display presentationDisplay;
    private DisplayManager displayManager;
    private String qrcodeUrl;
    private String title;
    private String name;
    private boolean loading = false;

    private final DisplayManager.DisplayListener displayListener = new DisplayManager.DisplayListener() {
        @Override
        public void onDisplayAdded(int displayId) {
            // 当有新的显示器连接时调用
            Log.e("displayListener", "显示器接入");
            showPresentation();
        }

        @Override
        public void onDisplayRemoved(int displayId) {
            // 当显示器被移除时调用
             Log.e("displayListener", "显示器移除");
             clearPresentation();
        }

        @Override
        public void onDisplayChanged(int displayId) {
            // 当显示器连接状态改变时调用

        }
    };

    public ReactTdplayerView(ThemedReactContext context) {
        super(context);
        this.themedReactContext = context;
        this.eventEmitter = new VideoEventEmitter(context);
        displayManager = (DisplayManager) context.getSystemService(Context.DISPLAY_SERVICE);
        displayManager.registerDisplayListener(displayListener, null);
        createViews();
        audioManager = (AudioManager) context.getSystemService(Context.AUDIO_SERVICE);
        themedReactContext.addLifecycleEventListener(this);
        audioFocusChangeListener = new OnAudioFocusChangedListener(this, themedReactContext);
        timerTaskManager.setCallback(new TimerTaskManager.Callback() {
            @Override
            public void performTask() {
                if (mPlayer != null) {
                    eventEmitter.progressChanged(mPlayer.getDuration(), mPlayer.getCurPosition());
                    loading = mPlayer.getCurPosition() / 1000D <= 2.5 && mPlayer.getCurPosition() / 1000D > 0;
                    if(mPresentation != null) {
                        mPresentation.setLoading(loading);
                    }
                }
            }
        });
    }

    @Override
    public void setId(int id) {
        super.setId(id);
        eventEmitter.setViewId(id);
    }
    private void clearPresentation() {
        if(playerView1 != null) {
            playerView1.clearVideoView();
            playerView1 = null;
        }
        if (mPresentation != null) {
            mPresentation.destroyBanner();
            mPresentation.dismiss();
            mPresentation = null; // 清理引用
        }

    }
    private void showPresentation() {
        Display[] displays = displayManager.getDisplays(DisplayManager.DISPLAY_CATEGORY_PRESENTATION);
        eventEmitter.displayChange(displays.length > 0);
        themedReactContext.getCurrentActivity().runOnUiThread(new Runnable() {
                @Override
                public void run() {
                    if (displays.length > 0) {
                        LayoutParams layoutParams = new LayoutParams(
                                        LayoutParams.MATCH_PARENT,
                                        LayoutParams.MATCH_PARENT);
                                playerView1 = new PlayerView(themedReactContext);
                                playerView1.setLayoutParams(layoutParams);
                           mPresentation = new MyPresentation(themedReactContext.getCurrentActivity(), displays[0], playerView1);
                           mPresentation.show();
                           if(qrcodeUrl != null) {
                                setQrcodeUrl(qrcodeUrl);
                           }
                           if(title != null) {
                                setTitle(title);
                           }
                           if(name!= null) {
                                setName(name);
                           }
                            mPresentation.setLoading(loading);
                   }
                }
            });

    }
    private void createViews() {

        LayoutParams layoutParams = new LayoutParams(
                LayoutParams.MATCH_PARENT,
                LayoutParams.MATCH_PARENT);
        playerView = new PlayerView(themedReactContext);
        playerView.setLayoutParams(layoutParams);

        addView(playerView, 0, layoutParams);
        playerView.setFocusable(true);
        showPresentation();
    }
    private void createPlayer() {
        if(mPlayer!=null){
            mPlayer.stop();
            mPlayer=null;
        }
        mPlayer = FactoryMediaPlayer.getInstance().createPlayer(0, new PlayerCreatedCallback() {
            @Override
            public void onError(int i, String s) {
                Log.e(TAG, " createPlayer = " + i + "msg=" + s);
            }
        }, true);
         Display[] displays = displayManager.getDisplays(DisplayManager.DISPLAY_CATEGORY_PRESENTATION);
         eventEmitter.displayChange(displays.length > 0);
    }
    /**
     * 播放视频
     *
     * @param mediaUrl 视频或者音频地址
     */
    public void openVideo(final String mediaUrl) {
        openVideo(new Runnable() {
            @Override
            public void run() {
                mPlayer.setDataSource(mediaUrl);
                reStartMessage = mediaUrl;
                restartBean = null;
            }
        });
    }

    public void openVideo(final String mediaUrl, final String videoUrl) {
        openVideo(new Runnable() {
            @Override
            public void run() {
                ArrayList<String> mediaUrlList = new ArrayList<>();
                ArrayList<String> videoarrayList = new ArrayList<>();
                mediaUrlList.add(mediaUrl);
                videoarrayList.add(videoUrl);
                mPlayer.setDataSource(mediaUrlList, videoarrayList,null);
            }
        });
    }

    public void openVideo(final String paramJson, final DownloadBean bean) {
        openVideo(new Runnable() {
            @Override
            public void run() {
                try {
                    mPlayer.setDataSource(paramJson, bean);
                    reStartMessage = paramJson;
                    restartBean = bean;
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        });
    }

    private void openVideo(Runnable setDataSource) {
        try {
            if (mPlayer == null) {
                Log.e(TAG, "mPlayer is null.");
                createPlayer();
            }
            stopVideo();
            audioChannelCount = 0;
            mPlayer.reset();
            initPlayerListener();
            playerView.setPlayer(mPlayer);
            if(playerView1 != null) {
                playerView1.setPlayer(mPlayer);
            }
            setDataSource.run();
            mPlayer.prepareAsync();
            mPlayer.notifyRefreshSurface();

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
    private void initPlayerListener() {
        mPlayer.setOnPreparedListener(new IMediaPlayer.OnPreparedListener() {
            @Override
            public void onPrepared(IMediaPlayer iMediaPlayer) {
                Log.d(TAG, "onPrepared: " + currentChannel);
                hasAudioFocus = requestAudioFocus();
                if (hasAudioFocus) {
                    iMediaPlayer.start();
                    mPlayer.setVolume(volume);
                    mPlayer.notifyRefreshSurface();
                    eventEmitter.load(iMediaPlayer.getDuration(), iMediaPlayer.getCurPosition(), iMediaPlayer.getAudioStreamCount());
                }
            }
        });
        mPlayer.setOnCompletionListener(new IMediaPlayer.OnCompletionListener() {
            @Override
            public void onCompletion(IMediaPlayer iMediaPlayer) {
                Log.d(TAG, "onCompletion: ");
                eventEmitter.end();
            }
        });
        mPlayer.setOnErrorListener(new IMediaPlayer.OnErrorListener() {
            @Override
            public boolean onError(IMediaPlayer iMediaPlayer, int what, int extra) {
                Log.d(TAG, "onError: what" + what + "extra=" + extra);
                eventEmitter.error(what, extra);
                return false;
            }
        });
        mPlayer.setOnVideoRunningListener(new IMediaPlayer.OnVideoRunningListener() {
            @Override
            public void onVideoRunning(IMediaPlayer iMediaPlayer) {
                Log.d(TAG, "onVideoRunning: ");
                audioChannelCount = iMediaPlayer.getAudioStreamCount();
                setSelectedAudioTrack(currentChannel);
                playRunning = true;
                eventEmitter.playbackStateChanged(true);
                timerTaskManager.start();
//                 refreshText();
            }
        });
        mPlayer.setOnSeekCompleteListener(new IMediaPlayer.OnSeekCompleteListener() {
            @Override
            public void onSeekComplete(IMediaPlayer iMediaPlayer) {
                Log.d(TAG, "onSeekComplete: ");
            }
        });
        mPlayer.setOnInfoListener(new IMediaPlayer.OnInfoListener() {
            @Override
            public void onInfo(IMediaPlayer iMediaPlayer, int what, int extra) {
                Log.d(TAG, "onInfo: what=" + what + "extra=" + extra);
            }
        });
        mPlayer.setOnCacheDownloadListener(new IMediaPlayer.OnCacheDownloadListener() {
            @Override
            public void onCacheFileDownloaded(final String filepath, final String mediaFileName, final int mediaFileLength) {
                Log.d(TAG, "downloaded! filepath:" + filepath + ",mediaFileName:" + mediaFileName + ",filelength:" + mediaFileLength);
                int lastDotIndex = filepath.lastIndexOf('.');
                try {
                    File oldFile = new File(filepath);
                    File newFile = new File(filepath.substring(0, lastDotIndex));
                    if (oldFile.exists()) {
                        if (oldFile.renameTo(newFile)) {
                             Log.d(TAG, "File renamed successfully");
                             eventEmitter.downloadComplete(filepath.substring(0, lastDotIndex));
                        } else {
                            Log.d(TAG,"Rename Error File rename failed");
                        }
                    } else {
                        Log.d(TAG,"File Not Found The specified file does not exist");
                    }
                } catch (Exception e) {
                    Log.d(TAG,"Exception"+ e.getMessage());
                }
//                 try {
//                     String cmd = "cp -f " + filepath + " " + dstFilePath;
//                     Process p = Runtime.getRuntime().exec(cmd);
//                     p.waitFor();
//                     TDFileUtils.fileTruncate(dstFilePath, mediaFileLength);
//                 } catch (Exception e) {
//                     e.printStackTrace();
//                     Logger.warn(filepath + " mv to " + dstFilePath + " failed!");
//                     return;
//                 }
            }
        });
    }
    public void refreshText() {
        if (timerTask == null) {
            Timer timer = new Timer();
            timerTask = new TimerTask() {
                @Override
                public void run() {
                    if(playRunning) {
                        eventEmitter.progressChanged(mPlayer.getDuration(), mPlayer.getCurPosition());
                    }
                }
            };
            timer.schedule(timerTask, 1000, 1000);
        }
    }
    public void stopVideo() {
        if (mPlayer != null) {
            mPlayer.stop();
        }
        playRunning = false;
        timerTaskManager.stop();
    }
    private void pauseVideo() {
        if (mPlayer != null) {
            mPlayer.pause();
            timerTaskManager.pause();
        }
    }
    private void rePlayPlayer() {
        if (mPlayer != null) {
            mPlayer.resume();
            mPlayer.notifyRefreshSurface();
            timerTaskManager.resume();
        }

    }
    public void resume() {
        hasAudioFocus = requestAudioFocus();
        if(hasAudioFocus) {
            rePlayPlayer();
            eventEmitter.playbackStateChanged(true);
        }
    }
    public void setFullscreen(boolean fullscreen) {
        playerView.setPlayer(mPlayer);
    }
    public void setPausedModifier(boolean paused) {
        playRunning = !paused;
        if (mPlayer != null) {
            if (!paused) {
                rePlayPlayer();

            } else {
                pauseVideo();
            }
        }
    }
    public void setSelectedAudioTrack(int selectAudioTrack) {
        currentChannel = selectAudioTrack;
        if(mPlayer != null) {
            if (audioChannelCount > 1) {
                mPlayer.selectAudioStream(currentChannel);
            } else {
                mPlayer.setAudioChannelMode(currentChannel);
            }
        }

    }
    public void reset() {
        if (mPlayer != null) {
            if(reStartMessage != null) {
                if (restartBean != null) {
                    openVideo(reStartMessage, restartBean);
                } else {
                    openVideo(reStartMessage);
                }
            }

        }
    }
    public void setVolume(int volume) {
        this.volume = volume;
        if(mPlayer != null)
        mPlayer.setVolume(volume);
    }
    public void setQrcodeUrl(String url) {
        if(mPresentation != null) {
            mPresentation.setQrcodeUrl(url);
        }
    }
    public void setTitle(String title) {
         if(mPresentation != null) {
             mPresentation.setTitle(title);
         }
    }
    public void setName(String name) {
         if(mPresentation != null) {
             mPresentation.setName(name);
         }
    }
    // LifecycleEventListener implementation
    @Override
    public void onHostResume() {
        if(playRunning) {
            rePlayPlayer();
            eventEmitter.playbackStateChanged(true);
        }
        playerView.updateSurfaceView();
        if(playerView1 != null) {
            playerView1.updateSurfaceView();
        }
    }
    @Override
    public void onHostPause() {
        pauseVideo();
        eventEmitter.playbackStateChanged(false);
        playerView.clearVideoView();
        if(playerView1 != null) {
            playerView1.clearVideoView();
        }
    }

    @Override
    public void onHostDestroy() {
        cleanUpResources();
    }

    @Override
    protected void onDetachedFromWindow() {
        super.onDetachedFromWindow();
    }

    public void cleanUpResources() {
        themedReactContext.removeLifecycleEventListener(this);
    }
    private static class OnAudioFocusChangedListener implements AudioManager.OnAudioFocusChangeListener {
        private final ReactTdplayerView view;
        private final ThemedReactContext themedReactContext;

        private OnAudioFocusChangedListener(ReactTdplayerView view, ThemedReactContext themedReactContext) {
            this.view = view;
            this.themedReactContext = themedReactContext;
        }

        @Override
        public void onAudioFocusChange(int focusChange) {
            switch (focusChange) {
                case AudioManager.AUDIOFOCUS_LOSS:
                    view.hasAudioFocus = false;
                    view.eventEmitter.audioFocusChanged(false);
                    // FIXME this pause can cause issue if content doesn't have pause capability (can happen on live channel)
                    view.pauseVideo();
                    view.eventEmitter.playbackStateChanged(false);
                    view.audioManager.abandonAudioFocus(this);
                    break;
                case AudioManager.AUDIOFOCUS_LOSS_TRANSIENT:
                    view.eventEmitter.audioFocusChanged(false);
                    view.pauseVideo();
                    view.eventEmitter.playbackStateChanged(false);
                    break;
                case AudioManager.AUDIOFOCUS_GAIN:
                    view.hasAudioFocus = true;
                    view.eventEmitter.audioFocusChanged(true);
                    if(view.playRunning) {
                        view.rePlayPlayer();
                        view.eventEmitter.playbackStateChanged(true);
                    }
                    break;
                default:
                    break;
            }

            Activity activity = themedReactContext.getCurrentActivity();
            if (view.mPlayer != null && activity != null) {
                if (focusChange == AudioManager.AUDIOFOCUS_LOSS_TRANSIENT_CAN_DUCK) {
                    // Lower the volume
                     activity.runOnUiThread(() ->
                            view.mPlayer.setVolume(80)
                        );
                } else if (focusChange == AudioManager.AUDIOFOCUS_GAIN) {
                    // Raise it back to normal
                    activity.runOnUiThread(() ->
                        view.mPlayer.setVolume(100)
                    );
                }
            }
        }
    }
    private boolean requestAudioFocus() {
        if (this.hasAudioFocus) {
            return true;
        }
        int result = audioManager.requestAudioFocus(audioFocusChangeListener,
                AudioManager.STREAM_MUSIC,
                AudioManager.AUDIOFOCUS_GAIN);
        return result == AudioManager.AUDIOFOCUS_REQUEST_GRANTED;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/ReactTdplayerViewManager.java

```
package com.thunder.ktvplayer.video;

import android.content.Context;
import android.graphics.Color;
import android.net.Uri;
import android.text.TextUtils;
import android.util.Log;

import com.thunder.android.stb.util.model.DownloadBean;
import androidx.annotation.NonNull;
import com.facebook.react.bridge.ReadableArray;
import com.facebook.react.bridge.ReadableMap;
import com.facebook.react.common.MapBuilder;
import com.facebook.react.uimanager.ThemedReactContext;
import com.facebook.react.uimanager.ViewGroupManager;
import com.facebook.react.uimanager.annotations.ReactProp;

import java.util.ArrayList;
import java.util.Map;
import java.util.UUID;
import org.json.JSONException;
import org.json.JSONObject;

import javax.annotation.Nullable;

public class ReactTdplayerViewManager extends ViewGroupManager<ReactTdplayerView> {

    private static final String TAG = "TdViewManager";
    private static final String REACT_CLASS = "RCTVideo";
    private static final String PROP_SOURCE = "source";
    private static final String PROP_SELECTED_AUDIO_TRACK = "selectedAudioTrack";
    private static final String PROP_PAUSED = "paused";
    private static final String PROP_FULLSCREEN = "isFullScreen";
    private static final String PROP_VOLUME = "volume";
    private static final String PROP_TITLE = "title";
    private static final String PROP_QRCODE_URL = "qrcodeUrl";
    private static final String PROP_NAME = "name";


    @NonNull
    @Override
    public String getName() {
        return REACT_CLASS;
    }

    @NonNull
    @Override
    protected ReactTdplayerView createViewInstance(@NonNull ThemedReactContext themedReactContext) {
        return new ReactTdplayerView(themedReactContext);
    }

    @Override
    public void onDropViewInstance(ReactTdplayerView view) {
        view.cleanUpResources();
    }

    @Override
    public @Nullable Map<String, Object> getExportedCustomDirectEventTypeConstants() {
        MapBuilder.Builder<String, Object> builder = MapBuilder.builder();
        for (String event : VideoEventEmitter.Events) {
        Log.d(TAG,event);
            builder.put(event, MapBuilder.of("registrationName", event));
        }
        return builder.build();
    }

    @ReactProp(name = PROP_SOURCE)
    public void setSrc(final ReactTdplayerView videoView, @Nullable ReadableMap source) {
        if (source.hasKey("uri")) {
            videoView.openVideo(source.getString("uri"));
        } else if(source.hasKey("songId")) {
            String songId = source.getString("songId");
            String songName = source.getString("songName");
            String path = source.getString("path");
            final DownloadBean bean = new DownloadBean(songName, songId, path);
             bean.playWithDownload = source.getBoolean("isDownload"); //设置边下边播
            String resolution = source.getString("resolution");//设置分辨率 值为 "1080","720","480","320","240"
            JSONObject jsonObject = new JSONObject();//设置播放源options
            try {
                jsonObject.put("musicno", songId);
                jsonObject.put("is265", "0");
                jsonObject.put("resolution", resolution);
                jsonObject.put("ls", "0");
            } catch (JSONException e) {
                e.printStackTrace();
            }
            videoView.openVideo(jsonObject.toString(), bean);
        }

    }

    @ReactProp(name = PROP_SELECTED_AUDIO_TRACK)
    public void setSelectedAudioTrack(final ReactTdplayerView videoView,
                                     @Nullable int selectedAudioTrack) {
                                     Log.d(TAG, selectedAudioTrack + "selectedAudioTrack");
        videoView.setSelectedAudioTrack(selectedAudioTrack);
    }

    @ReactProp(name = PROP_PAUSED, defaultBoolean = false)
    public void setPaused(final ReactTdplayerView videoView, final boolean paused) {
        videoView.setPausedModifier(paused);
    }

    @ReactProp(name = PROP_FULLSCREEN, defaultBoolean = false)
    public void setFullscreen(final ReactTdplayerView videoView, final boolean fullscreen) {
        videoView.setFullscreen(fullscreen);
    }
    @ReactProp(name = PROP_VOLUME,defaultInt = 100)
    public void setVolume(final ReactTdplayerView videoView, final int volume) {
        videoView.setVolume(volume);
    }
    @ReactProp(name = PROP_QRCODE_URL)
    public void setQrcodeUrl(final ReactTdplayerView videoView, final String url) {
        videoView.setQrcodeUrl(url);
    }
    @ReactProp(name = PROP_TITLE)
    public void setTitle(final ReactTdplayerView videoView, final String title) {
        videoView.setTitle(title);
    }
    @ReactProp(name = PROP_NAME)
        public void setName(final ReactTdplayerView videoView, final String name) {
            videoView.setName(name);
        }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/TimerTaskManager.java

```
package com.thunder.ktvplayer.video;

import java.util.Timer;
import java.util.TimerTask;

public class TimerTaskManager {
    private Timer timer;
    private TimerTask timerTask;
    private long interval;  // 间隔时间，单位为毫秒
    private boolean isPaused;
    private Callback callback;

    public TimerTaskManager(long interval) {
        this.interval = interval;
        this.isPaused = false;
        this.timer = new Timer();
    }

    public void start() {
        if (timerTask == null) {
            timerTask = new TimerTask() {
                @Override
                public void run() {
                    if (!isPaused) {
                        if (callback != null) {
                            callback.performTask();
                        }
                    }
                }
            };
            timer.scheduleAtFixedRate(timerTask, 0, interval);
        }
    }

    public void pause() {
        isPaused = true;
    }

    public void resume() {
        isPaused = false;
    }

    public void stop() {
        if (timerTask != null) {
            timerTask.cancel();
            timerTask = null;
        }
    }

    public void destroy() {
        stop();
        if (timer != null) {
            timer.cancel();
            timer.purge();
            timer = null;
        }
    }
    public void setCallback(Callback callback) {
        this.callback = callback;
    }
    public interface Callback {
        void performTask();
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/com/thunder/ktvplayer/video/VideoEventEmitter.java

```
package com.thunder.ktvplayer.video;

import androidx.annotation.StringDef;

import android.view.View;

import com.facebook.react.bridge.Arguments;
import com.facebook.react.bridge.ReactContext;
import com.facebook.react.bridge.UIManager;
import com.facebook.react.bridge.WritableArray;
import com.facebook.react.bridge.WritableMap;
import com.facebook.react.uimanager.UIManagerHelper;
import com.facebook.react.uimanager.common.ViewUtil;

import java.io.PrintWriter;
import java.io.StringWriter;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.util.ArrayList;
import java.util.Map;
import android.util.Log;

public class VideoEventEmitter {

    private final ReactContext mReactContext;

    private int viewId = View.NO_ID;

    public VideoEventEmitter(ReactContext reactContext) {
        this.mReactContext = reactContext;
    }

    private static final String EVENT_DOWNLOAD_COMPLETE = "onVideoDownloadComplete";
    private static final String EVENT_LOAD = "onVideoLoad";
    private static final String EVENT_ERROR = "onVideoError";
    private static final String EVENT_PROGRESS = "onVideoProgress";
    private static final String EVENT_END = "onVideoEnd";

    private static final String EVENT_PLAYBACK_STATE_CHANGED = "onVideoPlaybackStateChanged";
    private static final String EVENT_AUDIO_FOCUS_CHANGE = "onAudioFocusChanged";
    private static final String EVENT_VOLUME_CHANGE = "onVolumeChange";
    private static final String EVENT_AUDIO_TRACKS = "onAudioTracks";
    private static final String EVENT_DISPLAY_CHANGE = "onDisplayChange";

    static public final String[] Events = {
            EVENT_DOWNLOAD_COMPLETE,
            EVENT_LOAD,
            EVENT_ERROR,
            EVENT_PROGRESS,
            EVENT_END,
            EVENT_PLAYBACK_STATE_CHANGED,
            EVENT_AUDIO_FOCUS_CHANGE,
            EVENT_VOLUME_CHANGE,
            EVENT_AUDIO_TRACKS,
            EVENT_DISPLAY_CHANGE
    };

    @Retention(RetentionPolicy.SOURCE)
    @StringDef({
            EVENT_DOWNLOAD_COMPLETE,
            EVENT_LOAD,
            EVENT_ERROR,
            EVENT_PROGRESS,
            EVENT_END,
            EVENT_PLAYBACK_STATE_CHANGED,
            EVENT_AUDIO_FOCUS_CHANGE,
            EVENT_VOLUME_CHANGE,
            EVENT_AUDIO_TRACKS,
            EVENT_DISPLAY_CHANGE
    })
    @interface VideoEvents {
    }

    private static final String EVENT_PROP_CURRENT_TIME = "currentTime";
    private static final String EVENT_PROP_DURATION = "duration";
    private static final String EVENT_PROP_AUDIO_TRACKS = "audioTracks";
    private static final String EVENT_PROP_HAS_AUDIO_FOCUS = "hasAudioFocus";
    private static final String EVENT_PROP_VOLUME = "volume";
    private static final String EVENT_PROP_WHAT = "what";
    private static final String EVENT_PROP_EXTRA = "extra";
    private static final String EVENT_PROP_IS_PLAYING = "isPlaying";
    private static final String EVENT_PROP_FILE_PATH = "filePath";
    private static final String EVENT_PROP_DISPLAY_CHANGE = "dualScreen";

    public void setViewId(int viewId) {
        this.viewId = viewId;
    }

    public void downloadComplete(String filePath) {
         WritableMap map = Arguments.createMap();
                map.putString(EVENT_PROP_FILE_PATH, filePath);
        receiveEvent(EVENT_DOWNLOAD_COMPLETE, map);
    }
    public void load(double duration, double currentPosition, int audioTracks){

        WritableMap event = Arguments.createMap();
                event.putDouble(EVENT_PROP_DURATION, duration / 1000D);
                event.putDouble(EVENT_PROP_CURRENT_TIME, currentPosition / 1000D);
                event.putInt(EVENT_PROP_AUDIO_TRACKS, audioTracks);
                receiveEvent(EVENT_LOAD, event);
    }

    public void audioTracks(int audioTracks){
         WritableMap map = Arguments.createMap();
         map.putInt(EVENT_PROP_AUDIO_TRACKS, audioTracks);
        receiveEvent(EVENT_AUDIO_TRACKS, map);
    }
    public void displayChange(boolean status){
    Log.d("displayChange", "displayChange");
         WritableMap map = Arguments.createMap();
         map.putBoolean(EVENT_PROP_DISPLAY_CHANGE, status);
        receiveEvent(EVENT_DISPLAY_CHANGE, map);
    }
    public void progressChanged(double duration, double currentPosition) {
        WritableMap event = Arguments.createMap();
        event.putDouble(EVENT_PROP_CURRENT_TIME, currentPosition / 1000D);
        event.putDouble(EVENT_PROP_DURATION, duration / 1000D);
        receiveEvent(EVENT_PROGRESS, event);
    }

    public void playbackStateChanged(boolean isPlaying) {
        WritableMap map = Arguments.createMap();
        map.putBoolean(EVENT_PROP_IS_PLAYING, isPlaying);
        receiveEvent(EVENT_PLAYBACK_STATE_CHANGED, map);
    }

    public void end() {
        receiveEvent(EVENT_END, null);
    }
    public void error(int what, int extra) {
         WritableMap error = Arguments.createMap();
        error.putInt(EVENT_PROP_WHAT, what);
        error.putInt(EVENT_PROP_EXTRA, extra);
        receiveEvent(EVENT_ERROR, error);
    }

    public void volumeChange(float volume) {
        WritableMap map = Arguments.createMap();
        map.putDouble(EVENT_PROP_VOLUME, volume);
        receiveEvent(EVENT_VOLUME_CHANGE, map);
    }



    public void audioFocusChanged(boolean hasFocus) {
        WritableMap map = Arguments.createMap();
        map.putBoolean(EVENT_PROP_HAS_AUDIO_FOCUS, hasFocus);
        receiveEvent(EVENT_AUDIO_FOCUS_CHANGE, map);
    }

    private void receiveEvent(@VideoEvents String type, WritableMap event) {
        UIManager uiManager = UIManagerHelper.getUIManager(mReactContext, ViewUtil.getUIManagerType(viewId));

        if(uiManager != null) {
           uiManager.receiveEvent(UIManagerHelper.getSurfaceId(mReactContext), viewId, type, event);
        }
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/AudioRecordInfo.java

```
package myaudiorecord;

/**
 * Created by chengkai on 18-4-4.
 */
public class AudioRecordInfo
{
    private int SamplesRate = 0;
    private int SamplesBits = 0;
    private int Channels = 0;
    public AudioRecordInfo(int SamplesRate, int SamplesBits, int Channels){
        setSamplesRate(SamplesRate);
        setSamplesBits(SamplesBits);
        setChannels(Channels);
    }

    public void setSamplesBits(int samplesBits) {
        if(samplesBits == 0){
            this.SamplesBits = AudioRecorder.getInstance().getAudioRecordInfo().getSamplesBits();
        }else{
            this.SamplesBits = samplesBits;
        }
    }
    public int getSamplesBits() {
        return SamplesBits;
    }

    public void setSamplesRate(int samplesRate) {
        if(samplesRate == 0){
            this.SamplesRate = AudioRecorder.getInstance().getAudioRecordInfo().getSamplesRate();
        }else{
            this.SamplesRate = samplesRate;
        }
    }
    public int getSamplesRate() {
        return SamplesRate;
    }

    public void setChannels(int channels) {
        if(channels == 0){
            this.Channels = AudioRecorder.getInstance().getAudioRecordInfo().getChannels();
        }else{
            this.Channels = channels;
        }
    }
    public int getChannels() {
        return Channels;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/AudioRecorder.java

```
package myaudiorecord;
import android.media.AudioFormat;
import android.util.Log;


import com.thunder.miaimedia.recoder.RecorderData;

import java.io.IOException;
import java.util.Collections;
import java.util.List;
import java.util.concurrent.CopyOnWriteArrayList;

import myaudiorecord.RecordStream.RecorderOutputStream;
import myaudiorecord.record.IThRecorder;
import myaudiorecord.record.MyAudioRecord;
import myaudiorecord.utils.PcmData;


public class AudioRecorder {
    static final String TAG = AudioRecorder.class.getName();
    static private AudioRecorder instance  = null;

    private static int SamplesRate = 48000;
    static final private int SamplesBits = AudioFormat.ENCODING_PCM_16BIT;
    static final private int Channels = AudioFormat.CHANNEL_IN_STEREO;

    private List<RecorderOutputStream> recorderOutputStreams  = Collections.synchronizedList(new CopyOnWriteArrayList<RecorderOutputStream>());
    private RecordThread recordThread = null;


    private AudioRecordInfo audioRecordInfo =  new AudioRecordInfo(SamplesRate,SamplesBits,Channels);
    public AudioRecordInfo getAudioRecordInfo() {
        return audioRecordInfo;
    }

    static public AudioRecorder getInstance()
    {
        synchronized (AudioRecorder.class) {
            if (instance == null) {
                instance = new AudioRecorder();
            }
        }
        return instance;
    }
    private IThRecorder iThRecorder = null;
    private AudioRecorder(){
        iThRecorder = createThRecorder();
        audioRecordInfo.setSamplesRate(SamplesRate);
        if(recordThread == null){
            recordThread = new RecordThread("RecordThread");
            recordThread.start();
        }
    }

    public interface OnAudioRecorderErrorListener {
        void onAudioRecorderError(int nType);
    }
    private OnAudioRecorderErrorListener onAudioRecorderErrorListener = null;
    public void setOnRecorderErrorListener(OnAudioRecorderErrorListener onAudioRecorderErrorListener) {
        this.onAudioRecorderErrorListener = onAudioRecorderErrorListener;
    }

    public void addOutputStream(RecorderOutputStream outputStream)
    {
        if(outputStream == null || recorderOutputStreams == null){
            return;
        }
        Log.d(TAG, "addOutputStream: " + outputStream.getName());
        recorderOutputStreams.add(outputStream);
    }
    public void removeOutputStream(RecorderOutputStream outputStream)
    {
        if(outputStream == null || recorderOutputStreams == null){
            return;
        }
        Log.d(TAG, "removeOutputStream: " + outputStream.getName());
        recorderOutputStreams.remove(outputStream);
    }

    private static IThRecorder createThRecorder()
    {
        return MyAudioRecord.getInstance();
    }

    class RecordThread extends Thread {
        RecordThread(String name){
            super(name);
        }
        private void doAudioRecorderErrorListener()
        {
            if(onAudioRecorderErrorListener != null){
                onAudioRecorderErrorListener.onAudioRecorderError(0);
            }
        }

        @Override
        public void run(){
            if(recorderOutputStreams == null)
                return;
            byte[] bytes = new byte[10 * 1024];

            int readLen;
            PcmData pcmData  = new PcmData();
            if(iThRecorder == null){
                Log.e(TAG,"iThRecorder is null !!!  ");
                doAudioRecorderErrorListener();
                return;
            }
            iThRecorder.init(audioRecordInfo.getSamplesRate(), audioRecordInfo.getChannels(), audioRecordInfo.getSamplesBits());
            while(true){
                int reSampleLen;
                try {
                    Thread.sleep(500);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                if(recorderOutputStreams.size() == 0)
                    continue;
                iThRecorder.start();
                while(recorderOutputStreams.size() > 0){
                    readLen = iThRecorder.read(bytes,0,bytes.length);
                    if(readLen <= 0){
                        if(onAudioRecorderErrorListener != null){
                            onAudioRecorderErrorListener.onAudioRecorderError(1);
                        }
                        break;
                    }

                    pcmData.load(bytes,readLen,
                            AudioRecorder.getInstance().audioRecordInfo.getSamplesRate(),
                            AudioRecorder.getInstance().audioRecordInfo.getSamplesBits(),
                            AudioRecorder.getInstance().audioRecordInfo.getChannels());
                    if(true){
                        reSampleLen = pcmData.reSample(16000,
                                AudioFormat.CHANNEL_IN_LEFT);
                        RecorderData.getInstance().onReceiveData(pcmData.reSampleBuffer, 0, reSampleLen);
                    }
                    for(RecorderOutputStream recorderOutputStream:recorderOutputStreams){
                        reSampleLen = pcmData.reSample(recorderOutputStream.audioRecordInfo.getSamplesRate(),
                                recorderOutputStream.audioRecordInfo.getChannels());
                        if(reSampleLen > 0){
                            try {
                                recorderOutputStream.write(pcmData.reSampleBuffer,0,reSampleLen);
                            } catch (IOException e) {
                                e.printStackTrace();
                            }
                        }
                    }
                }
                iThRecorder.stop();
            }
        }
    }
}


```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/RecordStream/RecorderOutputStream.java

```
package myaudiorecord.RecordStream;


import java.io.IOException;
import java.io.OutputStream;

import myaudiorecord.AudioRecordInfo;
import myaudiorecord.AudioRecorder;

/**
 * Created by 成凯 on 2017/7/27.
 */
public abstract class RecorderOutputStream extends OutputStream {
    public AudioRecordInfo audioRecordInfo = null;
    private boolean canPause = false;

    public boolean isCanPause() {
        return canPause;
    }

    public RecorderOutputStream(boolean canPause)
    {
        this.canPause = canPause;
        audioRecordInfo = new AudioRecordInfo(
                AudioRecorder.getInstance().getAudioRecordInfo().getSamplesRate(),
                AudioRecorder.getInstance().getAudioRecordInfo().getSamplesBits(),
                AudioRecorder.getInstance().getAudioRecordInfo().getChannels()
        );

    }
    public abstract String getName();
    protected String recordName = null;
    public abstract int open(String recordName) throws IOException;
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/RecordStream/RecorderXiaoAIOutputStream.java

```
package myaudiorecord.RecordStream;

import android.media.AudioFormat;


import java.io.IOException;

import myaudiorecord.AudioRecorder;
import myaudiorecord.utils.ArrayBytesDeque;


/**
 * Created by chengkai on 17-12-15.
 */

public class RecorderXiaoAIOutputStream extends RecorderOutputStream {
    static private final int needSampleRateInHz = 16000;
    static private final int needChannel = AudioFormat.CHANNEL_IN_LEFT;
    private static final String TAG = RecorderXiaoAIOutputStream.class.getSimpleName();
    @Override
    public String getName() {
        return TAG;
    }

    ArrayBytesDeque arrayBytesDeque = null;
    public RecorderXiaoAIOutputStream() {
        super(false);
        audioRecordInfo.setSamplesRate(this.needSampleRateInHz);
        audioRecordInfo.setChannels(this.needChannel);
        arrayBytesDeque = new ArrayBytesDeque(2 * 1024 * 1024);
    }

    @Override
    public int open(String recordName) throws IOException {
        AudioRecorder.getInstance().addOutputStream(this);
        return 0;
    }

    @Override
    public void close() throws IOException {
        AudioRecorder.getInstance().removeOutputStream(this);
        arrayBytesDeque.clear();
        super.close();
    }

    @Override
    public void write(int b) throws IOException {

    }

    @Override
    public void write( byte[] b, int off, int len) throws IOException {
        arrayBytesDeque.add(b,off,len);
    }

    @Override
    public void write(byte[] buffer)
    {
        arrayBytesDeque.add(buffer,0,buffer.length);
    }

    public int read(byte[] audioData, int offsetInBytes, int sizeInBytes)
    {
        return arrayBytesDeque.pop(audioData,offsetInBytes,sizeInBytes);
    }
    public int getDataLen()
    {
        return arrayBytesDeque.getCacheLen();
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/record/IThRecorder.java

```
package myaudiorecord.record;

/**
 * Created by chengkai on 18-3-6.
 */

public interface IThRecorder {
    int init(int samplesRate, int channels, int samplesBits);
    int release();
    int start();
    int read(byte[] bytes, int offset, int len);
    int stop();
    int setVolume(int vol);
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/record/MyAudioRecord.java

```
package myaudiorecord.record;

import android.media.AudioRecord;
import android.media.MediaRecorder;
import android.util.Log;

/**
 * Created by chengkai on 18-3-6.
 *
 */

public class MyAudioRecord implements IThRecorder {
    private static final String TAG = "MyAudioRecord";
    private MyAudioRecord(){}
    private static MyAudioRecord instance = null;

    public static MyAudioRecord getInstance() {
        if (instance == null) {
            synchronized (MyAudioRecord.class) {
                if (instance == null) {
                    instance = new MyAudioRecord();
                }
            }
        }
        return instance;
    }

    private AudioRecord audioRecord = null;
    @Override
    public int init(int samplesRate,int channels,int samplesBits) {
        Log.d(TAG, "init: ");
        int minBufferSize = AudioRecord.getMinBufferSize(samplesRate, channels, samplesBits);
        audioRecord = new AudioRecord(
                MediaRecorder.AudioSource.DEFAULT,
                samplesRate, channels, samplesBits,
                minBufferSize * 2);//增大地层缓冲区大小

        if(audioRecord == null){
            Log.e(TAG,"MyAudioRecord init new error");
            return -1;
        }
        if(audioRecord.getState() == AudioRecord.STATE_UNINITIALIZED){
            release();
            Log.e(TAG,"MyAudioRecord init getState error");
            return -2;
        }
        return 0;
    }

    @Override
    public int release() {
        Log.d(TAG, "release: ");
        if(audioRecord == null)
            return -1;
        stop();
        if(audioRecord.getState() == AudioRecord.STATE_INITIALIZED){
            audioRecord.release();
        }
        audioRecord = null;
        return 0;
    }

    @Override
    public int start() {
        Log.d(TAG, "start: ");
        if(audioRecord == null)
            return -1;
        if(audioRecord.getRecordingState() == AudioRecord.RECORDSTATE_STOPPED){
            audioRecord.startRecording();
            Log.d(TAG, "audioRecord startRecording: ");
            if(audioRecord.getRecordingState() == AudioRecord.RECORDSTATE_RECORDING){
                return 0;
            }
        }
        return -2;
    }

    @Override
    public int read(byte[] bytes, int offset, int len) {
        if(audioRecord == null)
            return 0;
        if(audioRecord.getRecordingState() == AudioRecord.RECORDSTATE_STOPPED){
            return 0;
        }
        return audioRecord.read(bytes,offset,len);
    }

    @Override
    public int stop() {
        Log.d(TAG, "stop: ");
        if(audioRecord == null)
            return -1;
        if(audioRecord.getRecordingState() == AudioRecord.RECORDSTATE_RECORDING){
            audioRecord.stop();
            Log.d(TAG, "audioRecord stop: ");
            if(audioRecord.getRecordingState() == AudioRecord.RECORDSTATE_STOPPED){
                return 0;
            }
        }
        return -2;
    }

    @Override
    public int setVolume(int vol) {
        //not support
        return 0;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/utils/ArrayBytesDeque.java

```
package myaudiorecord.utils;

/**
 * Created by chengkai on 18-1-26.
 */

public class ArrayBytesDeque{

    private int max = 0;
    private byte[] cache = null;
    private byte[] tmpCopy = null;
    private int cacheLen = 0;

    public ArrayBytesDeque(int max) {
        this.max = max;
    }
    public boolean isEmpty() {
        return cacheLen == 0;
    }

    private byte[] tempData = null;
    public synchronized void add(byte[] buffer, int offset, int len) {
        if(cache == null){
            if(len > max){
                len = max;
            }
            cache = new byte[len];
            System.arraycopy(buffer,offset,cache,0,len);
            cacheLen = len;
        }else{
            if(cache.length - cacheLen >= len){
                System.arraycopy(buffer,offset,cache,cacheLen,len);
                cacheLen+=len;
            }else{
                if(len + cacheLen > max){
                    len = max - cacheLen;
                }
//                if(tempData == null){
//                    tempData = new byte[len + cacheLen];
//                }
                byte[] tmp = new byte[len + cacheLen];
                System.arraycopy(cache,0,tmp,0,cacheLen);
                System.arraycopy(buffer,offset,tmp,cacheLen,len);
                cache = tmp;
                cacheLen = len + cacheLen;
            }
        }
    }

    public synchronized int pop(byte[] buffer, int off, int len) {
        if(cache == null || cacheLen == 0)
            return 0;
        int readLen = 0;
        if(len <= cacheLen){
            readLen = len;
            System.arraycopy(cache,0,buffer,off,readLen);
            if(tmpCopy == null || tmpCopy.length < cacheLen - readLen){
                tmpCopy = new byte[cacheLen - readLen];
            }
            System.arraycopy(cache,readLen,tmpCopy,0,cacheLen - readLen);
            System.arraycopy(tmpCopy,0,cache,0,cacheLen - readLen);
            cacheLen -=readLen;
        }else {
            readLen = cacheLen;
            System.arraycopy(cache,0,buffer,off,readLen);
            cacheLen = 0;
        }
        return readLen;
    }

    public synchronized byte[] popAll() {
        byte[] retByte = new byte[cacheLen];
        int ret = pop(retByte,0,retByte.length);
        if(ret == retByte.length){
            return retByte;
        }
        return null;
    }

    public synchronized void clear() {
        cacheLen = 0;
        cache = null;
        tmpCopy = null;
    }

    public synchronized int getCacheLen()
    {
        return cacheLen;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/java/myaudiorecord/utils/PcmData.java

```
package myaudiorecord.utils;

import android.media.AudioFormat;

/**
 * Created by chengkai on 18-1-26.
 *
 */

public class PcmData {

    private byte[] bytesStereo = null;
    private byte[] rightByts = null;
    private byte[] leftByts = null;
    private int bytesStereoLen = 0;

    public byte[] reSampleBuffer = null;

    public PcmData()
    {
        bytesStereoLen = 1;
        this.rightByts = new byte[bytesStereoLen];
        this.leftByts = new byte[bytesStereoLen];
    }

    private int samplesRate = 0;
    private int samplesBits = 0;
    private int channels = 0;
    public boolean load(byte[] buffer, int len, int samplesRate ,int samplesBits,int channels)
    {
        if(buffer == null || buffer.length < len)
            return false;
        this.samplesRate = samplesRate;
        this.samplesBits = samplesBits;
        this.channels = channels;
        switch (channels){
            case  AudioFormat.CHANNEL_IN_STEREO:{
                //拆分左右声道
                bytesStereo = buffer;
                bytesStereoLen = len;
                split(bytesStereo,len,samplesBits);
                break;
            }
            case  AudioFormat.CHANNEL_IN_MONO:{
                bytesStereo = null;
                bytesStereoLen = len*2;
                this.rightByts = buffer;
                this.leftByts = buffer;
                break;
            }
            default:
                break;
        }
        return true;
    }


    private void split(byte[] buffer, int len, int samplesBits){
        if(buffer == null)
            return;
        if(rightByts == null || leftByts == null ||
                rightByts.length < len/2 || leftByts.length < len/2){
            rightByts = new byte[len/2];
            leftByts = new byte[len/2];
        }

        int i = 0;
        switch (samplesBits){
            case AudioFormat.ENCODING_PCM_16BIT:
                for (i = 0; i < len; i+=4) {
                    if((i + 3) < buffer.length){
                        leftByts[i/2 + 0] = buffer[i + 0];
                        leftByts[i/2 + 1] = buffer[i + 1];
                        rightByts[i/2 + 0] = buffer[i + 2];
                        rightByts[i/2 + 1] = buffer[i + 3];
                    }
                }
                break;
            case AudioFormat.ENCODING_PCM_8BIT:
                for (i = 0; i < len; i+=2) {
                    if((i + 1) < buffer.length){
                        leftByts[i/2 + 0] = buffer[i + 0];
                        rightByts[i/2 + 0] = buffer[i + 1];
                    }
                }
                break;
            default:
                return;
        }
    }
    //辗转相除获取分子分母
    private int GetMaxCommonDivisor(int maxnum,int minnum)
    {
        int temp = 0;
        /*使得max中存放较大的数,min存放较小的数*/
        if(maxnum < minnum) {
            temp = minnum;
            minnum = maxnum;
            maxnum = temp;
        }
        while(maxnum % minnum != 0) {
            temp = minnum;
            minnum = maxnum % minnum;
            maxnum = temp;
        }
        return minnum;
    }

    public int reSample(int needSampleRate,int needChannel)
    {
        int dstPos = 0;
        int bits = 0;
        byte[] dealBuffer = null;
        int dealBufferLen = 0;
        switch (needChannel) {
            case AudioFormat.CHANNEL_IN_STEREO:{
                bits = 4;
                dealBufferLen = bytesStereoLen;
                dealBuffer = bytesStereo;
                break;
            }
            case AudioFormat.CHANNEL_IN_LEFT:{
                bits = 2;
                dealBufferLen = bytesStereoLen/2;
                dealBuffer = leftByts;
                break;
            }
            case AudioFormat.CHANNEL_IN_MONO:
            case AudioFormat.CHANNEL_IN_RIGHT:{
                bits = 2;
                dealBufferLen = bytesStereoLen/2;
                dealBuffer = rightByts;
                break;
            }
            default:{
                break;
            }
        }
        if(dealBufferLen == 0 || dealBuffer == null)
            return 0;
        if(reSampleBuffer == null || reSampleBuffer.length < dealBufferLen){
            reSampleBuffer = new byte[dealBufferLen];
        }
        int maxCommonDivisor = GetMaxCommonDivisor(samplesRate,needSampleRate);
        int rate_out = needSampleRate/maxCommonDivisor;//倍率  分子
        int rate_in = samplesRate/maxCommonDivisor;//倍率  分母
        if(rate_out >= rate_in){
            System.arraycopy(dealBuffer,0,reSampleBuffer,0,dealBufferLen);
            return dealBufferLen;
        }
        for (int i = 0;i < dealBufferLen;i+=(bits*rate_in)){
            if((i + rate_out*bits) < dealBufferLen){
                System.arraycopy(dealBuffer,i,reSampleBuffer,dstPos,rate_out*bits);
                dstPos+=rate_out*bits;
            }
        }
        return dstPos;
    }
}

```
## /Users/thunder/mycode/rn/android/app/src/main/res/drawable/green_background.xml

```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <corners android:radius="8dp" /> <!-- 设置圆角半径 -->
    <solid android:color="@color/green" /> <!-- 设置填充颜色 -->
</shape>
```
## /Users/thunder/mycode/rn/android/app/src/main/res/drawable/rn_edit_text_material.xml

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Copyright (C) 2014 The Android Open Source Project

     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at

          http://www.apache.org/licenses/LICENSE-2.0

     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License.
-->
<inset xmlns:android="http://schemas.android.com/apk/res/android"
       android:insetLeft="@dimen/abc_edit_text_inset_horizontal_material"
       android:insetRight="@dimen/abc_edit_text_inset_horizontal_material"
       android:insetTop="@dimen/abc_edit_text_inset_top_material"
       android:insetBottom="@dimen/abc_edit_text_inset_bottom_material">

    <selector>
        <!--
          This file is a copy of abc_edit_text_material (https://bit.ly/3k8fX7I).
          The item below with state_pressed="false" and state_focused="false" causes a NullPointerException.
          NullPointerException:tempt to invoke virtual method 'android.graphics.drawable.Drawable android.graphics.drawable.Drawable$ConstantState.newDrawable(android.content.res.Resources)'

          <item android:state_pressed="false" android:state_focused="false" android:drawable="@drawable/abc_textfield_default_mtrl_alpha"/>

          For more info, see https://bit.ly/3CdLStv (react-native/pull/29452) and https://bit.ly/3nxOMoR.
        -->
        <item android:state_enabled="false" android:drawable="@drawable/abc_textfield_default_mtrl_alpha"/>
        <item android:drawable="@drawable/abc_textfield_activated_mtrl_alpha"/>
    </selector>

</inset>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/layout/custom_marquee_item.xml

```
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/marquee_text"
    android:textColor="@color/white"
    android:textSize="30sp"
    android:singleLine="true"
    android:gravity="center"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />

```
## /Users/thunder/mycode/rn/android/app/src/main/res/layout/launch_screen.xml

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
                android:layout_width="match_parent"
                android:background="@drawable/launch_screen"
                android:layout_height="match_parent">
<!--    <ImageView android:layout_width="match_parent" android:layout_height="match_parent" android:src="@drawable/launch_screen" android:scaleType="centerCrop" />-->
</RelativeLayout>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/layout/video_fullscreen.xml

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/video_fullscreen_layout"
    android:layout_width="match_parent"
    android:background="@color/black"
    android:layout_height="match_parent">
    <com.youth.banner.Banner
        android:id="@+id/banner_marquee_text"
        android:layout_width="match_parent"
        android:layout_marginTop="10dp"
        android:layout_height="50dp" />
    <LinearLayout
            android:id="@+id/loading_show"
            android:visibility="gone"
            android:layout_width="500dp"
            android:layout_height="178dp"
            android:layout_centerInParent="true"
            android:orientation="vertical"
            android:background="@drawable/play_show"
    >
        <TextView
                android:id="@+id/song_name"
                android:layout_marginStart="125dp"
                android:layout_marginTop="50dp"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:textSize="26sp"
                android:textColor="#902721"
                android:text=""
        />
        <TextView
                android:id="@+id/singer_name"
                android:layout_marginStart="125dp"
                android:layout_marginTop="8dp"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:textSize="18sp"
                android:textColor="@color/white"
                android:text=""
        />

    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="10dp"
        android:layout_alignParentEnd="true"
        android:gravity="center"
        android:layout_marginTop="70dp"
        android:layout_marginEnd="20dp"
        android:background="@drawable/green_background"
        android:orientation="vertical">
        <ImageView
            android:id="@+id/qrCodeImageView"
            android:padding="0dp"
            android:layout_width="150dp"
            android:layout_height="150dp"/>
        <TextView
            android:layout_marginTop="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textSize="18sp"
            android:textColor="@color/white"
            android:text="微信扫码点歌"
            />
    </LinearLayout>
</RelativeLayout>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/values/colors.xml

```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="primary_dark">#000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="green">#FF07C160</color>
    <color name="black">#FF000000</color>
</resources>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/values/strings.xml

```
<resources>
    <string name="app_name">雷石K歌</string>
</resources>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/values/styles.xml

```
<resources>

    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.ReactNative.AppCompat.Light.NoActionBar.FullScreen">
        <!-- Customize your theme here. -->
        <item name="android:editTextBackground">@drawable/rn_edit_text_material</item>
        <!--设置透明背景-->
        <item name="android:windowIsTranslucent">true</item>
    </style>

</resources>

```
## /Users/thunder/mycode/rn/android/app/src/main/res/xml/network_security_config.xml

```
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <base-config cleartextTrafficPermitted="true" />
</network-security-config>

```
## /Users/thunder/mycode/rn/babel.config.js

```
module.exports = {
  plugins: [
    [
      'module-resolver',
      {
        alias: {
          "react-native-sqlite-storage": "react-native-quick-sqlite"
        },
      },
    ],
    ['@babel/plugin-proposal-decorators', {legacy: true}],
    'react-native-reanimated/plugin',
  ],
  presets: ['module:@react-native/babel-preset'],
};

```
## /Users/thunder/mycode/rn/components/Card.tsx

```
import React, { forwardRef, memo } from "react";
import { ImageBackground, StyleSheet, Text } from "react-native";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function Card(props: CardProps, ref: any) {
    return <TouchFocusHighlight
        ref={ref}
        scaleNumber={props.type === "song" ? 1.05 : undefined}
        focusName={props.type}
        onPress={() => props.onHandlePress(props.type, props.title)}
        nextFocusLeft={props?.nextFocusLeft}
        nextFocusRight={props?.nextFocusRight}
        nextFocusUp={props?.nextFocusUp}
        nextFocusDown={props?.nextFocusDown}
        style={[styles.ListItem, props.style]}>
        <ImageBackground source={props.source} resizeMode="stretch" style={styles.ListItemImage}>
            {
                props.type !== "banner" && <Text style={[styles.ListItemText, props.textStyle]}>{props.title}</Text>
            }
        </ImageBackground>
    </TouchFocusHighlight>;
}

const styles = ScaledSheet.create({

    ListItem: {
        flex: 1,
        borderRadius: '6@ms1',
        overflow: "hidden"
    },
    ListItemImage: {
        flex: 1,
        justifyContent: "center",
    },
    ListItemText: {
        fontSize: '17@ms1',
        color: "#fff",
        fontWeight: "bold",
        paddingLeft: '5@ms1',
        letterSpacing: 3
    }
});
export default memo(forwardRef(Card));

```
## /Users/thunder/mycode/rn/components/Category.tsx

```
import React, { memo, useEffect, useState } from "react";
import { ImageBackground, InteractionManager, StyleSheet, Text, View } from "react-native";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { moderateScale, ScaledSheet } from "react-native-size-matters";
function Category(props: any) {
    const [categoryWidth, setCategoryWidth] = useState(0);
    const [categoryHeight, setCategoryHeight] = useState(0);
    const [activeCategory, setActiveCategory] = useState<any>({});
    const handleChange = (item: any) => {
        setActiveCategory(item)
        InteractionManager.runAfterInteractions(() => {
            // 异步操作
            props.onChange(item)
        });
    }
    useEffect(() => {
        if (props.category) {
            if(props.activeCategory) {
                setActiveCategory(props.activeCategory)
            } else {
                setActiveCategory(props.category[0])
            }
        }
    },[props.category,props.activeCategory])
    return <View style={styles.category} onLayout={(e) => {
        setCategoryWidth(e.nativeEvent.layout.width);
        setCategoryHeight(e.nativeEvent.layout.height);
    }}>
        {
            props.category?.map((item: any, index: number) => {
                return <TouchFocusHighlight
                    focusName={(item.moduleId || item.id).toString()}
                    key={index}
                    style={{
                        width: (categoryWidth - moderateScale(23,1)) / 4,
                        borderRadius: moderateScale(3,1),
                        overflow: "hidden",
                        height: (categoryHeight - moderateScale(14,1)) / 2,
                        backgroundColor: item.bgImg && activeCategory?.moduleId === item.moduleId ? "#2089dc" : "transparent",
                    }}
                    onPress={() => handleChange(item)}>
                    {
                        item.bgImg ? <ImageBackground style={{
                            flex: 1,
                            borderRadius: moderateScale(3,1),
                            alignItems: "center",
                            justifyContent: "flex-end"
                        }} source={item.bgImg}>
                            <Text numberOfLines={1} style={{ fontSize: moderateScale(13,1), backgroundColor: "rgba(0,0,0,0.5)", color: "#ffffff",width:"100%",textAlign:"center" }}>{item.moduleName}</Text>
                        </ImageBackground> : <View style={{
                            backgroundColor: activeCategory?.id === item.id ? "#2089dc" : "#4f548f",
                            flex: 1,
                            borderRadius: moderateScale(3,1),
                            overflow: "hidden",
                            alignItems: "center",
                            justifyContent: "center"
                        }}><Text numberOfLines={1} style={{ fontSize: moderateScale(13,1), color: "#ffffff" }}>{item.name}</Text></View>
                    }
                </TouchFocusHighlight>;
            })
        }
    </View>
}
const styles = ScaledSheet.create({
    category: {
        flex:1,
        flexDirection: "row",
        flexWrap: "wrap",
        alignItems: "center",
        backgroundColor: "#3D4170",
        overflow: "hidden",
        borderRadius: '3@ms1',
        padding:'5@ms1',
        gap: '4@ms1',
        marginTop: '5@ms1'
    },
})
export default memo(Category);

```
## /Users/thunder/mycode/rn/components/CategoryList.tsx

```
import React, { memo, useCallback, useEffect, useState } from "react";
import AsyncStorage from "@react-native-async-storage/async-storage";
import { request } from "../libs/util.ts";
import { Image, View } from "react-native";
import {company} from "../config.json";
import { FlashList } from "@shopify/flash-list";
import { ListItem } from "@rneui/themed";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import FastImage from "react-native-fast-image";
import {navigate} from "../libs/RootNavigation";
import { moderateScale } from "react-native-size-matters";

function CategoryList(props:any) {
    const [tabData, setTabData] = useState<any>([]);
    const getTabData = async () => {
        const token = await AsyncStorage.getItem("token");
        // @ts-ignore
        request(`${global.url}/vodc/topic/songlist?token=${token}&topicId=${props.topicId}&company=${company}`).then(res => {
            res.data.length && setTabData(res.data)
        });
    };
    const handleClick = (item: any) => {
        navigate("List", { type: "song", categoryId: item.id, name:`分类 & ${props.name} & ${item.name}`  })
    };
    const renderItem = useCallback(({ item, index }: { item: any; index: number }) => <RenderChild item={item}
                                                                                                   index={index}
                                                                                                   onItemClick={handleClick} />, [props.name]);
    const keyExtractor = useCallback((item: any, index: number) => item.id, []);
    useEffect(()=> {
        props.topicId && getTabData()
    },[props.topicId])
    return <FlashList
        data={tabData}
        numColumns={3}
        keyExtractor={keyExtractor}
        estimatedItemSize={moderateScale(100,1)}
        renderItem={renderItem}
        ListEmptyComponent={() => <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
            <Image resizeMode="contain" style={{ width: moderateScale(200), height: moderateScale(200) }}
                   source={require("../assets/imgs/empty.png")}></Image></View>}
        onEndReachedThreshold={1}
    />
}
interface RenderChildProps {
    item: any;
    index: number;
    onItemClick: (item: any) => void;
}

class RenderChild extends React.Component<RenderChildProps> {
    state = {
        loading: false,
        error: false
    };
    componentDidUpdate(prevProps: Readonly<RenderChildProps>, prevState: Readonly<{}>, snapshot?: any) {
        if (prevProps.item?.id !== this.props.item?.id) {
            this.setState({ error: false });
        }
    }
    render() {
        return <ListItem key={this.props.index} containerStyle={{
            backgroundColor: "transparent",
            flexDirection: "column",
            justifyContent: "center",
        }}>
            <TouchFocusHighlight
                focusName={"singerItem" + this.props.index}
                style={{
                    borderRadius: moderateScale(4,1),
                    width: moderateScale(80,1),
                    height: moderateScale(80,1),
                    overflow: "hidden"
                }}
                onPress={() => {
                    this.props.onItemClick(this.props.item);
                }}>
                {/*{this.state.loading && <Skeleton circle  width={80} height={80} animation="wave" />}*/}
                <FastImage style={{ width: moderateScale(80,1), height: moderateScale(80,1) }} onError={() => this.setState({ error: true })}
                           onLoadStart={() => this.setState({ loading: true })}
                           onLoadEnd={() => this.setState({ loading: false })}
                           source={this.state.error ? require("../assets/imgs/user.png") : {
                               uri: this.props.item.img,
                               priority: FastImage.priority.high
                           }} resizeMode={FastImage.resizeMode.contain} />
                <ListItem.Title numberOfLines={1} style={{
                    fontSize: moderateScale(11,1),
                    color: "#fff",
                    textAlign: "center",
                    position: "absolute",
                    backgroundColor: "rgba(0,0,0,0.5)",
                    width: moderateScale(80,1),
                    bottom: 0,
                    paddingVertical: moderateScale(3,1)
                }}>{this.props.item.name}</ListItem.Title>
            </TouchFocusHighlight>

        </ListItem>;
    }
}
export default memo(CategoryList)

```
## /Users/thunder/mycode/rn/components/ExitDialog.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useRef, useState } from "react";
import { findNodeHandle, StyleSheet, Text, TouchableHighlight, useTVEventHandler, View } from "react-native";
import { focus } from "@wouterds/react-native-tv-focus";
import LinearGradient from "react-native-linear-gradient";
import RNExitApp from "react-native-exit-app";
import { Dialog } from "@rneui/themed";
import { useAppDispatch } from "../store";
import { setHasDialog } from "../store/common.ts";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function ExitDialog(props: any, ref: any) {
    const dispatch = useAppDispatch();
    const [isVisible, setIsVisible] = useState(false);
    const dialogRef = useRef<any>();
    useImperativeHandle(ref, () => ({
        show: () => {
            setIsVisible(true);
        },
        isVisible
    }))
    const myTVEventHandler = useCallback((evt:any) => {
        if(evt.eventType === 'down' || evt.eventType === 'right') {
            if(isVisible) {
                focus(findNodeHandle(dialogRef.current));
            }
        }
    }, [isVisible]);
    useTVEventHandler(myTVEventHandler);
    useEffect(() => {
        dispatch(setHasDialog(isVisible));
    }, [isVisible])
    return <Dialog  overlayStyle={styles.Overlay} isVisible={isVisible} onBackdropPress={()=>setIsVisible(false)}>
        <LinearGradient
            style={{flex: 1, padding: moderateScale(10), justifyContent: 'space-between'}}
            start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={{alignItems: 'center', justifyContent: 'center', flex: 1}}>
                <Text style={{fontSize: moderateScale(14,1), color: '#fff'}}>确认退出吗？</Text>
            </View>
            <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                <TouchableHighlight style={styles.exitBtn} underlayColor="#2089dc" onPress={()=>setIsVisible(false)}>
                    <Text style={styles.exitBtnText}>取消</Text>
                </TouchableHighlight>
                <TouchableHighlight ref={dialogRef} style={[styles.exitBtn,{ marginLeft: moderateScale(5,1) }]} underlayColor="#2089dc" onPress={() =>RNExitApp.exitApp()}>
                    <Text style={styles.exitBtnText}>退出</Text>
                </TouchableHighlight>
            </View>
        </LinearGradient>
    </Dialog>;
}
const styles = ScaledSheet.create({
    Overlay: {
        width: '225@s',
        height: '100@s',
        padding: 0,
        borderRadius: '4@ms1',
        overflow: 'hidden'
    },
    exitBtn: {
        paddingVertical:'3@ms1',
        paddingHorizontal:'5@ms1',
        borderRadius:'2@ms1'
    },
    exitBtnText: {
        fontSize:'12@ms1',
        color: '#fff'
    }
})
export default memo(forwardRef(ExitDialog))

```
## /Users/thunder/mycode/rn/components/Letter.tsx

```
import React, { forwardRef, memo, useImperativeHandle, useRef, useState } from "react";
import { letters, figures } from "../libs/util.ts";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { findNodeHandle, StyleSheet, Text, View } from "react-native";
import { moderateScale, ScaledSheet } from "react-native-size-matters";
function Letter(props:any,ref:any) {
    const [type, setType] = useState('letter');
    const [height, setHeight] = useState(0);
    const [layoutHeight, setLayoutHeight] = useState(0);
    const lettersRef = useRef<any>([]);
    const switchRef = useRef<any>();
    useImperativeHandle(ref,()=>({
        firstFocus:findNodeHandle(lettersRef.current[0])
    }));
    return <View style={[styles.letter,{paddingVertical: moderateScale(5,1) }]} onLayout={(e)=> setLayoutHeight(e.nativeEvent.layout.height)}>
        { type === 'letter' ? letters.map((item: any, index: number) => {
            return <TouchFocusHighlight
                ref={ref=>lettersRef.current[index] = ref}
                key={index}
                nextFocusUp={index <= 8 ? props.bkspNativeTag : findNodeHandle(lettersRef.current[index - 9])}
                nextFocusDown={index >=16 ? undefined : findNodeHandle(lettersRef.current[index + 9])}
                nextFocusLeft={index%9 === 0 ? props.inputNativeTag : findNodeHandle(lettersRef.current[index - 1])}
                nextFocusRight={index%9 === 8 ? undefined : findNodeHandle(lettersRef.current[index + 1])}
                noBorder
                noScale
                focusName={'letter-' +item}
                style={{
                    width: "11.1111%",
                    height:(layoutHeight-moderateScale(5,1))/3,
                    alignItems: "center",
                    justifyContent: "center",
                    borderRadius: moderateScale(2,1),
                }}
                activeColor="#2089dc"
                onPress={() => {
                    props.onSearch(item)
                }}>
                <Text style={styles.letterText}>{item}</Text>
            </TouchFocusHighlight>
        }): figures.map((item: any, index: number) => {
            return <TouchFocusHighlight
                ref={ref=>lettersRef.current[index] = ref}
                key={index}
                nextFocusUp={index <= 8 ? props.bkspNativeTag : findNodeHandle(lettersRef.current[index - 9])}
                nextFocusDown={index >=16 ? undefined : findNodeHandle(lettersRef.current[index + 9])}
                nextFocusLeft={index%9 === 0 ? props.inputNativeTag : findNodeHandle(lettersRef.current[index - 1])}
                nextFocusRight={index%9 === 8 ? undefined : findNodeHandle(lettersRef.current[index + 1])}
                noBorder
                noScale
                focusName={'figure-' +item}
                style={{
                    width: "11.1111%",
                    height:(layoutHeight-moderateScale(5,1))/3,
                    alignItems: "center",
                    justifyContent: "center",
                    borderRadius: moderateScale(2,1),
                }}
                activeColor="#2089dc"
                onPress={() => {
                    props.onSearch(item)
                }}>
                <Text style={{color: "white", fontSize: moderateScale(13,1)}}>{item}</Text>
            </TouchFocusHighlight>
        })}
        <TouchFocusHighlight
            ref={switchRef}
            noBorder
            noScale
            focusName='letter-switch'
            onLayout={(e)=> setHeight(e.nativeEvent.layout.width)}
            style={{
                position: "absolute",
                width: "11.1111%",
                height:(layoutHeight-moderateScale(5,1))/3,
                alignItems: "center",
                justifyContent: "center",
                borderRadius: moderateScale(2,1),
                right: 0,
                bottom: 0
            }}
            activeColor="#2089dc"
            onPress={()=> setType(type === 'letter' ? 'figure' : 'letter')}>
            <Text style={{color: "white", fontSize: moderateScale(10,1), marginLeft: -6}}> {type === 'letter' ? '123' : 'abc'}</Text>
        </TouchFocusHighlight>
    </View>
}
const styles = ScaledSheet.create({
    letter: {
        flexDirection: "row",
        flexWrap: "wrap",
        flex: 1,
        alignItems: "center",
        paddingVertical: '5@ms1',
    },
    letterText: {
        color: "white",
        fontSize: '20@ms'
    },
})
export default memo(forwardRef(Letter), (prev, next) => {
    return prev.inputNativeTag === next.inputNativeTag && prev.bkspNativeTag === next.bkspNativeTag
});

```
## /Users/thunder/mycode/rn/components/LicenseDialog.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useRef, useState } from "react";
import LinearGradient from "react-native-linear-gradient";
import { findNodeHandle, StyleSheet, Text, useTVEventHandler, View, TextInput, Keyboard } from "react-native";
import { Dialog, Icon } from "@rneui/themed";
import { focus } from "@wouterds/react-native-tv-focus";
import RNExitApp from "react-native-exit-app";
import { letters as letterList, figures } from "../libs/util.ts";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import Animated,{ Easing, useAnimatedStyle, useSharedValue, withTiming } from "react-native-reanimated";
import { company } from "../config.json";
import { useAppDispatch } from "../store";
import { setHasDialog, setIsActive } from "../store/common.ts";
import { moderateScale, s, ScaledSheet } from "react-native-size-matters";

function LicenseDialog(props: any, ref: any) {
    const dispatch = useAppDispatch();
    const [isVisible, setIsVisible] = useState(false);
    const [license, setLicense] = useState('');
    const [showKeyboard, setShowKeyboard] = useState(false);
    const [letters, setLetters] = useState(letterList.concat(figures));
    const licenseInputRef = useRef<any>();
    const confirmBtn = useRef<any>();
    const transLateYAnim = useSharedValue<number>(moderateScale(150,1));
    const animatedTransLateStyles = useAnimatedStyle(() => ({
        transform: [{ translateY: transLateYAnim.value }],
    }));
    const lettersRef = useRef<any>([]);
    const keyboardStatus = useRef(true);
    const isTouching = useRef(false);
    const textInputRef = useRef<any>();
    const updateText = (text: string|number) => {
        if (text === "bksp") {
            setLicense(license.substring(0, license.length - 1));
        } else if (text === "del") {
            setLicense("");
        } else {
            setLicense(license + text);
        }

    }
    const switchKeyboard = () => {
        keyboardStatus.current = !keyboardStatus.current;
        setLetters(letterList.map(item=> keyboardStatus.current?item.toUpperCase():item.toLowerCase()).concat(figures))
    }
    useImperativeHandle(ref, () => ({
        show(license?: string) {
            dispatch(setIsActive({
                status: true,
                errMsg: ""
            }));
            setIsVisible(true);
            if(license) {
                setLicense(license);
            }
        },
        hide() {
            setIsVisible(false);
        },
        focus() {
            setShowKeyboard(true);
        },
        isVisible
    }))
    const myTVEventHandler = useCallback((evt:any) => {
        if(evt.eventType === 'down' || evt.eventType === 'up' || evt.eventType === 'left' || evt.eventType === 'right') {
            if(isTouching.current) {
                focus(findNodeHandle(licenseInputRef?.current));
                isTouching.current = false;
            }
        }
    }, [isVisible]);
    useTVEventHandler(myTVEventHandler);
    useEffect(() => {
        if(company !== 'taide') {
            if(showKeyboard) {
                transLateYAnim.value = withTiming(0, { duration: 200, easing: Easing.linear})
            } else {
                transLateYAnim.value = withTiming(moderateScale(150,1), { duration: 200, easing: Easing.linear})
            }
        } else {
            setTimeout(() => {
                if(showKeyboard) {
                    if(!Keyboard.isVisible()) {
                        textInputRef.current?.focus();
                    }
                } else {
                    textInputRef.current?.blur();
                }
            }, 200)
        }
    }, [showKeyboard])

    useEffect(() => {
        if(isVisible) {
            focus(findNodeHandle(licenseInputRef?.current));
        }
        dispatch(setHasDialog(isVisible));
    }, [isVisible])
    return <>
        <Dialog overlayStyle={styles.Overlay} animationType="none" backdropStyle={{backgroundColor: 'rgba(0,0,0,1)'}} isVisible={isVisible} onBackdropPress={()=>false}>
            <LinearGradient
                style={{ paddingVertical: moderateScale(5,1),paddingHorizontal: moderateScale(10), justifyContent: 'space-between',marginTop: -moderateScale(50,1), width: s(250), height: s(120), borderRadius: moderateScale(4,1)}}
                start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 1 }}
                locations={[ 0, 0.5, 1 ]}
                colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
            >
                <View style={{alignItems: 'center', justifyContent: 'center', flex: 1}}>
                    <Text style={{color: '#fff', fontSize: moderateScale(13,1), marginBottom:moderateScale(10,1)}}>输入License</Text>
                    <TouchFocusHighlight
                        ref={licenseInputRef}
                        style={{
                            width: '90%',
                            height: moderateScale(27,1),
                            paddingLeft: moderateScale(5,1),
                            justifyContent: 'center',
                            borderWidth: 1,
                            borderColor: 'rgba(255,255,255,0.7)',
                            borderRadius: moderateScale(4,1),
                            }}
                        onHandleFocus={()=>setShowKeyboard(true)}
                        onPress={()=>setShowKeyboard(true)}>
                        {
                            <TextInput value={license} editable={company === 'taide'} ref={textInputRef} style={{color: '#fff', fontSize: moderateScale(10,1)}} onChangeText={(text)=> {
                                setLicense(text);
                            }} />
                        }

                    </TouchFocusHighlight>
                </View>
                <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                    <TouchFocusHighlight
                        noBorder
                        noScale
                        style={styles.exitBtn}
                        nextFocusLeft={findNodeHandle(licenseInputRef.current)}
                        nextFocusUp={findNodeHandle(licenseInputRef.current)}
                        activeColor="#2089dc"
                        onPress={() => {
                        RNExitApp.exitApp()
                    }}>
                        <Text style={styles.exitBtnText}>退出</Text>
                    </TouchFocusHighlight>
                    <TouchFocusHighlight
                        ref={confirmBtn}
                        noBorder
                        noScale
                        style={[styles.exitBtn,{ marginLeft: moderateScale(5,1) }]}
                        nextFocusUp={findNodeHandle(licenseInputRef.current)}
                        nextFocusRight={findNodeHandle(confirmBtn.current)}
                        activeColor="#2089dc"
                        onPress={() => {
                        props.onConfirm(license);
                            setShowKeyboard(false);
                    }}>
                        <Text style={styles.exitBtnText}>确认</Text>
                    </TouchFocusHighlight>
                </View>
            </LinearGradient>
            <Animated.View style={[ styles.Letter, animatedTransLateStyles] }>
                {letters.map((letter, index) => {
                    return (
                        <TouchFocusHighlight
                            ref={el => lettersRef.current[index] = el}
                            noBorder
                            noScale
                            style={{
                            width: moderateScale(30,1),
                            height: moderateScale(30,1),
                            alignItems: "center",
                            justifyContent: "center",
                            marginBottom: moderateScale(5,1),
                            marginRight: moderateScale(5,1),
                            borderRadius: moderateScale(2,1),
                        }} key={index} activeColor="#2089dc"
                            onPress={(event) =>  updateText(letter)}
                            onHandlePressOut={()=> isTouching.current = true}>
                            <Text style={styles.LetterText}>{letter}</Text>
                        </TouchFocusHighlight>
                    );
                })}
                <View style={styles.clearBtnBox}>
                    <TouchFocusHighlight
                        noBorder
                        noScale
                        style={styles.clearBtn}
                        activeColor="#2089dc"
                        onPress={switchKeyboard}
                        onHandlePressOut={()=> isTouching.current = true}>
                        <>
                            <Text style={{ fontSize: 26, color: '#fff' }}>Aa</Text>
                        </>
                    </TouchFocusHighlight>
                    <TouchFocusHighlight
                        style={styles.clearBtn}
                        activeColor="#2089dc"
                        noBorder
                        noScale
                        onPress={(event) => updateText("bksp")}
                        onHandlePressOut={()=> isTouching.current = true}>
                        <>
                            <Icon
                                size={moderateScale(16,1)}
                                name="backspace-outline"
                                type="ionicon"
                                color="#fff"
                            />
                            {/*<Text style={{ fontSize: 20, color: '#fff' }}>退格</Text>*/}
                        </>
                    </TouchFocusHighlight>
                    <TouchFocusHighlight
                        noBorder
                        noScale
                        style={styles.clearBtn}
                        activeColor="#2089dc"
                        onPress={(event) => updateText("del")}
                        onHandlePressOut={()=> isTouching.current = true}>
                        <>
                            <Icon
                                size={moderateScale(16,1)}
                                name="trash-outline"
                                type="ionicon"
                                color="#fff"
                            />
                            {/*<Text style={{ fontSize: 20, color: '#fff' }}>清空</Text>*/}
                        </>
                    </TouchFocusHighlight>
                    <TouchFocusHighlight
                        noBorder
                        noScale
                        style={[styles.clearBtn,{
                        paddingHorizontal: moderateScale(5,1),
                        width: moderateScale(40,1),
                        height: moderateScale(25,1),
                        backgroundColor: 'rgba(32,137,220,0.71)'
                    }]}
                        activeColor="#2089dc"

                        onPress={(event) => {
                            focus(findNodeHandle(confirmBtn.current))
                            setShowKeyboard(false)
                        }}
                        onHandlePressOut={()=> isTouching.current = true}>
                        <Text style={{ fontSize: moderateScale(12,1), color: '#fff' }}>完成</Text>
                    </TouchFocusHighlight>
                </View>
            </Animated.View>
        </Dialog>
    </>;
}
const styles = ScaledSheet.create({
    Overlay: {
        width: '100%',
        height: '100%',
        padding: 0,
        overflow: 'hidden',
        alignItems: 'center',
        justifyContent: 'center',
        backgroundColor: 'transparent',
    },
    exitBtn: {
        paddingVertical:'3@ms1',
        paddingHorizontal:'5@ms1',
        borderRadius:'2@ms1',
    },
    exitBtnText: {
        fontSize:'12@ms1',
        color: '#fff'
    },
    Letter: {
        flexDirection: "row",
        flexWrap: "wrap",
        position: "absolute",
        backgroundColor: "#646161",
        zIndex: 1,
        width: "100%",
        height: '110@ms1',
        bottom: 0,
        paddingVertical: '5@ms1',
        paddingHorizontal: '10@ms1',
    },
    LetterText: {
        fontSize: '16@ms1',
        color: "#fff",
    },
    clearBtnBox: {
        position: "absolute",
        right: '10@ms1',
        bottom: '10@ms1',
        flexDirection: "row",
        zIndex: 11,
        alignItems: "center",
    },
    clearBtn: {
        width: '30@ms1',
        height: '30@ms1',
        padding: '2@ms1',
        borderRadius: '2@ms1',
        alignItems: "center",
        justifyContent: "center",
        flexDirection: "row",
        marginLeft: '5@ms1',
    }
})
export default memo(forwardRef(LicenseDialog))

```
## /Users/thunder/mycode/rn/components/LinearGradientText.tsx

```
import React from "react";
import Svg, { Defs, LinearGradient, Stop, Text, Use } from "react-native-svg";
function LinearGradientText(props:any) {

    return <Svg width={props.width} height={props.height} style={props.style} viewBox={`0 0 ${props.width} ${props.height}`}>
        <Defs>
            <LinearGradient
                id="Gradient"
                gradientUnits="userSpaceOnUse"
                x1="0"
                y1="0"
                x2={props.x2}
                y2="0">
                <Stop offset="0" stopColor={props.colors[0]} />
                <Stop offset="1" stopColor={props.colors[1]} />
            </LinearGradient>
            <Text
                id="Text"
                x={props.x}
                y={props.y}
                dominant-baseline="middle"
                fontSize={props.size}
                textAnchor="middle">
                {props.text}
            </Text>
        </Defs>
        <Use href="#Text" fill="url(#Gradient)" />
    </Svg>

}

export default LinearGradientText;

```
## /Users/thunder/mycode/rn/components/Loading.tsx

```
import React, { forwardRef, memo, useImperativeHandle, useState } from "react";
import PlayShow from "../assets/imgs/playShow.svg";
import { StyleSheet, Text, View } from "react-native";
import { moderateScale } from "react-native-size-matters";

function Loading(props: any, ref: any) {
    const [loading, setLoading] = useState(false);
    useImperativeHandle(ref, () => ({
        setLoading
    }))
    return (
        <View style={[styles.loading, {
            width: props?.isFullscreen ? moderateScale(250,1) : moderateScale(125,1),
            height:  props?.isFullscreen ? moderateScale(89,1) : moderateScale(50,1),
            opacity: loading ? 1 : 0,
            transform: [{ translateX:  props?.isFullscreen ? -moderateScale(125,1) : -moderateScale(62.5,1) }, { translateY:  props?.isFullscreen ? -moderateScale(44.5,1) : -moderateScale(25,1) }]
        }]}>
            <PlayShow style={{
                position: "absolute",
                top: 0,
                left: 0,
                right: 0,
                bottom: 0
            }} />
            <Text style={{
                ...styles.loadingSongText, left:  props?.isFullscreen ? moderateScale(65,1) : moderateScale(32.5,1),
                top:  props?.isFullscreen ? moderateScale(25,1) : moderateScale(13,1),
                fontSize:  props?.isFullscreen ? moderateScale(12,1) : moderateScale(8,1)
            }}>{props?.musicName}</Text>
            <Text style={{
                ...styles.loadingSingerText, left:  props?.isFullscreen ? moderateScale(65,1) : moderateScale(32.5,1),
                top:  props?.isFullscreen ? moderateScale(47.5,1) : moderateScale(25,1),
                fontSize:  props?.isFullscreen ? moderateScale(8,1) : moderateScale(6,1)
            }}>{props?.singer}</Text>
        </View>
    )

}
const styles = StyleSheet.create({
    loading: {
        flex: 1,
        position: "absolute",
        left: "50%",
        top: "50%"
    },
    loadingSongText: {
        position: "absolute",
        color: "#902721"
    },
    loadingSingerText: {
        fontSize: moderateScale(8,1),
        color: "#fff",
        position: "absolute",
        left: moderateScale(65,1),
        top: moderateScale(47.5,1)

    },
})

export default memo(forwardRef(Loading), (prevProps, nextProps) =>
    prevProps.isFullscreen === nextProps.isFullscreen &&
    prevProps.musicName === nextProps.musicName &&
    prevProps.singer === nextProps.singer
)

```
## /Users/thunder/mycode/rn/components/Local.tsx

```
import React, { memo, useCallback, useEffect, useRef, forwardRef, useImperativeHandle } from "react";
import { useCallbackState } from "../hooks/useCallBackState";
import SongItem from "./SongItem";
import { getList, delSong, updateList } from "../libs/util";
import RNFS from "react-native-fs";
import Pagination from "./Pagination";
import { Image, NativeEventEmitter, NativeModules, View } from "react-native";
import { FlashList } from "@shopify/flash-list";
import { moderateScale } from "react-native-size-matters";

export default memo(forwardRef(function Local(props: any, ref) {
    const [songList, setSongList] = useCallbackState([]);
    const isAllRef = useRef(false);
    const listRef = useRef<any>();
    const listTotalRef = useRef([]);
    const currentPageRef = useRef(1);
    const paginationRef = useRef<any>();

    const getSongList = () => {
        isAllRef.current = false;
        getList(currentPageRef.current, 10, props.searchText).then((res: any) => {
            if (res.length < 10) {
                isAllRef.current = true;
            }
            res?.length && setSongList(listTotalRef.current.concat(res), (list: any) => {
                listTotalRef.current = list;
            });
        });

    };
    const scrollToIndex = (index: number) => {
        let timer = setTimeout(() => {
            listTotalRef.current.length && listRef.current?.scrollToIndex({
                index,
                animated: false
            });
            clearTimeout(timer);
        }, 200);
    };
    const pageChange = (type: string, state?: boolean) => {
        if (type === "prev") {
            if (paginationRef.current.page === 1) return;
            paginationRef.current?.go(paginationRef.current.page - 1);
            scrollToIndex((paginationRef.current.page - 2) * 5);
        } else {
            if (state) {
                if (!isAllRef.current) {
                    currentPageRef.current++;
                    getSongList();
                }
            } else {
                if (paginationRef.current.page * 5 >= listTotalRef.current.length) return;
                paginationRef.current?.go(paginationRef.current.page + 1);
                scrollToIndex(paginationRef.current.page * 5);
            }
        }
    };
    const handleViewableItemsChanged = useCallback((info: any) => {
        if (info.viewableItems[info.viewableItems.length - 4]) {
            paginationRef.current?.go(Math.floor(info.viewableItems[info.viewableItems.length - 4].index / 5) + 1);
        }
    }, []);
    const deleteSong = async (item: any) => {
        if (await RNFS.exists(item.path)) {
            await RNFS.unlink(item.path);
        }
        delSong(item.songid).then(() => {
            setSongList(songList.filter((song: any) => song.songid !== item.songid), (list: any) => {
                listTotalRef.current = list;
            });
        });
    };
    useImperativeHandle(ref, () => {
        return {
            reset: () => {
                paginationRef.current?.go(1);
                currentPageRef.current = 1;
                setSongList([], (list: any) => {
                    listTotalRef.current = list;
                });
                getSongList();
            }
        };
    });
    const renderItem = ({ item, index }: any) => <SongItem item={item} index={index} showDelBtn
                                                           onDelPress={() => deleteSong(item)} />;
    const keyExtractor = useCallback((item: any, index: number) => (item.songid || item.songId).toString() + index, []);
    // (<Swipeable key={item.songid} renderRightActions={()=> <RectButton onPress={()=> deleteSong(item)} style={{width: 70,backgroundColor: '#ff0000',height:76,alignItems:'center',justifyContent:'center',borderRadius:6,marginTop:10}}>
    //   <Text style={{fontSize:16, color:'#fff'}}>删除</Text>
    // </RectButton>}>
    //   <SongItem item={item} index={index} />
    // </Swipeable>);
    useEffect(() => {
        paginationRef.current?.go(1);
        currentPageRef.current = 1;
        setSongList([], (list: any) => {
            listTotalRef.current = list;
        });
        getSongList();
        const nativeEventEmitter = new NativeEventEmitter(NativeModules.RnUtilsModule);
        const sdCardListener = nativeEventEmitter.addListener('sdCardChange', async () => {
            await updateList();
            paginationRef.current?.go(1);
            currentPageRef.current = 1;
            setSongList([], (list: any) => {
                listTotalRef.current = list;
            });
            getSongList();
        })
        return () => {
            sdCardListener.remove();
        };
    }, [props.searchText]);

    return <View style={{ flex: 1, flexDirection: "row" }}>
        <FlashList
            data={songList}
            ref={(ref) => listRef.current = ref}
            onEndReached={() => {
                pageChange("next", true);
            }}
            keyExtractor={keyExtractor}
            estimatedItemSize={90}
            onViewableItemsChanged={handleViewableItemsChanged}
            renderItem={renderItem}
            ListEmptyComponent={() => <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
                <Image resizeMode="contain" style={{ width: moderateScale(200), height: moderateScale(200) }}
                       source={require("../assets/imgs/empty.png")}></Image></View>}
            onEndReachedThreshold={1}
        />
        <Pagination ref={paginationRef} onChange={pageChange} />
    </View>;
}), (prevProps, nextProps) => {
    return prevProps.searchText === nextProps.searchText;
});

```
## /Users/thunder/mycode/rn/components/Marquee.tsx

```
import React, { forwardRef, memo, useEffect, useState } from "react";
import Animated, {
    cancelAnimation,
    Easing, ReduceMotion,
    useAnimatedStyle,
    useSharedValue,
    withDelay,
    withRepeat,
    withTiming
} from "react-native-reanimated";
import { Dimensions, ScrollView, StyleSheet } from "react-native";

function Marquee(props:any, ref: any) {
    const [titleWidth, setTitleWidth] = useState(0);
    // 跑马灯需要移动的距离为平路宽度
    const transLateXAnim = useSharedValue<number>(Dimensions.get('window').width);
    const animatedTransLateStyles = useAnimatedStyle(() => ({
        transform: [{ translateX: transLateXAnim.value }],
    }));
    const animateStart = ()=> {
        transLateXAnim.value = withDelay(1000,withRepeat(
            withTiming(-titleWidth, { duration: 40000, easing: Easing.linear, reduceMotion:ReduceMotion.Never}),
            -1,
            false,
            undefined,
            ReduceMotion.Never
        ), ReduceMotion.Never);
    }
    useEffect(()=> {
        if(titleWidth && props.isFullScreen) {
            transLateXAnim.value = Dimensions.get('window').width;
            animateStart()
        } else {
            cancelAnimation(transLateXAnim)
        }
    }, [titleWidth, props.isFullScreen]);
    return <ScrollView scrollEnabled={false} contentContainerStyle={{minWidth: '100%'}} horizontal style={styles.TitleBar}>
        <Animated.Text numberOfLines={1} ellipsizeMode="clip" onLayout={(e)=> {
            setTitleWidth(e.nativeEvent.layout.width);
        }}  style={[styles.TitleBarText,animatedTransLateStyles] }>{props.text} </Animated.Text>
    </ScrollView>;
}
const styles = StyleSheet.create({
    TitleBar: {
        position: 'absolute',
        paddingVertical: 20,
        width: '100%'
    },
    TitleBarText: {
        color: '#1214ec',
        fontSize: 30,
        fontWeight: '700',
        textAlign: 'left',
        textShadowColor: '#fff',
        textShadowOffset: {width: 0, height: 1},
        textShadowRadius: 4,
    },
})
export default memo(forwardRef(Marquee))

```
## /Users/thunder/mycode/rn/components/OrderedDialog.tsx

```
import React, { forwardRef, memo,  useEffect, useImperativeHandle, useRef } from "react";
import LinearGradient from "react-native-linear-gradient";
import { findNodeHandle, Image, Text, TouchableHighlight,  View } from "react-native";
import { Dialog, Icon } from "@rneui/themed";
import { FlashList } from "@shopify/flash-list";
import SongItem from "./SongItem.tsx";
import { useAppDispatch, useAppSelector } from "../store";
import { focus } from "@wouterds/react-native-tv-focus";
import { setHasDialog } from "../store/common.ts";
import { moderateScale } from "react-native-size-matters";

function OrderedDialog(props: any, ref: any) {
    const dispatch = useAppDispatch();
    const [isVisible, setIsVisible] = React.useState(false);
    const {orderList} = useAppSelector(state=>state.common);
    const dialogCloseRef = useRef<any>()
    const renderItem = ({ item, index }: { item: any; index: number }) => <SongItem index={index} isOrder={true} item={item} key={index}/>
    useImperativeHandle(ref, () => ({
        show() {
            setIsVisible(true);
        },
        isVisible
    }))
    useEffect(()=>{
        if(isVisible) {
            focus(findNodeHandle(dialogCloseRef.current));
        }
        dispatch(setHasDialog(isVisible));
    }, [isVisible])
    return <Dialog isVisible={isVisible} overlayStyle={{padding: 0,overflow: 'hidden',borderRadius: moderateScale(4,1), height: '70%'}} onBackdropPress={()=>setIsVisible(false)}>
        <LinearGradient
            style={{flex: 1, paddingHorizontal: moderateScale(10,1)}}
            start={{ x : 0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0,0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={{height: moderateScale(40), backgroundColor: 'transparent', borderBottomWidth: 1, borderColor: 'rgba(255,255,255,0.2)', marginTop: moderateScale(5,1), borderRadius:moderateScale(3,1)}}>
                <Text style={{color: '#ffffff', fontSize: moderateScale(12,1), marginVertical: moderateScale(5,1)}}>已点歌曲</Text>
            </View>
            <TouchableHighlight ref={dialogCloseRef} style={{position: 'absolute', right: moderateScale(10,1), top: moderateScale(5,1),borderRadius:moderateScale(4,1), padding: moderateScale(4,1), alignItems: 'center', justifyContent: 'center'}} underlayColor="#2089dc" onPress={() => setIsVisible(false)}>
                <Icon
                    size={moderateScale(18,1)}
                    name='close-outline'
                    type='ionicon'
                    color='#ffffff'
                />
            </TouchableHighlight>
            <FlashList
                data={orderList}
                renderItem={renderItem}
                ListEmptyComponent={() => <View style={{alignItems: "center", justifyContent: "center", flex: 1}}>
                    <Image resizeMode="contain" style={{width: moderateScale(200), height: moderateScale(200)}} source={require('../assets/imgs/empty.png')}></Image>
                </View>}

                estimatedItemSize={moderateScale(43,1)} />

        </LinearGradient>
    </Dialog>;
}

export default memo(forwardRef(OrderedDialog))

```
## /Users/thunder/mycode/rn/components/Pagination.tsx

```
import React, { forwardRef, memo, useImperativeHandle, useRef, useState } from "react";
import { findNodeHandle, Text, View } from "react-native";
import { Icon } from "@rneui/themed";
import { moderateScale } from "react-native-size-matters";

import TouchFocusHighlight from "./TouchFocusHighlight.tsx";

interface Props {
    onChange: (type: string) => void;
}

function Pagination(props: Props,ref:any) {
    const [page, setPage] = useState(1);
    const prevRef = useRef<any>(null);
    const nextRef = useRef<any>(null);
    useImperativeHandle(ref, () => ({
        page,
        go:(index:number)=>{
            setPage(index)
        }
    }))
    return <View style={{
        marginLeft: moderateScale(10,1),
        flexDirection: "column",
        alignItems: "center",
        justifyContent: "center"
    }}>
        <TouchFocusHighlight
            focusName="prevPage"
            style={{ borderRadius: moderateScale(3,1) }}
            ref={prevRef}
            noBorder
            noScale
            nextFocusDown={findNodeHandle(nextRef.current)}
            nextFocusRight={findNodeHandle(prevRef.current)}
            activeColor="#2089dc"
            onPress={() => {
                props.onChange("prev");
            }}>
            <Icon
                size={moderateScale(25,1)}
                name="chevron-up-circle-outline"
                type="ionicon"
                color="#ffffff"
            />
        </TouchFocusHighlight>
        <Text style={{ color: "#ffffff", fontSize: moderateScale(12,1), marginVertical: moderateScale(25,1) }}>{page}</Text>
        <TouchFocusHighlight
            focusName="nextPage"
            style={{ borderRadius: moderateScale(3,1) }}
            ref={nextRef}
            noBorder
            noScale
            nextFocusUp={findNodeHandle(prevRef.current)}
            nextFocusRight={findNodeHandle(nextRef.current)}
            activeColor="#2089dc"
            onPress={() => {
                props.onChange("nextPage");
            }}>
            <Icon
                size={moderateScale(25,1)}
                name="chevron-down-circle-outline"
                type="ionicon"
                color="#ffffff"
            />
        </TouchFocusHighlight>
    </View>;
}

export default memo(forwardRef(Pagination));

```
## /Users/thunder/mycode/rn/components/Player.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useState } from "react";
import { setIsPlaying } from "../store/control.ts";
import { RCTVideo } from "../libs/components.ts";
import store, { useAppDispatch, useAppSelector } from "../store";
import { StyleSheet, Text, View } from "react-native";
import QRCode from "react-native-qrcode-svg";
import { moderateScale, s, ScaledSheet } from "react-native-size-matters";

function Player(props: any, ref: any) {
    const {config, current, orderList} = useAppSelector(state=>state.common);
    const [track, setTrack] = useState(1);
    const [isDualScreen, setIsDualScreen] = useState(false);
    const {playStatus,selectedAudioTrack} = useAppSelector(state=>state.control);
    const dispatch = useAppDispatch();
    const setCurrentTrack = useCallback(()=> {
        let index = 1;
        if (props.source.Music_ZTrack) { // Music_ZTrack:1 原唱在第一轨
            selectedAudioTrack ?
                (props.source.Music_ZTrack == 1 ? index = 1 : index = 2) : (props.source.Music_ZTrack == 1 ? index = 2 : index = 1);
        } else { // 不存在时默认第一轨原唱
            selectedAudioTrack ? index = 1 : index = 2;
        }
        setTrack(index);
    }, [selectedAudioTrack, props.source])
    const onDisplayChange = (e: any) => {
        setIsDualScreen(e.nativeEvent.dualScreen);
        props.onDisplayChanged(e.nativeEvent.dualScreen);
    }
    useEffect(()=>{
        setCurrentTrack();

    },[props.source, selectedAudioTrack])
    return <>
        <RCTVideo
            onVideoLoad={props.onLoad}
            ref={ref}
            onVideoPlaybackStateChanged={(e) => {
                dispatch(setIsPlaying(e.nativeEvent.isPlaying));
            }}
            qrcodeUrl={config?.sing_qr}
            name={props.name}
            title={current ?`正在播放：${current.singer || ""}   ${current.music_name}&_&下一曲：${orderList.length > 1 ? (orderList[1].singer || "") + "  " + orderList[1].music_name : "未点歌"}`: ""}
            onVideoProgress={(e) => props.onProgress(e.nativeEvent.currentTime)}
            volume={props.volume}
            selectedAudioTrack={track}
            onVideoDownloadComplete={props.onDownloadComplete}
            onDisplayChange={onDisplayChange}
            onVideoError={props.onVideoError}
            onVideoEnd={props.onNext}
            paused={!playStatus}
            source={props.source}
            style={{ flex: 1, width: "100%", height: "100%" }}
        />
        {
            config.sing_qr && !isDualScreen && <View
                style={props.isFullscreen ? [styles.qrcodeBox, {  top: moderateScale(40,1) }] : styles.qrcodeBox}>
                <View style={{padding: props.isFullscreen ? moderateScale(5,1): moderateScale(2,1),backgroundColor: "#fff"}}>
                    <QRCode
                        value={config.sing_qr}
                        color="#000"
                        backgroundColor="#fff"
                        size={props.isFullscreen ? s(65) : s(35)}
                    />
                </View>
                <Text style={props.isFullscreen ? [styles.qrcodeText,{
                    fontSize: moderateScale(9,1)
                }] : styles.qrcodeText}>微信扫码点歌</Text>
            </View>
        }
    </>

}
const styles = ScaledSheet.create({
    qrcodeBox: {
        position: "absolute",
        right: '10@ms1',
        top: '10@ms1',
        backgroundColor: "#07C160",
        padding: '5@ms1',
        alignItems: "center",
        borderRadius: '3@ms1',
    },
    qrcodeText: {
        marginTop: '3@ms1',
        fontSize: '6@ms1',
        color: "#fff"
    },
})
export default memo(forwardRef(Player), (prevProps, nextProps) =>
    prevProps.volume === nextProps.volume &&
    prevProps.source === nextProps.source &&
    prevProps.name === nextProps.name &&
    prevProps.isFullscreen === nextProps.isFullscreen)

```
## /Users/thunder/mycode/rn/components/PlayerControl.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useRef, useState } from "react";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { findNodeHandle, StyleSheet, Text, useTVEventHandler, View } from "react-native";
import { Badge } from "@rneui/themed";
import { focus } from "@wouterds/react-native-tv-focus";
import { useAppSelector } from "../store";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function PlayerControl(props: any, ref: any) {
    const [isVisible, setIsVisible] = useState(false);
    const { isPlaying, playStatus,selectedAudioTrack } = useAppSelector(state => state.control);
    const {orderList} = useAppSelector(state => state.common);
    const orderButtonRef = useRef<any>(null);
    const videoNextBtnRef = useRef<any>();
    const videoTrackBtnRef = useRef<any>();
    const videoPlayBtnRef = useRef<any>();
    const videoResetBtnRef = useRef<any>();
    const videoVolumePBtnRef = useRef<any>();
    const videoVolumeSBtnRef = useRef<any>();
    const videoBackBtnRef = useRef<any>();
    const controlRef = useRef<any>();
    const timer = useRef<NodeJS.Timeout>();
    // tv 上播放的时候遥控器事件
    const myTVEventHandler = useCallback((evt: any) => {
        if (evt.eventType === "down" || evt.eventType === "up" || evt.eventType === "left" || evt.eventType === "right") {
            if (!isVisible) {
                setIsVisible(true);
            }
        }
        hideControl();
        props.onActive()
    }, [isVisible]);
    useTVEventHandler(myTVEventHandler);
    const hideControl = () => {
        timer.current && clearTimeout(timer.current);
        timer.current = setTimeout(() => {
            setIsVisible(false);
        }, 5000);
    };
    useImperativeHandle(ref, () => ({
        isVisible,
        hideControl: (status?: boolean) => {
            if (status) {
                setIsVisible(false);
            } else {
                hideControl();
            }
        },
        switch: () => setIsVisible(!isVisible),
        showControl: () => setIsVisible(true),
    }))
    const handleEvent = useCallback((type: string, status?: boolean) => {
        if(type === 'order') {
            setIsVisible(false);
        } else {
            hideControl();
        }
        props.onChange(type, status)
    }, [])
    useEffect(() => {
        if (isVisible) {
            focus(findNodeHandle(controlRef.current));
            hideControl();
        } else {
            timer.current && clearTimeout(timer.current);
        }
    }, [isVisible]);
    return <View ref={controlRef} nextFocusLeft={orderButtonRef.current?._nativeTag}
                 nextFocusUp={orderButtonRef.current?._nativeTag}
                 nextFocusDown={orderButtonRef.current?._nativeTag}
                 nextFocusRight={orderButtonRef.current?._nativeTag}
                 style={Object.assign({},styles.controlBar,{opacity: isVisible ? 1 : 0})} focusable={true}>
        <TouchFocusHighlight
            ref={orderButtonRef}
            noBorder
            noScale
            focusName="video-order"
            nextFocusUp={orderButtonRef.current?._nativeTag}
            nextFocusRight={videoNextBtnRef.current?._nativeTag}
            nextFocusLeft={videoBackBtnRef.current?._nativeTag}
            nextFocusDown={orderButtonRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('order')}>
            <>
                <Text style={styles.icons}>{"\ue632"}</Text>
                <Text style={styles.controlText}>已点</Text>
                <Badge
                    badgeStyle={{ width: moderateScale(10,1), height: moderateScale(10,1), borderRadius: moderateScale(10,1) }}
                    textStyle={{ fontSize: moderateScale(6,1) }}
                    status="error"
                    value={orderList.length}
                    containerStyle={{ position: "absolute", top: 0, right: moderateScale(5,1) }}
                />
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoNextBtnRef}
            noBorder
            noScale
            focusName="video-next"
            nextFocusUp={videoNextBtnRef.current?._nativeTag}
            nextFocusLeft={orderButtonRef.current?._nativeTag}
            nextFocusRight={videoTrackBtnRef.current?._nativeTag}
            nextFocusDown={videoNextBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('next')}>
            <>
                <Text style={styles.icons}>{"\ue645"}</Text>
                <Text style={styles.controlText}>切歌</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoTrackBtnRef}
            noBorder
            noScale
            focusName="video-track"
            nextFocusUp={videoTrackBtnRef.current?._nativeTag}
            nextFocusLeft={videoNextBtnRef.current?._nativeTag}
            nextFocusRight={videoPlayBtnRef.current?._nativeTag}
            nextFocusDown={videoTrackBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('track')}>
            <>
                <Text style={styles.icons}>{!selectedAudioTrack ? "\ue63a" : "\ue610"}</Text>
                <Text style={styles.controlText}>{!selectedAudioTrack ? "原唱" : "伴唱"}</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoPlayBtnRef}
            noBorder
            noScale
            focusName="video-play"
            nextFocusUp={videoPlayBtnRef.current?._nativeTag}
            nextFocusLeft={videoTrackBtnRef.current?._nativeTag}
            nextFocusRight={videoResetBtnRef.current?._nativeTag}
            nextFocusDown={videoPlayBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('play', !isPlaying ? true : !playStatus)}>
            <>
                <Text style={styles.icons}>{playStatus && isPlaying ? "\ue641" : "\ue646"}</Text>
                <Text style={styles.controlText}>{playStatus && isPlaying ? "暂停" : "播放"}</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoResetBtnRef}
            noBorder
            noScale
            focusName="video-reset"
            nextFocusUp={videoResetBtnRef.current?._nativeTag}
            nextFocusLeft={videoPlayBtnRef.current?._nativeTag}
            nextFocusRight={videoVolumePBtnRef.current?._nativeTag}
            nextFocusDown={videoResetBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('reset')}>
            <>
                <Text style={styles.icons}>{"\ue637"}</Text>
                <Text style={styles.controlText}>重唱</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoVolumePBtnRef}
            noBorder
            noScale
            focusName="video-volumeP"
            nextFocusUp={videoVolumePBtnRef.current?._nativeTag}
            nextFocusLeft={videoResetBtnRef.current?._nativeTag}
            nextFocusRight={videoVolumeSBtnRef.current?._nativeTag}
            nextFocusDown={videoVolumePBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('volumeP')}>
            <>
                <Text style={styles.icons}>{"\ue626"}</Text>
                <Text style={styles.controlText}>音量</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoVolumeSBtnRef}
            noBorder
            noScale
            focusName="video-volumeS"
            nextFocusUp={videoVolumeSBtnRef.current?._nativeTag}
            nextFocusLeft={videoVolumePBtnRef.current?._nativeTag}
            nextFocusRight={videoBackBtnRef.current?._nativeTag}
            nextFocusDown={videoVolumeSBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('volumeS')}>
            <>
                <Text style={styles.icons}>{"\ue636"}</Text>
                <Text style={styles.controlText}>音量</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={videoBackBtnRef}
            noBorder
            noScale
            focusName="video-back"
            nextFocusUp={videoBackBtnRef.current?._nativeTag}
            nextFocusLeft={videoVolumeSBtnRef.current?._nativeTag}
            nextFocusRight={orderButtonRef.current?._nativeTag}
            nextFocusDown={videoBackBtnRef.current?._nativeTag}
            style={styles.controlBtn}
            activeColor="#2089dc"
            onPress={() => handleEvent('back')}>
            <>
                <Text style={styles.icons}>{"\ue612"}</Text>
                <Text style={styles.controlText}>退出</Text>
            </>
        </TouchFocusHighlight>
    </View>
}
const styles = ScaledSheet.create({
    controlBar: {
        width: "100%",
        position: "absolute",
        bottom: 0,
        backgroundColor: "rgba(0,0,0,0.5)",
        height: '50@ms1',
        flexDirection: "row",
        alignItems: "center",
        justifyContent: "center"
    },
    icons: { fontSize: '18@ms1', color: "#fff", fontFamily: "iconfont", marginBottom: 2 },
    controlBtn: {
        flexDirection: "column",
        margin: '5@ms1',
        alignItems: "center",
        borderRadius: '4@ms1',
        width: '42@ms1',
        height: '42@ms1',
        justifyContent: "center"
    },
    controlText: {
        fontSize: '11@ms1',
        color: "#fff"
    },
})

export default memo(forwardRef(PlayerControl), (prevProps, nextProps) => prevProps.currentAudioTrack === nextProps.currentAudioTrack)

```
## /Users/thunder/mycode/rn/components/Progress.tsx

```
import React, { forwardRef, memo, useImperativeHandle } from "react";
import { Text, View } from "react-native";
import useDownload from "../hooks/useDownload.ts";
import { RootSiblingPortal } from 'react-native-root-siblings';
import { moderateScale } from "react-native-size-matters";

export default memo(forwardRef(function Progress(props: any, ref: any) {
    const { isDownload, progress, setProgress, setIsDownload } = useDownload();
    useImperativeHandle(ref, () => ({
        setProgress,
        setIsDownload
    }));
    return (
        <RootSiblingPortal>
            {
                isDownload &&
                <View style={{ position: "absolute", zIndex: 21, left: props?.left || moderateScale(90,1), top: props?.top || moderateScale(5,1) }}>
                    <Text style={{
                        color: "#fff",
                        fontSize: moderateScale(8,1)
                    }}>正在下载：{(progress?.name || "") + "    " + (progress?.value || "0%")}</Text>
                </View>
            }
        </RootSiblingPortal>
    );
}));

```
## /Users/thunder/mycode/rn/components/QrcodeDialog.tsx

```
import React, { memo, useCallback, useEffect, useRef } from "react";
import { focus } from "@wouterds/react-native-tv-focus";
import { findNodeHandle, StyleSheet, Text, TouchableHighlight, useTVEventHandler, View } from "react-native";
import { setQrcodeStatus } from "../store/common.ts";
import LinearGradient from "react-native-linear-gradient";
import QRCode from "react-native-qrcode-svg";
import { Dialog } from "@rneui/themed";
import { useAppDispatch, useAppSelector } from "../store";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function QrcodeDialog(props: any) {
    const { qrcodeStatus,dialogTitle,config } = useAppSelector(state => state.common);
    const dispatch = useAppDispatch();
    const dialogCloseRef = useRef<any>();
    const myTVEventHandler = useCallback((evt:any) => {
        if(evt.eventType === 'down' || evt.eventType === 'up' || evt.eventType === 'left' || evt.eventType === 'right') {
            if(qrcodeStatus) {
                focus(findNodeHandle(dialogCloseRef.current));
            }
        }
    }, [qrcodeStatus]);
    useTVEventHandler(myTVEventHandler);
    return <Dialog overlayStyle={styles.Overlay} isVisible={qrcodeStatus} onBackdropPress={()=>{
        props.onVerify(true)
        dispatch(setQrcodeStatus(false))
    }}>

        <LinearGradient
            style={{flex: 1, padding: moderateScale(10), flexDirection: 'column', justifyContent: 'space-between',}}
            start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <Text style={{color:'#fff', fontSize: moderateScale(10,1)}}>{dialogTitle}</Text>
            <View style={{justifyContent: 'center', alignItems: 'center'}}>
                {
                    config?.active_dialog?.qr.url && <QRCode
                        value={config.active_dialog.qr.url}
                        color="#000"
                        backgroundColor="#fff"
                        size={moderateScale(80,1)}
                    />
                }
            </View>
            <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                <TouchableHighlight ref={dialogCloseRef} style={styles.exitBtn} underlayColor="#2089dc" onPress={()=> {
                    props.onVerify(true)
                    dispatch(setQrcodeStatus(false))
                }}>
                    <Text style={styles.exitBtnText}>关闭</Text>
                </TouchableHighlight>
            </View>
        </LinearGradient>
    </Dialog>
}
const styles = ScaledSheet.create({
    Overlay: {
        width: '200@s',
        height: '150@s',
        padding: 0,
        borderRadius: '4@ms1',
        overflow: 'hidden'
    },
    exitBtn: {
        paddingVertical:'3@ms1',
        paddingHorizontal:'5@ms1',
        borderRadius:'2@ms1',
    },
    exitBtnText: {
        fontSize:'12@ms1',
        color: '#fff'
    }
})
export default memo(QrcodeDialog)

```
## /Users/thunder/mycode/rn/components/Rank.tsx

```
import React, { memo, useCallback, useEffect, useRef } from "react";
import { Tab } from "@rneui/themed";
import { Image, TouchableHighlight, View } from "react-native";
import SongItem from "./SongItem";
import { useCallbackState } from "../hooks/useCallBackState";
import Pagination from "./Pagination";
import { request } from "../libs/util";
import { FlashList } from "@shopify/flash-list";
import { company } from "../config.json";
import AsyncStorage from "@react-native-async-storage/async-storage";
import { moderateScale } from "react-native-size-matters";

function Rank(props: RankProps) {
    // 分类模块 激活的tab和tab数据
    const [activeIndex, setActiveIndex] = useCallbackState(0);
    const [tabData, setTabData] = useCallbackState([]);
    // 歌曲列表
    const [songList, setSongList] = useCallbackState([]);

    // 获取实时更新的tab数据
    const tabDataRef = useRef();
    // 分页加载是否已经全部加载
    const isAllRef = useRef(false);
    // 存储更新后的父组件传过来的数据，解决分页加载数据无法拿到数据的问题
    const activeCategory = useRef<any>();
    // 存储更新后的激活tab
    const activeIndexRef = useRef(0);
    const listRef = useRef<any>();
    const currentPageRef = useRef(1);
    const listTotalRef = useRef([]);
    const searchText = useRef<string | undefined>("");
    const paginationRef = useRef<any>();
    // 获取排行榜的歌曲列表信息
    const getRankData = async () => {
        isAllRef.current = false;
        // @ts-ignore
        let url = `${global.url}`;
        const token = await AsyncStorage.getItem("token");
        if (searchText.current) {
            url += `/kcloud/getmusics?token=${token}&page=${currentPageRef.current}&size=10&word=${searchText.current}&language=&company=${company}`;
        } else {
            url += `/apollo/module/songlist?token=${token}&id=${activeCategory.current?.moduleId}&unionid=o6qE3ty1odlYIcombCte8ee2TppM&page=${currentPageRef.current}&size=10&company=${company}`;
        }
        request(url).then(res => {
            const list = (searchText.current ? res.data.mediainfo.list : res.data.list) || [];
            if (list?.length < 10) {
                isAllRef.current = true;
            }
            if (currentPageRef.current === 1) {
                setSongList(list.length ? list : [], (list: any) => {
                    listTotalRef.current = list;
                });
                setTimeout(() => {
                    scrollToIndex(0);
                }, 500)
            } else {
                list?.length && setSongList(listTotalRef.current.concat(list), (list: any) => {
                    listTotalRef.current = list;
                });
            }

        });
    };
    // 获取分类的tab信息
    const getTabData = async () => {
        const token = await AsyncStorage.getItem("token");
        // @ts-ignore
        request(`${global.url}/vodc/topic/songlist?token=${token}&topicId=${activeCategory.current?.id}&company=${company}`).then(res => {
            setTabData(res.data.filter((item: any) => item.name.indexOf("歌神") === -1 && item.name.indexOf("我的常唱") === -1), (data: any) => {
                if (activeIndex !== 0) setActiveIndex(0);
                paginationRef.current?.go(1);
                currentPageRef.current = 1;
                tabDataRef.current = data;
                activeIndexRef.current = 0;
                getCategoryData();
                isAllRef.current = false;
            });
        });
    };
    // 获取分类歌曲列表
    const getCategoryData = async () => {
        const token = await AsyncStorage.getItem("token");
        isAllRef.current = false;
        // @ts-ignore
        request(`${global.url}/vodc/song/list?token=${token}&p=${currentPageRef.current}&openid=&unionid=&type=hot&tp=${tabDataRef.current[activeIndexRef.current]?.id}&company=${company}`).then(res => {
            if (res.data?.length < 10) {
                isAllRef.current = true;

            }
            if (currentPageRef.current === 1) {
                setSongList(res.data.length ? res.data : [], (list: any) => {
                    listTotalRef.current = list;
                });
                setTimeout(() => {
                    scrollToIndex(0);
                }, 500)
            } else {
                res.data?.length && setSongList(listTotalRef.current.concat(res.data), (list: any) => {
                    listTotalRef.current = list;
                });
            }
        });
    };
    // 获取戏曲的歌曲列表
    const getDramaData = async () => {
        const token = await AsyncStorage.getItem("token");
        isAllRef.current = false;
        // @ts-ignore
        request(`${global.url}/vodc/song/list?token=${token}&p=${currentPageRef.current}&openid=&unionid=&type=hot&tp=${activeCategory.current?.id}`).then(res => {
            if (res.data?.length < 10) {
                isAllRef.current = true;
            }
            if (currentPageRef.current === 1) {
                setSongList(res.data.length ? res.data : [], (list: any) => {
                    listTotalRef.current = list;
                });
                setTimeout(() => {
                    scrollToIndex(0);
                }, 500)
            } else {
                res.data?.length && setSongList(listTotalRef.current.concat(res.data), (list: any) => {
                    listTotalRef.current = list;
                });
            }

        });
    };
    const scrollToIndex = (index: number) => {
        listTotalRef.current?.length && listRef.current?.scrollToIndex({
            index,
            animated: false
        });
    };
    const handleViewableItemsChanged = useCallback((info: any) => {
        if (props?.type === "category") {
            if (info.viewableItems[info.viewableItems?.length - 3]) {
                paginationRef.current?.go(Math.floor(info.viewableItems[info.viewableItems?.length - 3].index / 4) + 1);
            }
        } else {
            if (info.viewableItems[info.viewableItems?.length - 4]) {
                paginationRef.current?.go(Math.floor(info.viewableItems[info.viewableItems?.length - 4].index / 5) + 1);
            }
        }

    }, []);
    // 分页切换
    const pageChange = (type: string, state?: boolean) => {
        if (type === "prev") {
            if (paginationRef.current.page === 1) return;
            paginationRef.current?.go(paginationRef.current.page - 1);
            if (props?.type === "category") {
                scrollToIndex((paginationRef.current.page - 2) * 4);
            } else {
                scrollToIndex((paginationRef.current.page - 2) * 5);
            }
        } else {
            if (state) {
                if (!isAllRef.current) {
                    currentPageRef.current++;
                    if (props.type === "category") {
                        tabDataRef.current && getCategoryData();
                    } else if (props.type === "banner") {
                        getDramaData();
                    } else {
                        getRankData();
                    }
                }
            } else {
                if (props.type === "category") {
                    if ((paginationRef.current.page) * 4 >= listTotalRef.current?.length) return;
                    paginationRef.current?.go(paginationRef.current.page + 1);
                    scrollToIndex(paginationRef.current.page * 4);
                } else {
                    if ((paginationRef.current.page) * 5 >= listTotalRef.current?.length) return;
                    paginationRef.current?.go(paginationRef.current.page + 1);
                    scrollToIndex(paginationRef.current.page * 5);
                }

            }
        }
    };
    const renderItem = useCallback(({ item, index }: { item: any, index: number }) => <SongItem item={item}
                                                                                                index={index} />, []);
    const keyExtractor = useCallback((item: any, index: number) => (item.songid || item.songId).toString() + index, []);
    useEffect(() => {
        if (props.activeCategory) {
            activeCategory.current = props.activeCategory;
            if (props.type === "category") {
                getTabData();
            } else if (props.type === "banner") {
                paginationRef.current?.go(1);
                currentPageRef.current = 1;
                getDramaData();
            } else if (props.type === "rank") {
                paginationRef.current?.go(1);
                currentPageRef.current = 1;
                getRankData();
            }
        }
    }, [props.activeCategory]);
    useEffect(() => {
        searchText.current = props.searchText;
        if (searchText.current !== undefined) {
            paginationRef.current?.go(1);
            currentPageRef.current = 1;
            getRankData();
        }
    }, [props.searchText]);
    return <>
        {
            props?.type === "category" && <Tab
                style={{
                    height: moderateScale(40),
                    backgroundColor: "#3D4170",
                    marginBottom: moderateScale(5,1),
                    borderRadius: moderateScale(3,1)
                }}
                titleStyle={{
                    color: "#ffffff",
                    fontSize: moderateScale(12,1)
                }}
                buttonStyle={(active) => ({
                    padding: 0,
                    backgroundColor: active ? "#2089dc" : "transparent",
                    height: moderateScale(40)
                })}
                containerStyle={{ backgroundColor: "transparent" }}
                value={activeIndex}
                scrollable
                disableIndicator
                variant="primary"
            >
                {tabData?.map((item: any, index: number) => (
                    <Tab.Item
                        TouchableComponent={TouchableHighlight} underlayColor="transparent"
                        activeOpacity={1}
                        onShowUnderlay={() => {
                            setActiveIndex(index, (val: number) => {
                                paginationRef.current?.go(1);
                                currentPageRef.current = 1;
                                activeIndexRef.current = val;
                                !props.searchText && getCategoryData();
                            });
                        }}
                        key={index}
                        title={item.name}
                    />
                ))}
            </Tab>
        }
        <View style={{ flex: 1, flexDirection: "row" }}>
            <FlashList
                data={songList}
                ref={(ref) => listRef.current = ref}
                onEndReached={() => {
                    songList.length && pageChange("next", true);
                }}
                keyExtractor={keyExtractor}
                estimatedItemSize={90}
                onViewableItemsChanged={handleViewableItemsChanged}
                ListEmptyComponent={() => <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
                    <Image resizeMode="contain" style={{ width: 300, height: 300 }}
                           source={require("../assets/imgs/empty.png")}></Image></View>}
                renderItem={renderItem}
                onEndReachedThreshold={1}
            />
            <Pagination ref={paginationRef} onChange={pageChange} />
        </View>
    </>;
}

export default memo(Rank, (prevProps, nextProps) => {
    if (prevProps?.activeCategory !== nextProps?.activeCategory) {
        return false;
    }
    if (prevProps?.searchText !== nextProps?.searchText) {
        return false;
    }
    return true;
});

```
## /Users/thunder/mycode/rn/components/Search.tsx

```
import React, { forwardRef, memo, useEffect, useImperativeHandle, useRef, useState } from "react";
import { findNodeHandle, StyleSheet, Text, TouchableHighlight, View,
    InteractionManager } from "react-native";
import { Icon, SearchBar } from "@rneui/themed";
import Letter from "./Letter.tsx";
import { HandInputDrawingPad } from "../libs/components.ts";
import { useCallbackState } from "../hooks/useCallBackState.ts";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { useAppSelector } from "../store";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

interface SearchProps {
    onSearch: (text: string) => void,
}
function Search(props: SearchProps, ref: any) {
    const [keyboardType, setKeyBoardType] = useState("input");
    const [searchText, setSearchText] = useCallbackState("");
    const [matches, setMatches] = useState([]);
    const lettersRef = useRef<any>();
    const {videoNativeTag} = useAppSelector(state => state.control);
    const delBtnRef = useRef<any>();
    const bkspBtnRef = useRef<any>();
    const inputBtnRef = useRef<any>();
    const writeBtnRef = useRef<any>();
    const sysBtnRef = useRef<any>();
    const searchTextRef = useRef<any>('');
    const searchBarRef = useRef<any>();
    const updateSearch = (search: any, value="") => {
        let text = '';
        if(search === 'bksp') {
            text = searchTextRef.current.substring(0,searchTextRef.current.length-1)
        } else if(search === 'del') {
            text = '';
        } else if(search === 'input') {
            text = value;
        } else {
            text = searchTextRef.current + search;
        }
        setSearchText(text,(val:string)=>{
            searchTextRef.current = val
            InteractionManager.runAfterInteractions(() => {
                // 异步操作
                props.onSearch(val)
            });

        });
    }
    const selectText = (item: any) => {
        requestAnimationFrame(() => {
            updateSearch(item);
            setMatches([]);
        });
    };
    const onResult = (e: any) => {
        const result = e.nativeEvent.result;
        setMatches(Array.from(result.slice(0, 8)));
    };
    useImperativeHandle(ref, () => ({
        updateSearch,
        blur: () => {
            searchBarRef.current?.blur();
        }
    }))
    useEffect(()=> {
        if(keyboardType === 'sys') {
            setTimeout(()=>{
                searchBarRef.current?.focus();
            }, 200)
        } else {
            setTimeout(()=>{
                searchBarRef.current?.blur();
            }, 200)
        }
    }, [keyboardType])
    return <View style={styles.search}>
        <View style={styles.clearBtnBox}>
            <TouchFocusHighlight
                ref={bkspBtnRef}
                nextFocusRight={findNodeHandle(delBtnRef.current)}
                nextFocusUp={videoNativeTag}
                nextFocusDown={lettersRef.current?.firstFocus}
                nextFocusLeft={findNodeHandle(inputBtnRef.current)}
                noBorder
                noScale
                focusName="bksp"
                style={{
                    height:moderateScale(28),
                    width:moderateScale(28),
                    alignItems: "center",
                    justifyContent: "center",
                    borderRadius: moderateScale(2,1),
                }}
                activeColor="#2089dc"
                onPress={(event) => updateSearch("bksp")}>
                <Icon
                    size={moderateScale(10,1.4)}
                    name="backspace-outline"
                    type="ionicon"
                    color="#ffffff"
                />
            </TouchFocusHighlight>
            <TouchFocusHighlight
                ref={delBtnRef}
                nextFocusDown={lettersRef.current?.firstFocus}
                nextFocusUp={videoNativeTag}
                nextFocusLeft={findNodeHandle(bkspBtnRef.current)}
                focusName="del"
                noBorder
                noScale
                style={{
                    marginLeft:moderateScale(3,1),
                    height:moderateScale(28),
                    width:moderateScale(28),
                    alignItems: "center",
                    justifyContent: "center",
                    borderRadius: moderateScale(2,1),
                }}
                activeColor="#2089dc"
                onPress={(event) => updateSearch("del")}>
                <Icon
                    size={moderateScale(12,1)}
                    name="trash-outline"
                    type="ionicon"
                    color="#ffffff"
                />
            </TouchFocusHighlight>
        </View>
        <SearchBar
            ref={searchBarRef}
            inputContainerStyle={{ height: moderateScale(30) }}
            inputStyle={{ color: "#ffffff", fontSize: moderateScale(8,1), padding: 0 }}
            containerStyle={styles.searchBar}
            placeholder={keyboardType === "input" ? "输入首字母搜索" : "输入搜索信息"}
            onChangeText={(text)=> {
                updateSearch("input",text)
            }}
            value={searchText}
            editable={keyboardType === 'sys'}
        />
        <View style={{ flexDirection: "row", flex: 1 }}>
            <View style={styles.selectButton}>
                <TouchFocusHighlight
                    ref={inputBtnRef}
                    focusName="input"
                    style={Object.assign({},styles.KeyboardBtn,{
                        borderColor: "#2089dc",
                        backgroundColor: keyboardType === "input" ? "#2089dc" : "transparent",
                    })}
                    nextFocusUp={findNodeHandle(bkspBtnRef.current)}
                    nextFocusDown={findNodeHandle(writeBtnRef.current)}
                    nextFocusLeft={findNodeHandle(inputBtnRef.current)}
                    nextFocusRight={lettersRef.current?.firstFocus}
                    onHandleFocus={() => setKeyBoardType("input")}
                    onPress={() =>setKeyBoardType("input") }
                    activeColor="#2089dc">
                    <Text
                        style={{
                            fontSize: moderateScale(8,1),
                            color: '#fff'
                        }}>输入</Text>
                </TouchFocusHighlight>
                <TouchFocusHighlight
                    ref={writeBtnRef}
                    style={Object.assign({},styles.KeyboardBtn,{
                        borderColor: "#2089dc",
                        marginVertical: moderateScale(5,1),
                        backgroundColor: keyboardType === "write" ? "#2089dc" : "transparent",
                    })}
                    nextFocusUp={findNodeHandle(inputBtnRef.current)}
                    nextFocusLeft={findNodeHandle(writeBtnRef.current)}
                    nextFocusDown={findNodeHandle(sysBtnRef.current)}
                    focusName="write"
                    onHandleFocus={() => setKeyBoardType("write")}
                    onPress={() => setKeyBoardType("write")}
                    activeColor="#2089dc" >
                    <Text style={{
                        fontSize: moderateScale(8,1),
                        color: "#fff"
                    }}>手写</Text>
                </TouchFocusHighlight>
                <TouchFocusHighlight
                    ref={sysBtnRef}
                    style={Object.assign({},styles.KeyboardBtn,{
                        borderColor: "#2089dc",
                        backgroundColor: keyboardType === "sys" ? "#2089dc" : "transparent",
                    })}
                    nextFocusUp={findNodeHandle(writeBtnRef.current)}
                    nextFocusLeft={findNodeHandle(sysBtnRef.current)}
                    focusName="write"
                    onHandleFocus={() => setKeyBoardType("sys")}
                    onPress={() => setKeyBoardType("sys")}
                    activeColor="#2089dc" >
                    <Text style={{
                        fontSize: moderateScale(8,1),
                        color: "#fff"
                    }}>系统</Text>
                </TouchFocusHighlight>
            </View>
            {
                keyboardType === "input" ? <Letter ref={lettersRef} onSearch={updateSearch} bkspNativeTag={findNodeHandle(bkspBtnRef.current)} inputNativeTag={findNodeHandle(inputBtnRef.current)}/>
                     : keyboardType === "write" ?
                    <View
                        style={{ flex: 1, paddingTop: moderateScale(5,1), overflow: "hidden", flexDirection: "row" }}>
                        <HandInputDrawingPad onChange={onResult} style={{
                            flex: 1,
                            borderRadius: moderateScale(3,1),
                            backgroundColor: "#393E42",
                            overflow: "hidden"
                        }} />

                        <View style={{
                            marginLeft: moderateScale(5,1),
                            width: moderateScale(50,1),
                            backgroundColor: "#393E42",
                            borderRadius: moderateScale(3,1),
                            flexWrap: "wrap",
                            overflow: "hidden"
                        }}>
                            {matches.map((item: any, index: number) => {
                                return (
                                    <TouchableHighlight style={{
                                        width: "50%",
                                        paddingVertical: moderateScale(2,1),
                                        alignItems: "center",
                                        justifyContent: "center",
                                        borderRadius: moderateScale(2,1)
                                    }} key={index} activeOpacity={1}
                                                        underlayColor="#2089dc"
                                                        onPress={() => selectText(item)}>
                                        <Text style={[styles.letterText,{ fontSize: moderateScale(10,1) }]}>{item}</Text>
                                    </TouchableHighlight>
                                );
                            })}
                        </View>
                    </View>: <View />
            }
        </View>
    </View>
}
const styles = ScaledSheet.create({
    search: {
        flex: 1,
        borderRadius: '3@ms1',
        backgroundColor: "#3D4170",
        overflow: "hidden",
        padding: '5@ms1'
    },
    KeyboardBtn: {
        alignItems: "center",
        justifyContent: "center",
        borderRadius: '3@ms1',
        borderWidth: 1,
        borderColor: "transparent",
        paddingVertical: '3@ms1',
    },
    clearBtnBox: {
        flexDirection: "row",
        position: "absolute",
        right: '10@ms1',
        top: '9@ms1',
        zIndex: 11,
        alignItems: "center",
        justifyContent: "space-between",
        backgroundColor: '#303337'

    },
    searchBar: {
        height: '40@ms',
        borderRadius: '3@ms1',
        borderTopWidth: 0,
        borderBottomWidth: 0,
        zIndex:10,
        padding:0,
        alignItems: "center",
        justifyContent: "center",
        paddingHorizontal: '4@ms1',
    },
    selectButton: {
        flexDirection: "column",
        marginRight: '5@ms1',
        width: '35@ms1',
        justifyContent: "center",
    },
    letterText: {
        color: "white",
        fontSize: '12@ms1'
    },
})
export default memo(forwardRef(Search));

```
## /Users/thunder/mycode/rn/components/Singer.tsx

```
import React, { memo, useCallback, useEffect, useMemo, useRef, useState } from "react";
import { ListItem, Tab } from "@rneui/themed";
import { Image, TouchableHighlight, View } from "react-native";
import { useCallbackState } from "../hooks/useCallBackState";
import Pagination from "./Pagination";
import FastImage from "react-native-fast-image";
import { request } from "../libs/util";
import { FlashList } from "@shopify/flash-list";
import AnalyticsUtil from "../libs/AnalyticsUtil";
import { company } from "../config.json";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import AsyncStorage from "@react-native-async-storage/async-storage";
import { moderateScale } from "react-native-size-matters";
function Singer(props: SingerProps) {
    const [singerData, setSingerData] = useCallbackState([]);
    const [activeIndex, setActiveIndex] = useCallbackState(0);
    const [tabData, setTabData] = useState<string[]>([]);
    const listRef = useRef<any>();
    const currentPageRef = useRef(1);
    const singerDataRef = useRef([]);
    const totalRef = useRef(0);
    const paginationRef = useRef<any>();
    const getSingerData = async () => {
        const token = await AsyncStorage.getItem("token");
        request(`${global.url}/kcloud/getsingerlist_new?token=${token}&page=${currentPageRef.current}&size=16&tp=${tabData[activeIndex] === "全部" ? "" : tabData[activeIndex]}&word=${props.searchText}&company=${company}`).then((res) => {
            const list = res?.data?.actorinfo?.list || [];
            totalRef.current = res?.data?.actorinfo?.total || 0;
            if (currentPageRef.current === 1) {
                setSingerData(list.length ? list : [], (list: any) => {
                    singerDataRef.current = list;
                });
                setTimeout(() => {
                    scrollToIndex(0);
                }, 500)
            } else {
                list?.length && setSingerData(singerDataRef.current.concat(list), (list: any) => {
                    singerDataRef.current = list;
                });
            }
        });
    };
    const singerClick = (item: any) => {
        props.onShowList(item.singerName, item.singerId);
        AnalyticsUtil.onEventWithMap("singer", {
            singerName: item.singerName,
            singerId: item.singerId
        });
    };
    const pageChange = (type: string, state?: boolean) => {
        if (type === "prev") {
            if (paginationRef.current.page === 1) return;
            paginationRef.current?.go(paginationRef.current.page - 1);
            scrollToIndex((paginationRef.current.page - 2) * 8);
        } else {
            if (state) {
                if (!(totalRef.current === singerDataRef.current.length)) {
                    currentPageRef.current++;
                    getSingerData();
                }
            } else {
                if ((paginationRef.current.page + 1) * 8 > singerDataRef.current.length) return;
                paginationRef.current?.go(paginationRef.current.page + 1);
                scrollToIndex((paginationRef.current.page) * 8);
            }
        }
    };
    const scrollToIndex = (index: number) => {
        singerDataRef.current.length && listRef.current?.scrollToIndex({
            index,
            animated: false
        });
    };
    const handleViewableItemsChanged = useCallback((info: any) => {
        if (info.viewableItems.slice(info.viewableItems.length - 8)[0]) {
            paginationRef.current?.go(Math.floor(info.viewableItems.slice(info.viewableItems.length - 8)[0]?.index / 8 + 1));
        }
    }, []);
    const renderItem = useCallback(({ item, index }: { item: any; index: number }) => <RenderChild item={item}
                                                                                                   index={index}
                                                                                                   onSingerClick={singerClick} />, []);
    const keyExtractor = useCallback((item: any, index: number) => item.singerId, []);
    useEffect(()=> {
        setTabData(["全部", "大陆男歌星", "港台男歌星", "大陆女歌星", "港台女歌星", "中国组合", "外国歌星"])
    }, [])
    useEffect(() => {
        if (tabData.length) {
            paginationRef.current?.go(1);
            currentPageRef.current = 1;
            getSingerData();
        }
    }, [props.searchText, activeIndex, tabData.length]);
    return <>
        <Tab
            style={{
                height: moderateScale(40),
                backgroundColor: "#3D4170",
                marginBottom: moderateScale(5,1),
                borderRadius: moderateScale(3,1)
            }}
            titleStyle={{
                color: "#ffffff",
                fontSize: moderateScale(12,1)
            }}
            buttonStyle={(active) => ({
                padding: 0,
                backgroundColor: active ? "#2089dc" : "transparent",
                height: moderateScale(40)
            })}
            containerStyle={{ backgroundColor: "transparent" }}
            value={activeIndex}
            scrollable
            disableIndicator
            variant="primary"
        >
            {tabData?.map((item: any, index: number) => (
                <Tab.Item
                    TouchableComponent={TouchableHighlight} underlayColor="transparent"
                    activeOpacity={1}
                    onShowUnderlay={() => setActiveIndex(index)}
                    key={index}
                    title={item}
                />
            ))}
        </Tab>
        <View style={{ flex: 1, flexDirection: "row" }}>
            <FlashList
                data={singerData}
                ref={(ref) => listRef.current = ref}
                numColumns={4}
                onEndReached={() => {
                    singerData.length && pageChange("next", true);
                }}
                keyExtractor={keyExtractor}
                estimatedItemSize={moderateScale(85,1)}
                onViewableItemsChanged={handleViewableItemsChanged}
                renderItem={renderItem}
                ListEmptyComponent={() => <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
                    <Image resizeMode="contain" style={{ width: moderateScale(200), height: moderateScale(200) }}
                           source={require("../assets/imgs/empty.png")}></Image></View>}
                onEndReachedThreshold={1}
            />
            <Pagination ref={paginationRef} onChange={pageChange} />
        </View>
    </>;
}

interface RenderChildProps {
    item: any;
    index: number;
    onSingerClick: (item: any) => void;
}

class RenderChild extends React.Component<RenderChildProps> {
    state = {
        loading: false,
        error: false
    };
    componentDidUpdate(prevProps: Readonly<RenderChildProps>, prevState: Readonly<{}>, snapshot?: any) {
        if (prevProps.item?.singerId !== this.props.item?.singerId) {
            this.setState({ error: false });
        }
    }
    render() {
        return <ListItem key={this.props.index} containerStyle={{
            backgroundColor: "transparent",
            flexDirection: "column",
            justifyContent: "center",
            // maxWidth: 120,
            height: moderateScale(85,1)
        }}>
            <TouchFocusHighlight
                focusName={"singerItem" + this.props.index}
                style={{
                    borderRadius: moderateScale(50,1),
                    width: moderateScale(50,1),
                    height: moderateScale(50,1),
                    overflow: "hidden"
                }}
                onPress={() => {
                    this.props.onSingerClick(this.props.item);
                }}>
                {/*{this.state.loading && <Skeleton circle  width={100} height={100} animation="wave" />}*/}
                <FastImage style={{ width: moderateScale(50,1), height: moderateScale(50,1) }} onError={() => this.setState({ error: true })}
                           onLoadStart={() => this.setState({ loading: true })}
                           onLoadEnd={() => this.setState({ loading: false })}
                           source={this.state.error ? require("../assets/imgs/user.png") : {
                               uri: this.props.item.actor_pic + "?imageView2/1/w/100/h/100/q/50!/format/webp",
                               priority: FastImage.priority.high
                           }} resizeMode={FastImage.resizeMode.contain} />
            </TouchFocusHighlight>
            <ListItem.Title numberOfLines={1} style={{
                fontSize: moderateScale(11,1),
                color: "#fff",
                marginTop: moderateScale(5,1),
                textAlign: "center"
            }}>{this.props.item.singerName || this.props.item.singer}</ListItem.Title>
        </ListItem>;
    }
}

export default memo(Singer, (prevProps, nextProps) => {
    return prevProps.searchText === nextProps.searchText;
});

```
## /Users/thunder/mycode/rn/components/Song.tsx

```
import React, { memo, useCallback, useEffect, useMemo, useRef, useState } from "react";
import SongItem from "./SongItem";
import { Image, TouchableHighlight, View } from "react-native";
import { useCallbackState } from "../hooks/useCallBackState";
import Pagination from "./Pagination";
import { request } from "../libs/util";
import { FlashList } from "@shopify/flash-list";
import { company } from "../config.json";
import { Tab } from "@rneui/themed";
import AsyncStorage from "@react-native-async-storage/async-storage";
import { moderateScale } from "react-native-size-matters";
import { useRoute } from "@react-navigation/native";

function Song(props: SongProps) {
    const route = useRoute<{key: string, name:string, params: {categoryId?: number|string, singerId?: number|string}}>()
    // 页面显示的页码
    const [songList, setSongList] = useCallbackState([]);
    const [activeIndex, setActiveIndex] = useState(0);

    const isAllRef = useRef(false);
    const listRef = useRef<any>();
    const listTotalRef = useRef([]);
    // 请求数据的 页码
    const currentPageRef = useRef(1);
    const paginationRef = useRef<any>();
    const [tabData, setTabData] = useState<string[]>([])
    const getSongList = useCallback(async () => {
        const token = await AsyncStorage.getItem("token");
        // @ts-ignore
        let url = `${global.url}`;
        if (route?.params?.singerId) {
            url += `/apollo/search/actorsong?token=${token}&page=${currentPageRef.current}&key=${props.searchText}&unionid=&actorid=${route?.params?.singerId}&size=10&company=${company}`;
        } else {
            if(route?.params?.categoryId) {
                if(props.searchText) {
                    url += `/kcloud/getmusics?token=${token}&page=${currentPageRef.current}&size=10&word=${props.searchText}&language=${tabData[activeIndex] === "全部" ? "" : tabData[activeIndex]}&company=${company}`;
                } else {
                    url += `/vodc/song/list?token=${token}&p=${currentPageRef.current}&openid=&unionid=&type=hot&tp=${route?.params?.categoryId}&company=${company}`
                }
            } else {
                url += `/kcloud/getmusics?token=${token}&page=${currentPageRef.current}&size=10&word=${props.searchText}&language=${tabData[activeIndex] === "全部" ? "" : tabData[activeIndex]}&company=${company}`;
            }

        }
        isAllRef.current = false;
        // @ts-ignore
        request(url).then(res => {
            const list = !route?.params?.singerId ? (route?.params?.categoryId && !props.searchText ? res.data :res.data.mediainfo.list) : res.data.list;
            if (list.length < 10) {
                isAllRef.current = true;
            }
            if (currentPageRef.current === 1) {
                setSongList(list.length ? list : [], (list: any) => {
                    listTotalRef.current = list;
                });
                setTimeout(() => {
                    scrollToIndex(0);
                }, 500)
            } else {
                if(list.length) {
                    setSongList(listTotalRef.current.concat(list), (list: any) => {
                        listTotalRef.current = list;
                    });
                }
            }
        });
    }, [route?.params?.singerId, props.searchText,tabData, currentPageRef.current, activeIndex, route?.params?.categoryId]);
    const pageChange = useCallback((type: string, state?: boolean) => {
        if (type === "prev") {
            if (paginationRef.current.page === 1) return;
            if (route?.params?.singerId || route?.params?.categoryId) {
                paginationRef.current?.go(paginationRef.current.page - 1);
                scrollToIndex((paginationRef.current.page - 2) * 5);
            } else {
                paginationRef.current?.go(paginationRef.current.page - 1);
                scrollToIndex((paginationRef.current.page - 2) * 4);
            }

        } else {
            if (state) {
                if (!isAllRef.current) {
                    currentPageRef.current++;
                    getSongList();
                }
            } else {
                if (route?.params?.singerId || route?.params?.categoryId) {
                    if ((paginationRef.current.page) * 5 >= listTotalRef.current.length) return;
                    paginationRef.current?.go(paginationRef.current.page + 1);
                    scrollToIndex(paginationRef.current.page * 5);
                } else {
                    if ((paginationRef.current.page) * 4 >= listTotalRef.current.length) return;
                    paginationRef.current?.go(paginationRef.current.page + 1);
                    scrollToIndex(paginationRef.current.page * 4);
                }

            }
        }

    }, [paginationRef.current?.page, listTotalRef.current.length, currentPageRef.current, route?.params?.singerId, route?.params?.categoryId]);
    const scrollToIndex = (index: number) => {
        listTotalRef.current.length && listRef.current?.scrollToIndex({
            index,
            animated: false
        });
    };
    const handleViewableItemsChanged = useCallback((info: any) => {
        if (route?.params?.singerId || route?.params?.categoryId) {
            if (info.viewableItems[info.viewableItems.length - 4]) {
                paginationRef.current?.go(Math.floor(info.viewableItems[info.viewableItems.length - 4].index / 5) + 1);
            }
        } else {
            if (info.viewableItems[info.viewableItems.length - 3]) {
                paginationRef.current?.go(Math.floor(info.viewableItems[info.viewableItems.length - 3].index / 4) + 1);
            }
        }
    }, []);
    const renderItem = useCallback(({ item, index }: { item: any; index: number }) => <SongItem item={item}
                                                                                                index={index} />, []);
    const keyExtractor = useCallback((item: any, index: number) => (item.songid || item.songId).toString() + index, []);
   useEffect(()=> {
       setTabData(["全部", "国语", "闽南语", "粤语", "英语", "韩语", "日语", "其它"])
   }, [])
    useEffect(() => {
        if (tabData.length) {
            paginationRef.current?.go(1);
            currentPageRef.current = 1;
            getSongList();
        }
    }, [props.searchText, activeIndex, tabData.length]);
    return <>
        {
            !route?.params?.singerId && !route?.params?.categoryId && <Tab
                style={{
                    height: moderateScale(40),
                    backgroundColor: "#3D4170",
                    marginBottom: moderateScale(5,1),
                    borderRadius: moderateScale(3,1)
                }}
                titleStyle={{
                    color: "#ffffff",
                    fontSize: moderateScale(12,1)
                }}
                buttonStyle={(active) => ({
                    padding: 0,
                    backgroundColor: active ? "#2089dc" : "transparent",
                    height: moderateScale(40)
                })}
                containerStyle={{ backgroundColor: "transparent" }}
                value={activeIndex}
                scrollable
                disableIndicator
                variant="primary"
            >
                {tabData?.map((item: any, index: number) => (
                    <Tab.Item
                        TouchableComponent={TouchableHighlight} underlayColor="transparent"
                        activeOpacity={1}
                        onShowUnderlay={() => setActiveIndex(index)}
                        key={index}
                        title={item}
                    />
                ))}
            </Tab>
        }
        <View style={{ flexDirection: "row", flex: 1 }}>
            <FlashList
                data={songList}
                ref={listRef}
                onEndReached={() => {
                    songList.length && pageChange("next", true);
                }}
                removeClippedSubviews={false}
                keyExtractor={keyExtractor}
                estimatedItemSize={moderateScale(45,1)}
                onViewableItemsChanged={handleViewableItemsChanged}
                renderItem={renderItem}
                ListEmptyComponent={() => <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
                    <Image resizeMode="contain" style={{ width: moderateScale(200), height: moderateScale(200) }}
                           source={require("../assets/imgs/empty.png")}></Image></View>}
                onEndReachedThreshold={1}
            />
            <Pagination ref={paginationRef} onChange={pageChange} />
        </View>
    </>;
}

export default memo(Song, (prevProps, nextProps) => {
    return prevProps.searchText === nextProps.searchText;
});

```
## /Users/thunder/mycode/rn/components/SongItem.tsx

```
import React, { forwardRef, memo, useImperativeHandle, useRef, useState } from "react";
import { Icon, ListItem } from "@rneui/themed";
import { findNodeHandle, Text, GestureResponderEvent, InteractionManager, ToastAndroid } from "react-native";
import {
    addSong,
    delSong,
    fetchGetCurrent,
    setCurrent,
    setDialogTitle,
    setDownloadList,
    setIsActive,
    setOrderList,
    setQrcodeStatus,
    setVipStatus,
    topSong
} from "../store/common";
import { delSong as deleteSong, getHashPath, isExist, request } from "../libs/util";
import AsyncStorage from "@react-native-async-storage/async-storage";
import store, { useAppDispatch, useAppSelector } from "../store";
import AnalyticsUtil from "../libs/AnalyticsUtil";
import commonConfig from "../config.json";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import RNFS from "react-native-fs";
import { moderateScale } from "react-native-size-matters";


function SongItem(props: SongItemProps, ref: any) {
    const dispatch = useAppDispatch();
    const { videoNativeTag } = useAppSelector(state => state.control);
    const marker = useRef<any>();
    const delBtn = useRef<any>();
    const order = (e?: GestureResponderEvent) => {
        // const nativeEvent = e.nativeEvent;
        requestAnimationFrame(async () => {
            if (store.getState().common.activeCode === -2) {
                dispatch(setDialogTitle("会员已过期，请扫码充值!"));
                dispatch(setQrcodeStatus(true));
                return;
            }
            const num = await AsyncStorage.getItem("number");
            if (store.getState().common.activeCode === 0) {
                if (store.getState().common.config.try_num !== 0 && Number(num) >= store.getState().common.config.try_num) {
                    dispatch(setDialogTitle("免费播放次数已用完，扫码激活!"));
                    dispatch(setQrcodeStatus(true));
                    return;
                }
                await AsyncStorage.setItem("number", String(num ? Number(num) + 1 : 1));
            }
            InteractionManager.runAfterInteractions(async () => {
                if (store.getState().common.netType !== "none") {
                    const res = await request(`${global.apiSdkUrl}/plist/add_by_vod?token=${await AsyncStorage.getItem("token") }&company=${commonConfig.company}`, {
                        method: "POST",
                        body: JSON.stringify({
                            "songid": props.item.songid || props.item.songId,
                            "music_name": props.item.music_name || props.item.songName,
                            "singer": props.item.singer || props.item.singerName,
                            "path": props.item.path || ""
                        })
                    });
                    if (res.errcode === 100001) {
                        dispatch(setIsActive({
                            status: false,
                            errMsg: res.errmsg
                        }));
                    } else if (res.errcode === 100002) {
                        dispatch(setVipStatus(true));
                    } else if (res.errcode === 100003) {
                        ToastAndroid.show(res.errmsg, ToastAndroid.SHORT);
                        if (await RNFS.exists(await getHashPath(props.item.songid || props.item.songId))) {
                            await RNFS.unlink(await getHashPath(props.item.songid || props.item.songId));
                        }
                        if (await isExist(props.item.songid || props.item.songId)) {
                            deleteSong(props.item.songid || props.item.songId);
                        }
                    } else {

                        dispatch(setOrderList(res));
                        if (!store.getState().common.current) {
                            dispatch(fetchGetCurrent(true));
                        }
                        // const item = res[res.length - 1];
                        // if (commonConfig.isDownloadMode) {
                        //     const exists = await isExist(item.songid);
                        //     if (!exists || exists.local === 0) {
                        //         if (!store.getState().common.downloadList.find((val: any) => val?.songid === item.songid)) {
                        //             dispatch(setDownloadList([...store.getState().common.downloadList, item]));
                        //         }
                        //     }
                        // }
                        ToastAndroid.show('成功添加曲目' + (props.item.music_name || props.item.songName), ToastAndroid.SHORT);
                        AnalyticsUtil.onEventWithMap("order_song", {
                            songName: props.item.music_name || props.item.songName,
                            songId: props.item.songid || props.item.songId
                        });
                    }
                } else {
                    if (!props.item.path) {
                        ToastAndroid.show("当前无网络连接，连接网络后重试", ToastAndroid.SHORT);
                        return;
                    }
                    if (store.getState().common.activeCode === -1) {
                        ToastAndroid.show("当前设备已到期，充值续费后重试", ToastAndroid.SHORT);
                        return;
                    }
                    dispatch(addSong(props.item));
                    if (!store.getState().common.current) {
                        dispatch(setCurrent(store.getState().common.orderList[0]));
                    }
                    ToastAndroid.show('成功添加曲目' + (props.item.music_name || props.item.songName), ToastAndroid.SHORT);
                }
            });
        });


    };
    const del = () => {
        requestAnimationFrame(async () => {
            if (store.getState().common.netType !== "none") {
                const token = await AsyncStorage.getItem("token");
                request(`${global.apiUrl}/plist/del/${token}/${props.index}`, { method: "POST" }).then(async (res) => {
                    dispatch(setOrderList(res));
                    // if (commonConfig.isDownloadMode) {
                    //     const arr: any = [];
                    //     if (res.length) {
                    //         for (let i = 0; i < res.length; i++) {
                    //             let item = res[i];
                    //             const exists = await isExist(item.songid);
                    //             if (!exists || exists.local === 0) {
                    //                 if(!arr.find((val: any) => val?.songid === item.songid)) {
                    //                     arr.push(item);
                    //                 }
                    //             }
                    //         }
                    //         dispatch(setDownloadList(arr));
                    //     }
                    // }
                });
            } else {
                dispatch(delSong(props.index));
            }
        });

    };
    const goTop = () => {
        requestAnimationFrame(async () => {
            const token = await AsyncStorage.getItem("token");
            if (store.getState().common.netType !== "none") {
                request(`${global.apiUrl}/plist/top/${token}/${props.index}`, { method: "POST" }).then(async (res) => {
                    dispatch(setOrderList(res));
                    // if (commonConfig.isDownloadMode) {
                    //     const arr: any = [];
                    //     if (res.length) {
                    //         for (let i = 0; i < res.length; i++) {
                    //             let item = res[i];
                    //             const exists = await isExist(item.songid);
                    //             if (!exists || exists.local === 0) {
                    //                 if(!arr.find((val: any) => val?.songid === item.songid)) {
                    //                     arr.push(item);
                    //                 }
                    //             }
                    //         }
                    //         dispatch(setDownloadList(arr));
                    //     }
                    // }

                });
            } else {
                dispatch(topSong(props.index));
            }
        });

    };
    useImperativeHandle(ref, () => ({
        order
    }));
    return props.isOrder ?
        <ListItem containerStyle={{
            backgroundColor: "#3D4170",
            borderRadius: moderateScale(3,1),
            justifyContent: "center",
            alignItems: "center",
            paddingVertical: 0,
            paddingHorizontal: moderateScale(10),
            height: moderateScale(40,1),
            marginTop: moderateScale(5,1)
        }}>
            <ListItem.Content>
                <ListItem.Title style={{ fontSize: moderateScale(12,1), color: "#fff" }}
                                numberOfLines={1}>{props.item.music_name || props.item.songName}</ListItem.Title>
                <ListItem.Subtitle style={{
                    color: "rgba(255, 255, 255, 0.7)",
                    fontSize: moderateScale(10,1)
                }}>{props.item.singer || props.item.singerName}</ListItem.Subtitle>
                <ListItem.Subtitle style={{
                    position: "absolute",
                    right: 10,
                    alignItems: "center",
                    flexDirection: "row",
                    justifyContent: "space-between"
                }}>
                    {
                        props.index === 0 &&
                        <Text style={{ fontSize: moderateScale(11,1), color: "#fff", fontFamily: "iconfont" }}>{"\ue62e"}</Text>
                    }
                    {props.index > 1 && <TouchFocusHighlight
                        focusName={"songItem-top-" + props.index}
                        noBorder
                        noScale
                        style={{
                            padding: moderateScale(5,1),
                            borderRadius: moderateScale(2,1)
                        }}
                        onPress={goTop}
                        activeColor="#2089dc">
                        <Text style={{
                            fontSize: moderateScale(16,1),
                            color: "#fff",
                            fontFamily: "iconfont",
                            justifyContent: "center",
                            alignItems: "center"
                        }}>{"\ue6c6"}</Text>
                    </TouchFocusHighlight>}
                    {props.index !== 0 && <TouchFocusHighlight
                        focusName={"songItem-del-" + props.index}
                        noBorder
                        noScale
                        style={{
                            padding: moderateScale(5,1),
                            borderRadius: moderateScale(2,1)
                        }}
                        onPress={del}
                        activeColor="#2089dc">
                        <Text style={{
                            fontSize: moderateScale(16,1),
                            color: "#fff",
                            fontFamily: "iconfont",
                            justifyContent: "center",
                            alignItems: "center"
                        }}>{"\ue608"}</Text>
                    </TouchFocusHighlight>}
                </ListItem.Subtitle>
            </ListItem.Content>
        </ListItem> : <>
            <TouchFocusHighlight
                ref={marker}
                noBorder
                noScale
                focusName={"songItem-" + (props.item.songid || props.item.songId)}
                nextFocusLeft={videoNativeTag}
                nextFocusRight={props.showDelBtn ? findNodeHandle(delBtn.current) : null}
                style={{
                    marginHorizontal: moderateScale(5,1),
                    borderRadius: moderateScale(3,1),
                    backgroundColor: "#3D4170",
                    marginBottom: moderateScale(5,1)
                }}
                activeColor="#2089dc"
                onPress={order}>
                <ListItem containerStyle={{
                    backgroundColor: "transparent",
                    justifyContent: "center",
                    alignItems: "center",
                    borderRadius: moderateScale(3,1),
                    paddingVertical: 0,
                    paddingHorizontal: moderateScale(10),
                    height: moderateScale(40,1)
                }}>
                    {props.serial && <Text style={{ color: "#fff", fontSize: moderateScale(12,1) }}>{props?.index as number + 1}</Text>}
                    <ListItem.Content>
                        <ListItem.Title style={{
                            fontSize: moderateScale(12,1),
                            color: "#fff",
                            paddingRight: (props.showDelBtn || props.item?.is_vip === 1) ? moderateScale(40) : 0
                        }} numberOfLines={1}>{props.item.music_name || props.item.songName}</ListItem.Title>
                        <ListItem.Subtitle style={{
                            color: "rgba(255, 255, 255, 0.7)",
                            fontSize: moderateScale(10,1)
                        }}>{props.item.singer || props.item.singerName}</ListItem.Subtitle>
                        <ListItem.Subtitle style={{
                            position: "absolute",
                            right: moderateScale(5,1),
                            alignItems: "center",
                            flexDirection: "row",
                            justifyContent: "space-between"
                        }}>
                            {
                                props.item?.is_vip === 1 && <Text
                                    style={{ fontFamily: "iconfont", color: "#ffcb93", fontSize: moderateScale(20,1) }}>{"\ue65e"}</Text>
                            }
                            {props.showDelBtn && <TouchFocusHighlight
                                focusName={"songItem-del-" + props.index}
                                ref={delBtn}
                                noBorder
                                noScale
                                nextFocusLeft={findNodeHandle(marker.current)}
                                style={{
                                    padding: moderateScale(5,1),
                                    borderRadius: moderateScale(2,1)
                                }}
                                onPress={() => {
                                    props.onDelPress && props.onDelPress();
                                }}
                                activeColor="#2089dc">
                                <Icon
                                    size={moderateScale(13,1)}
                                    name="trash-outline"
                                    type="ionicon"
                                    color="#ffffff"
                                />
                            </TouchFocusHighlight>}
                        </ListItem.Subtitle>
                    </ListItem.Content>
                </ListItem>
            </TouchFocusHighlight>
        </>;

}

export default memo(forwardRef(SongItem));

```
## /Users/thunder/mycode/rn/components/SpaceDialog.tsx

```
import React, { forwardRef, memo, useEffect, useImperativeHandle, useRef, useState } from "react";
import LinearGradient from "react-native-linear-gradient";
import { findNodeHandle, StyleSheet, Text, TouchableHighlight, View } from "react-native";
import Modal from "react-native-modal";
import { focus } from "@wouterds/react-native-tv-focus";
import { Dialog } from "@rneui/themed";
import { moderateScale, s } from "react-native-size-matters";

function SpaceDialog(props: any, ref: any) {
    const [dialogStatus, setDialogStatus] = useState(false);
    const [text, setText] = useState("");
    const dialogRef = useRef<any>(null);
    useImperativeHandle(ref, () => ( {
        show: (status: boolean) => {
            if(status) {
                setText('U盘')
            } else {
                setText('本地')
            }
            setDialogStatus(true)
        },
    }));
    useEffect(()=> {
        if(dialogStatus) {
            focus(findNodeHandle(dialogRef.current));
        }
    }, [dialogStatus])
    return <Dialog overlayStyle={{ width: s(300), height: s(120), padding: 0, borderRadius: moderateScale(4,1), overflow: "hidden" }} isVisible={dialogStatus} onBackdropPress={() => setDialogStatus(false)}>
        <LinearGradient
            style={{ flex: 1, padding: moderateScale(10), justifyContent: "space-between" }}
            start={{ x: 0.0, y: 0 }} end={{ x: 1, y: 0 }}
            locations={[0.1, 0.7, 1]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={{ alignItems: "center", justifyContent: "center", flex: 1 }}>
                <Text style={{ fontSize: moderateScale(14,1), color: "#fff" }}>{text}存储空间不足，请前往本地模块清理数据！</Text>
            </View>
            <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                <TouchableHighlight ref={dialogRef} style={{ ...styles.exitBtn }} underlayColor="#2089dc" onPress={() =>setDialogStatus(false)}>
                    <Text style={styles.exitBtnText}>关闭</Text>
                </TouchableHighlight>
            </View>
        </LinearGradient>
    </Dialog>

}
const styles = StyleSheet.create({
    exitBtn: {
        paddingVertical:moderateScale(4,1),
        paddingHorizontal:moderateScale(5,1),
        borderRadius:moderateScale(2,1),
    },
    exitBtnText: {
        fontSize:moderateScale(12,1),
        color: '#fff'
    }
})
export default memo(forwardRef(SpaceDialog))

```
## /Users/thunder/mycode/rn/components/TitleBar.tsx

```
import React, { forwardRef, memo, useEffect, useState } from "react";
import Carousel from "react-native-reanimated-carousel";
import { Dimensions, StyleSheet, Text, View } from "react-native";
import { useAppSelector } from "../store";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function TitleBar(props:any, ref:any) {
    const [titleData, setTitleData] = useState<string[]>([]);
    const { current, orderList } = useAppSelector(state => state.common);
    const updateTitleData = () => {
        if (current) {
            setTitleData([`正在播放： ${current.singer || ""}   ${current.music_name}`,
                `下一曲：${orderList.length > 1 ? (orderList[1].singer || "") + "  " + orderList[1].music_name : "未点歌"}`]);

        } else {
            setTitleData(["未点歌"]);
        }
    };
    useEffect(() => {
        updateTitleData();
    }, [current, orderList]);
    return <View style={styles.titleBar}>
        <Carousel
    width={Dimensions.get("window").width}
    height={moderateScale(25,1)}
    vertical
    loop
    enabled={false} // Default is true, just for demo
    style={{ width: "100%" }}
    autoPlay={titleData.length > 1}
    autoPlayInterval={10000}
    data={titleData}
    renderItem={({ item, index }) => <Text style={styles.titleBarText}>{item}</Text>}
    />
</View>
}
const styles = ScaledSheet.create({
    titleBar: {
        position: "absolute",
        paddingVertical: '10@ms1',
        width: "100%",
        // backgroundColor: 'rgba(0,0,0,0.5)',
        top: '5@ms1',
        left: 0
    },
    titleBarText: {
        color: "#fff",
        fontSize: '20@ms',
        fontWeight: "400",
        textAlign: "center"
        // textShadowColor: '#fff',
        // textShadowOffset: {width: 0, height: 1},
        // textShadowRadius: 4,
    },
})
export default memo(forwardRef(TitleBar));

```
## /Users/thunder/mycode/rn/components/TouchFocusHighlight.tsx

```
import React, { forwardRef, memo, useState } from "react";
import {
    TouchableHighlight,
    ViewStyle,
    TouchableHighlightProps,
    GestureResponderEvent,
    RegisteredStyle
} from "react-native";
interface Props extends TouchableHighlightProps {
    focusName?: string
    noBorder?: boolean
    noScale?: boolean,
    scaleNumber?: number
    style?: ViewStyle | any,
    activeColor?: string,
    onHandleFocus?: () => void
    onHandleBlur?: () => void
    onHandlePressIn?: (e:GestureResponderEvent) => void
    onHandlePressOut?: (e:GestureResponderEvent) => void
}
function TouchFocusHighlight(props: Props, ref: any) {
    const [isPressed, setIsPressed] = React.useState(false);
    const [tvBtnFocus, setTvBtnFocus] = useState<boolean>(false);

    return (
        <TouchableHighlight
            ref={ref}
            focusable
            onPress={props.onPress}
            onFocus={(e)=>{
                setTvBtnFocus(true)
                props.onHandleFocus?.()
            }}
            onBlur={()=>{
                setTvBtnFocus(false)
                props.onHandleBlur?.()
            }}
            onPressIn={(e)=> {
                setIsPressed(true);
                props?.onHandlePressIn?.(e)
            }}
            onPressOut={(e)=>{
                setIsPressed(false)
                props?.onHandlePressOut?.(e)
            }}
            activeOpacity={0}
            underlayColor={props.activeColor || props.style?.backgroundColor || "transparent"}
            {...props}
            style={[
                props.style, {
                borderWidth:  props.style?.borderWidth || !props.noBorder ? 2: 0,
                opacity: (isPressed && !props.activeColor  ) ? 0.7 : 1,
                borderColor:  props.style?.borderColor || (tvBtnFocus ? "#fff" : (props.style?.backgroundColor || "transparent"))},
                props.noScale ?{backgroundColor: tvBtnFocus ? props.activeColor: props.style?.backgroundColor || 'transparent'} : {transform: props.style?.transform || [{ scale: tvBtnFocus ? props.scaleNumber || 1.08 : 1 }],zIndex:999}]} >
            <>
                {props.children}
            </>
        </TouchableHighlight>
    );
}
export default memo(forwardRef(TouchFocusHighlight));

```
## /Users/thunder/mycode/rn/components/UnActiveDialog.tsx

```
import React, { memo, useEffect, useRef } from "react";
import LinearGradient from "react-native-linear-gradient";
import { findNodeHandle, StyleSheet, Text, TouchableHighlight, View } from "react-native";
import RNExitApp from "react-native-exit-app";
import { Dialog } from "@rneui/themed";
import { useAppDispatch, useAppSelector } from "../store";
import { focus } from "@wouterds/react-native-tv-focus";
import {isInputLicenseMode} from "../config.json";
import { setHasDialog } from "../store/common.ts";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function UnActiveDialog(props:any) {
    const dispatch = useAppDispatch();
    const {isActive, errMsg} = useAppSelector(state=>state.common);
    const dialogCloseRef = useRef<any>();
    useEffect(()=>{
        if(!isActive) {
            focus(findNodeHandle(dialogCloseRef.current));
        }
        dispatch(setHasDialog(!isActive));
    }, [isActive])
    return <Dialog overlayStyle={styles.Overlay} backdropStyle={{backgroundColor: 'rgba(0,0,0,1)'}} isVisible={!isActive}>
        <LinearGradient
            style={{flex: 1, padding: moderateScale(10), justifyContent: 'space-between'}}
            start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={{alignItems: 'center', justifyContent: 'center', flex: 1}}>
                <Text style={{fontSize: moderateScale(12,1), color: '#fff'}}>{errMsg}</Text>
            </View>
            <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                <TouchableHighlight ref={isInputLicenseMode? null:dialogCloseRef} style={styles.exitBtn} underlayColor="#2089dc" onPress={() => RNExitApp.exitApp()}>
                    <Text style={styles.exitBtnText}>退出</Text>
                </TouchableHighlight>
                {
                    isInputLicenseMode? <TouchableHighlight ref={dialogCloseRef} style={[styles.exitBtn,{marginLeft: moderateScale(5,1) }]} underlayColor="#2089dc" onPress={props.onPress}>
                        <Text style={styles.exitBtnText}>重新输入</Text>
                    </TouchableHighlight>: null
                }

            </View>
        </LinearGradient>
    </Dialog>
}
const styles = ScaledSheet.create({
    Overlay: {
        width: '225@s',
        height: '100@s',
        padding: 0,
        borderRadius: '4@ms1',
        overflow: 'hidden',
        marginTop: -moderateScale(50,1),
    },
    exitBtn: {
        paddingVertical:'3@ms1',
        paddingHorizontal:'5@ms1',
        borderRadius:'2@ms1'
    },
    exitBtnText: {
        fontSize:'12@ms1',
        color: '#fff'
    }
})
export default memo(UnActiveDialog)

```
## /Users/thunder/mycode/rn/components/UpdateDialog.tsx

```
import React, { forwardRef, memo,  useEffect, useImperativeHandle, useRef, useState } from "react";
import { Dialog } from "@rneui/themed";
import LinearGradient from "react-native-linear-gradient";
import { findNodeHandle,StyleSheet, Text, TouchableHighlight, View } from "react-native";
import { focus } from "@wouterds/react-native-tv-focus";
import RNFS from "react-native-fs";
import RNApkInstaller from "@dominicvonk/react-native-apk-installer";
import { useAppDispatch } from "../store";
import { setHasDialog } from "../store/common.ts";
import { moderateScale, ScaledSheet } from "react-native-size-matters";
function UpdateDialog({ url= "", onActive= ()=>{} }, ref: any) {
    const dispatch = useAppDispatch();
    const [isVisible, setIsVisible] = useState(false);
    const[isUpdate, setIsUpdate] = useState(false);
    const [isDownloading, setIsDownloading] = useState(false);
    const [percent, setPercent] = useState('0%');
    const dialogRef = useRef<any>();
    const downloadJobId = useRef<any>();
    const confirm = async () => {
        if(!isUpdate) {
            setIsUpdate(true);
            if(!await await RNFS.exists(RNFS.ExternalDirectoryPath + '/apk')) {
                await RNFS.mkdir(RNFS.ExternalDirectoryPath + '/apk');
            }
            if(await RNFS.exists(RNFS.ExternalDirectoryPath + '/apk/' + url.substring(url.lastIndexOf('/') + 1))) {
                return
            }
            setIsDownloading(true);
            RNFS.downloadFile({
                fromUrl: url,
                toFile: RNFS.ExternalDirectoryPath + '/apk/' + url.substring(url.lastIndexOf('/') + 1),
                background: true,
                begin: ({ jobId }) => {
                    downloadJobId.current = jobId;
                    setIsDownloading(true);
                },
                progress: ({ bytesWritten, contentLength }) => {
                    setPercent((bytesWritten/contentLength * 100).toFixed(0) + '%');
                }
            }).promise
                .then((result) => {
                    if (result.statusCode === 200) {
                        setIsDownloading(false);
                    } else {
                        console.error('File download failed:', result.statusCode);
                    }
                })
                .catch((error) => {
                    console.error('File download error:', error);
                });
            return;
        }
        if(isDownloading) {
            return
        }
        RNApkInstaller.install(RNFS.ExternalDirectoryPath + '/apk/' + url.substring(url.lastIndexOf('/') + 1))
    }
    const cancel = () => {
        setIsVisible(false);
    }
    useImperativeHandle(ref, () => ({
        show: () => {
            setIsVisible(true);
        },
        isVisible
    }))
    useEffect(() => {
        if(isVisible) {
            focus(findNodeHandle(dialogRef.current));
        }
        dispatch(setHasDialog(isVisible));
    }, [isVisible])
    return <Dialog  overlayStyle={styles.Overlay} isVisible={isVisible} onBackdropPress={()=>setIsVisible(false)}>
        <LinearGradient
            style={{flex: 1, padding: moderateScale(10), justifyContent: 'space-between'}}
            start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={{alignItems: 'center', justifyContent: 'center', flex: 1}}>
                <Text style={{fontSize: moderateScale(13,1), color: '#fff'}}>
                    {isUpdate ? (isDownloading ? '正在下载：' + percent:'下载完成，立即安装？') : '新版本已发布，是否立即更新？'}
                </Text>
            </View>
            <View style={{flexDirection: 'row', justifyContent: 'flex-end', alignItems: 'center'}}>
                <TouchableHighlight style={styles.exitBtn} underlayColor="#2089dc" onPress={cancel}>
                    <Text style={styles.exitBtnText}>{isUpdate ? (isDownloading ? '取消' : '稍后安装') : '稍后更新'}</Text>
                </TouchableHighlight>
                <TouchableHighlight ref={dialogRef} style={[styles.exitBtn,{ marginLeft: moderateScale(5,1) }]} underlayColor="#2089dc" onPress={confirm}>
                    <Text style={styles.exitBtnText}>{isUpdate ? (isDownloading ? '下载中' : '立即安装') : '立即更新'}</Text>
                </TouchableHighlight>
            </View>
        </LinearGradient>
    </Dialog>;
}
const styles = ScaledSheet.create({
    Overlay: {
        width: '250@s',
        height: '100@s',
        padding: 0,
        borderRadius: '4@ms1',
        overflow: 'hidden'
    },
    exitBtn: {
        paddingVertical:'3@ms1',
        paddingHorizontal:'5@ms1',
        borderRadius:'2@ms1'
    },
    exitBtnText: {
        fontSize:'12@ms1',
        color: '#fff'
    }
})
export default memo(forwardRef(UpdateDialog))

```
## /Users/thunder/mycode/rn/components/VideoPlayer.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useRef, useState } from "react";
import {
    setPlayStatus,
    setSelectedAudioTrack,
    setVideoNativeTag
} from "../store/control";
import {
    delSong,
    fetchGetCurrent,
    setCurrent,
    setDialogTitle,
    setIsActive,
    setOrderList,
    setQrcodeStatus,
    setVipStatus,
    updateDownloadList,
    updateOrderList
} from "../store/common";
import store, { useAppDispatch, useAppSelector } from "../store";
import {
    Dimensions,
    findNodeHandle, Keyboard, NativeEventEmitter,
    NativeModules,
    StyleSheet,
    ToastAndroid,
    ViewStyle
} from "react-native";
import { addSong, delSong as deleteSong, getHashPath, getList, isExist, request } from "../libs/util";
import RNFS from "react-native-fs";
import Progress from "./Progress";
import AsyncStorage from "@react-native-async-storage/async-storage";
import commonConfig from "../config.json";
import { throttle } from "lodash";
// import Animated, {
//     Easing, ReduceMotion,
//     useAnimatedStyle,
//     useSharedValue,
//     withTiming
// } from "react-native-reanimated";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import Volume from "./Volume.tsx";
import { Source } from "../libs/components.ts";
import { useCallbackState } from "../hooks/useCallBackState.ts";
import { debounce } from "lodash";
import Player from "./Player.tsx";
import SpaceDialog from "./SpaceDialog.tsx";
import TitleBar from "./TitleBar.tsx";
import PlayerControl from "./PlayerControl.tsx";
import Loading from "./Loading.tsx";
import { getRoute, navigationRef } from "../libs/RootNavigation.js";
import usePlayer from "../hooks/usePlayer.ts";
import { moderateScale, s, ScaledSheet, vs } from "react-native-size-matters";

export interface VideoPlayerMethods {
    isFullscreen: boolean;
    toggleRest: () => void;
    onNext: () => void;
    switchAudioTrack: () => void;
    toggleVolume: (status: boolean) => void;
    togglePlay: (status: boolean) => void;
    exit: () => void;
    startActivityTimer: () => void;
}

function VideoPlayer(props: any, ref: any) {
    const { routeName, videoStyle, isFullscreen, fullscreenChange } = usePlayer(props.keyboardHeight);
    const dispatch = useAppDispatch();
    // 全屏控件显示状态
    const [videoSource, setVideoSource] = useState<Source>({});
    const [loopCurrent, setLoopCurrent] = useCallbackState(null);
    const [videoVolume, setVideoVolume] = useState(100);
    const [isDualScreen, setIsDualScreen] = useState(false);
    const { playStatus } = useAppSelector(state => state.control);
    const {
        hasDialog,
        current,
        activeCode
    } = useAppSelector(state => state.common);
    // 加载中歌曲名字显示的状态
    // const opacityAnim = useSharedValue<number>(0);
    // const animatedOpacityStyles = useAnimatedStyle(() => ({
    //     opacity: opacityAnim.value
    // }));
    // 是否正在下载
    const isDownload = useRef(false);
    // 长链接实例
    const websocket = useRef<WebSocket>();
    // 全屏控件显示定时器标识
    const timer = useRef<NodeJS.Timeout>();
    const videoBtnRef = useRef<any>();
    const controlRef = useRef<any>();
    const volumeRef = useRef<any>(null);
    const progressRef = useRef<any>();
    const isMute = useRef<any>(false);
    // 播放器实例
    const player: any = useRef(null);
    // 整在现在的文件的曲目信息
    const downloadCurrent = useRef<any>(null);
    // 标记无已点歌曲播放时的url
    const loopCurrentRef = useRef<any>(null);
    // 重连次数
    const resetNumber = useRef<any>(0);
    const resetSongNumber = useRef<any>(0);
    // 无已点歌曲时循环列表
    const loopList = useRef<any>([]);
    const dialogRef = useRef<any>();
    const currentSource = useRef<any>();
    const loadingRef = useRef<any>();
    const activityTimer = useRef<NodeJS.Timeout>();
    // 切换播放状态
    const togglePlay = useCallback(throttle((status: boolean) => {
        dispatch(setPlayStatus(status));
        if (status) {
            if (!store.getState().control.isPlaying) {
                NativeModules.VideoManagerModule.resume(findNodeHandle(player.current));
            }
        } else {
            if ((activeCode === -1 || activeCode === 1) && store.getState().common.netType !== "none") {
                dispatch(setVipStatus(true));
            }
        }
        startActivityTimer();
    }, 500, { leading: true }), [store.getState().control.isPlaying, isFullscreen, activeCode, store.getState().common.netType]);
    // 加载load数据 处理音轨信息
    const onLoad = (e: any) => {
        resetNumber.current = 0;
        resetSongNumber.current = 0;
        togglePlay(true);
    };
    // 切换音轨
    const switchAudioTrack = useCallback(throttle(() => {
        dispatch(setSelectedAudioTrack(!store.getState().control.selectedAudioTrack));
    }, 500, { leading: true }), [store.getState().control.selectedAudioTrack, isFullscreen]);
    // 设备调节音量 1位最大值， 0最小值
    const toggleVolume = useCallback(throttle((status: boolean) => {
        if (status) {
            volumeRef.current?.increase();
        } else {
            volumeRef.current?.decrease();
        }
    }, 500, { leading: true }), [isFullscreen]);
    // 重唱
    const toggleRest = useCallback(throttle(async () => {
        if (!currentSource.current.path) {
            if (await RNFS.exists(await getHashPath(currentSource.current.songid as string))) {
                let data;
                if (current) {
                    data = {
                        ...current,
                        path: await getHashPath(currentSource.current.songid as string)
                    };
                } else {
                    data = {
                        ...loopCurrentRef.current,
                        path: await getHashPath(currentSource.current.songid as string)
                    };
                }
                setCurrentVideoSource(data);
                if (!store.getState().control.playStatus || !store.getState().control.isPlaying) togglePlay(true);
                return;
            }
        }

        NativeModules.VideoManagerModule.reset(findNodeHandle(player.current));
        if (!store.getState().control.playStatus || !store.getState().control.isPlaying) togglePlay(true);
    }, 500, { leading: true }), [store.getState().control.playStatus, togglePlay, store.getState().control.isPlaying, isFullscreen, currentSource.current, current, loopCurrentRef.current]);
    // 切换下一曲 status true 为主动切换，false 为播放完毕自动切换
    const onNext = useCallback(throttle(async () => {
        if (!store.getState().common.current) { // 没有已点歌曲的时候播放轮播列表
            if (loopList.current.length === 1) {
                toggleRest();
                return;
            }
            let index = loopList.current.findIndex((item: any) => item.songid === loopCurrentRef.current.songid);
            if (index === loopList.current.length - 1) {
                index = 0;
            } else {
                index++;
            }
            setCurrentVideoSource(loopList.current[index]);
            setLoopCurrent(loopList.current[index], (val: any) => {
                loopCurrentRef.current = val;
            });
            return;
        }
        isFullscreen && controlRef.current?.showControl();
        if (store.getState().common.orderList[1]?.songid === store.getState().common.current.songid) {
            toggleRest();
        }
        if (store.getState().common.netType !== "none") { // 设备有网的状态下
            const res = await request(`${global.apiUrl}/plist/cut/${await AsyncStorage.getItem("token")}`, { method: "POST" });
            dispatch(setOrderList(res));
            dispatch(fetchGetCurrent(true));
            // if (commonConfig.isDownloadMode) {
            //     const arr: any = [];
            //     if (res.length) {
            //         for (let i = 0; i < res.length; i++) {
            //             let item = res[i];
            //             const exists = await isExist(item.songid);
            //             if (!exists || exists.local === 0) {
            //                 if(!arr.find((val: any) => val?.songid === item.songid)) {
            //                     arr.push(item);
            //                 }
            //             }
            //         }
            //         dispatch(setDownloadList(arr));
            //     }
            // }
        } else {
            dispatch(delSong(0));
            dispatch(setCurrent(store.getState().common.orderList[0]));
        }
    }, 500, { leading: true }), [isFullscreen]);
    const exitFullScreen = useCallback(() => {
        if (controlRef.current?.isVisible) {
            controlRef.current.hideControl(true);
            return;
        }
        fullscreenChange(false);
    }, [isFullscreen, controlRef.current?.isVisible]);
    // 视频点击
    const videoClick = useCallback(() => {
        if (!isFullscreen) { // 不是全屏切换全屏
            fullscreenChange(true);
        } else { // 全屏状态切换控件显示
            controlRef.current?.switch();
        }
    }, [isFullscreen]);
    // 下载文件
    const downloadFile = async (filePath: string, item: any) => {
        // 判断是否有挂载存储
        const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
        let freeSpace;// 设备剩余空间
        if (exPath.length) {
            freeSpace = await NativeModules.RnUtilsModule.getSDCardPathSpace(exPath[0]);
        } else {
            freeSpace = (await RNFS.getFSInfo()).freeSpace;
        }
        if (freeSpace / Math.pow(2, 30) <= store.getState().common.config?.reserve_storage_size) { // 空间不足1g，弹窗提示
            dialogRef.current?.show(exPath.length > 0);
            return;
        }
        isDownload.current = true;
        // 控制下载进度显示状态
        progressRef.current?.setIsDownload(true);
        progressRef.current?.setProgress({
            value: "0%",
            name: item.music_name
        });
        NativeModules.DownloadSongModule.downloadSong(item.music_name, item.songid.toString(), filePath, store.getState().common.config?.resolution || "720");
    };
    const videoDownloadComplete = async (e: any) => {
        const filePath = e.nativeEvent.filePath;
        /// 获取歌曲的原伴唱轨道信息
        const res = await getSongInfo(current?.songid || loopCurrentRef.current?.songid);
        // 存储本地sq
        addSong(current ? Object.assign({}, current, {
            path: filePath,
            Music_ZTrack: res.result ? res.result.matches[0].Music_ZTrack : 1,
            isActive: true
        }) : Object.assign({}, loopCurrentRef.current, {
            path: filePath,
            Music_ZTrack: res.result ? res.result.matches[0].Music_ZTrack : 1,
            isActive: true
        }));
        ToastAndroid.show(`${current?.music_name || loopCurrentRef.current?.music_name} 已保存到${commonConfig.company ==="dangbei"? "历史" : "本地模块"}`, ToastAndroid.SHORT);
    };
    // x下载队列管理
    const downloadFiles = async () => {
        const item = store.getState().common.downloadList[0];
        downloadCurrent.current = item;
        try {
            // 下载路径不存在直接创建
            if (!await RNFS.exists(await getHashPath(item.songid, true))) {
                await RNFS.mkdir(await getHashPath(item.songid, true));
            }
            // 开始下载
            downloadFile(await getHashPath(item.songid, true), item);
        } catch (e) {
            console.log(e, "download");
        }
    };
    const getOrderList = async () => {
        // 手机点歌获取播放列表，更新播放列表
        const res = await request(`${global.apiUrl}/plist/${await AsyncStorage.getItem("token")}`);
        dispatch(setOrderList(res));
        // if (commonConfig.isDownloadMode) {
        //     const arr: any = [];
        //     if (res.length) {
        //         for (let i = 0; i < res.length; i++) {
        //             let item = res[i];
        //             const exists = await isExist(item.songid);
        //             if (!exists || exists.local === 0) {
        //                 if(!arr.find((val: any) => val?.songid === item.songid)) {
        //                     arr.push(item);
        //                 }
        //             }
        //         }
        //         dispatch(setDownloadList(arr));
        //     }
        // }
    };
    // 长链接获取消息
    const onMessage = async (event: any) => {
        let obj: any;
        try {
            obj = JSON.parse(decodeURIComponent(JSON.parse(event.data).text));
        } catch (e) {
            console.log(e);
        }
        if (typeof obj === "object") {
            switch (obj.type) {
                // 播放状态切换
                case "toggle_p":
                    togglePlay(!store.getState().control.playStatus);
                    break;
                // 重唱
                case "reset":
                    toggleRest();
                    break;
                case "toggle_c":
                    switchAudioTrack();
                    break;
                case "order":
                    order(obj.params);
                    break;
                case "next":
                    await getOrderList();
                    dispatch(fetchGetCurrent(true));
                    if (store.getState().common.current) {
                        if (store.getState().common.orderList[0]?.songid === store.getState().common.current.songid) {
                            toggleRest();
                        }
                    } else {
                        onNext();
                    }
                    break;
                case "toggle_vol":
                    toggleVolume(obj.params === 1);
                    break;
                default:
                    break;
            }
        }
    };
    const order = async (params: any) => {
        if (params) {
            let item: any = {};
            if (typeof params === "object") {
                item = params;
            } else {
                item = JSON.parse(params).item;
            }
            const num = await AsyncStorage.getItem("number");
            if (store.getState().common.activeCode === 0) {
                if (store.getState().common.config.try_num !== 0 && Number(num) >= store.getState().common.config.try_num) {
                    dispatch(setDialogTitle("免费播放次数已用完，扫码激活!"));
                    dispatch(setQrcodeStatus(true));
                    return;
                }
                await AsyncStorage.setItem("number", String(num ? Number(num) + 1 : 1));
            }
            request(`${global.apiSdkUrl}/plist/add_by_vod?token=${await AsyncStorage.getItem("token")}&company=${commonConfig.company}`, {
                method: "POST",
                body: JSON.stringify({
                    "songid": item.songid || item.songId,
                    "music_name": item.music_name || item.songName,
                    "singer": item.singer || item.singerName,
                    "path": item.path || ""
                })
            }).then(async res => {
                if (res.errcode === 100001) {
                    dispatch(setIsActive({
                        status: false,
                        errMsg: res.errmsg
                    }));
                } else if (res.errcode === 100002) {
                    dispatch(setVipStatus(true));
                } else if (res.errcode === 100003) {
                    ToastAndroid.show(res.errmsg, ToastAndroid.SHORT);
                    if (await RNFS.exists(await getHashPath((item.songid || item.songId) as string))) {
                        await RNFS.unlink(await getHashPath(item.songid || item.songId));
                    }
                    if (await isExist(item.songid || item.songId)) {
                        deleteSong(item.songid || item.songId);
                    }
                } else {
                    dispatch(setOrderList(res));
                    if (!store.getState().common.current) {
                        dispatch(fetchGetCurrent(true));
                    }
                    // if (commonConfig.isDownloadMode) {
                    //     const exists = await isExist(res[res.length - 1].songid);
                    //     if (!exists || exists.local === 0) {
                    //         if (!store.getState().common.downloadList.find((val: any) => val.songid === res[res.length - 1].songid.songid)) {
                    //             dispatch(setDownloadList([...store.getState().common.downloadList, res[res.length - 1]]));
                    //         }
                    //     }
                    // }

                }
            });
        } else {
            getOrderList();
        }
    };
    // 初始化websoket长链接
    const initWebSocket = async () => {
        websocket.current = new WebSocket(`wss://mc.ktv.com.cn/ws/${await AsyncStorage.getItem("token")}`);
        websocket.current.onopen = () => {
            console.log("WebSocket connected");
        };

        websocket.current.onmessage = onMessage;
    };

    const getSongInfo = async (id: number) => { // 获取音轨信息方法
        return request(`${global.url}/MusicService.aspx?op=getmusicinfobynos&depot=2&nos=${id}`);
    };
    const getLoopList = async () => { // 获取本地已下载的歌曲用于轮播，当前只取20首
        // if (await RNFS.exists(RNFS.ExternalDirectoryPath + "/download/7588436.ts")) {
        //     loopList.current = [{
        //         songid: "7588436",
        //         music_name: "我和我的祖国(HD)",
        //         singer: "王菲",
        //         path: RNFS.ExternalDirectoryPath + "/download/7588436.ts"
        //     }];
        // } else {
        //     progressRef.current?.setIsDownload(false);
        //     NativeModules.DownloadSongModule.downloadSong("我和我的祖国(HD)", "7588436", RNFS.ExternalDirectoryPath + "/download", store.getState().common.config?.resolution || "720");
        //     loopList.current = [{
        //         songid: "7588436",
        //         music_name: "我和我的祖国(HD)",
        //         singer: "王菲"
        //     }];
        // }
        const res = await getList(1, 30);
        if (res.length) {
            loopList.current = (res);
        } else {
            loopList.current = [{
                songid: "7588436",
                music_name: "我和我的祖国(HD)",
                singer: "王菲"
            }];
        }
    };

    // 视频加载错误回调
    const videoError = (e: any) => {
        console.log("videoErr", e.nativeEvent, resetNumber.current);
        if (resetNumber.current === 5) {
            ToastAndroid.show(`曲目${current?.music_name || loopCurrentRef.current?.music_name}加载失败，已为您切换下一首`, ToastAndroid.SHORT);

            onNext();
            resetSongNumber.current += 1;
            resetNumber.current = 0;
            return;
        }
        resetNumber.current += 1;
        if (resetSongNumber.current === 10) {
            ToastAndroid.show("多次尝试重新加载失败，已为您取消重新加载", ToastAndroid.SHORT);
            resetSongNumber.current = 0;
            return;
        }
        toggleRest();
    };
    const startActivityTimer = useCallback(() => {
        if (!isFullscreen &&
            !hasDialog &&
            playStatus
        ) {
            if (activityTimer.current) {
                clearTimeout(activityTimer.current);
            }
            // 启动定时器来检测用户活动
            activityTimer.current = setTimeout(() => {
                fullscreenChange(true);
            }, 60000); // 60秒，您可以根据需要调整时间
        } else {
            if (activityTimer.current) {
                clearTimeout(activityTimer.current);
            }
        }
    }, [isFullscreen, hasDialog, playStatus]);
    useImperativeHandle(ref, (): VideoPlayerMethods => {
        return {
            isFullscreen,
            toggleRest,
            onNext,
            switchAudioTrack,
            toggleVolume,
            togglePlay,
            startActivityTimer,
            exit: exitFullScreen
        };
    });
    const xiaoAiEvent = (res: any) => {
        switch (res.type) {
            case "doPause":
                togglePlay(false);
                break;
            case "doPlay":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                if (store.getState().control.playStatus) {
                    NativeModules.VideoManagerModule.resume(findNodeHandle(player.current));
                } else {
                    togglePlay(true);
                }
                break;
            case "doOriginal":
                dispatch(setSelectedAudioTrack(true));
                break;
            case "doAccompany":
                dispatch(setSelectedAudioTrack(false));
                break;
            case "doReplay":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                toggleRest();
                break;
            case "doNext":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                onNext();
                break;
            case "doMute":
                setVideoVolume(0);
                isMute.current = true;
                break;
            case "doRecovery":
                setVideoVolume(100);
                isMute.current = false;
                break;
            case "doBGMUp":
                toggleVolume(true);
                break;
            case "doBGMDown":
                toggleVolume(false);
                break;
            case "setVolume":
                volumeRef.current.setVolume(res.params.volume);
                break;
            case "addSong":
                order({
                    songid: res.params?.mediaSerialNo,
                    music_name: res.params?.mediaName,
                    singer: res.params.starName
                });
                break;
            case "doXiaoAiPlayStart":
                if (!isMute.current) {
                    setVideoVolume(40);
                }
                break;
            case "doXiaoAiPlayStop":
                if (!isMute.current) {
                    setVideoVolume(100);
                }
                break;
            default:
                break;
        }
    };
    const voiceEvent = (res: any) => {
        switch (res.action) {
            case "pause":
                togglePlay(false);
                break;
            case "play":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                if (store.getState().control.playStatus) {
                    NativeModules.VideoManagerModule.resume(findNodeHandle(player.current));
                } else {
                    togglePlay(true);
                }
                break;
            case "original":
                dispatch(setSelectedAudioTrack(true));
                break;
            case "accomp":
                dispatch(setSelectedAudioTrack(false));
                break;
            case "replay":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                toggleRest();
                break;
            case "next":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                onNext();
                break;
            case "enter_full_screen":
                fullscreenChange(true);
                break;
            case "exit_full_screen":
                fullscreenChange(false);
                break;
            case "open_sang":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                props?.onShowOrder();
                break;
            case "open_local":
                if (store.getState().common.vipStatus) {
                    dispatch(setVipStatus(false));
                }
                props?.onChange("List", "local", "本地");
                break;
            default:
                break;
        }
    };
    const onDownloadListener = async (data: any) => {
        if (data.type === "onProgress") {
            progressRef.current?.setProgress({
                value: data.progress + "%",
                name: data.songName
            });
        } else if (data.type === "onCompleted") {
            if (data.songid !== "7588436") {
                progressRef.current?.setIsDownload(false);
                isDownload.current = false;
                /// 获取歌曲的原伴唱轨道信息
                const res = await getSongInfo(data.songid);
                // 存储本地sq
                addSong({
                    ...downloadCurrent.current,
                    path: data.path,
                    Music_ZTrack: res.result ? res.result.matches[0].Music_ZTrack : 1,
                    isActive: true
                });
                dispatch(updateOrderList({ ...downloadCurrent.current, path: data.path }));
                if (store.getState().common.downloadList.length) {
                    // 正在下载的歌曲和下载列表的第一个是同一个 删除第一个
                    if (downloadCurrent.current.songid === store.getState().common.downloadList[0]?.songid) {
                        dispatch(updateDownloadList(false));
                    } else {
                        // 如果正在下载完成的不在第一个，从列表中删除
                        if (store.getState().common.downloadList.find((val: any) => val?.songid === downloadCurrent.current?.songid)) {
                            dispatch(updateDownloadList(downloadCurrent.current));
                        } else {
                            downloadFiles();
                        }
                    }
                }
            }
        } else if (data.type === "onError") {
            ToastAndroid.show("下载失败, 请重试！", ToastAndroid.SHORT);
            progressRef.current?.setIsDownload(false);
            isDownload.current = false;
            if (store.getState().common.downloadList.length) {
                if (downloadCurrent.current.songid === store.getState().common.downloadList[0]?.songid) {
                    dispatch(updateDownloadList(false));
                } else {
                    if (store.getState().common.downloadList.find((val: any) => val?.songid === downloadCurrent.current?.songid)) {
                        dispatch(updateDownloadList(downloadCurrent.current));
                    } else {
                        downloadFiles();
                    }
                }
            }
        }
    };
    const playLoop = async () => {
        await getLoopList();
        const index = parseInt((Math.random() * loopList.current.length).toString());
        setCurrentVideoSource(loopList.current[index]);
        setLoopCurrent(loopList.current[index], (val: any) => {
            loopCurrentRef.current = val;
        });
    };

    const setCurrentVideoSource = async (data: any) => {
        currentSource.current = data;
        if (data.path && await RNFS.exists(data.path)) { // 从本地模块添加的歌曲存在path
            setVideoSource({
                uri: data.path,
                Music_ZTrack: data.Music_ZTrack
            });
        } else {
            if (store.getState().common.netType !== "none") {
                // 从网络模块添加的歌曲 判断本地是否有文件， 有直接播放 没有边下边播
                if (await RNFS.exists(await getHashPath(data.songid))) {
                    setVideoSource({
                        uri: await getHashPath(data.songid),
                        Music_ZTrack: data.Music_ZTrack
                    });
                } else {
                    let isDownload = commonConfig.isDownloadMode;
                    // 判断是否有挂载存储
                    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
                    let freeSpace;// 设备剩余空间
                    if (exPath.length) {
                        freeSpace = await NativeModules.RnUtilsModule.getSDCardPathSpace(exPath[0]);
                    } else {
                        freeSpace = (await RNFS.getFSInfo()).freeSpace;
                    }
                    if (freeSpace / Math.pow(2, 30) <= store.getState().common.config?.reserve_storage_size) { // 空间不足1g，弹窗提示
                        dialogRef.current?.show(exPath.length > 0);
                        isDownload = false;
                    }
                    if(commonConfig.company === 'dangbei' && (await getList(1, 20)).length >= 10) {
                        isDownload = false;
                    }
                    setVideoSource({
                        songId: data.songid.toString(),
                        songName: data.music_name,
                        path: await getHashPath(data.songid, true),
                        isDownload: isDownload,
                        resolution: store.getState().common.config?.resolution || "720",
                        Music_ZTrack: data.Music_ZTrack
                    });
                }

            } else {
                onNext();
            }

        }
    };
    const handleChange = (type: string, status?: boolean) => {
        switch (type) {
            case "next":
                onNext();
                break;
            case "play":
                togglePlay(status);
                break;
            case "reset":
                toggleRest();
                break;
            case "order":
                props?.onShowOrder();
                break;
            case "volumeP":
                toggleVolume(true);
                break;
            case "volumeS":
                toggleVolume(false);
                break;
            case "track":
                switchAudioTrack();
                break;
            case "back":
                if (commonConfig.isFullScreenMode) {
                    if (controlRef.current.isVisible) {
                        controlRef.current.hideControl(true);
                        return;
                    }
                    props.onBack();
                } else {
                    fullscreenChange(false);
                }
                break;
        }
    };

    useEffect(() => {
        const xiaoAiEmitter = new NativeEventEmitter(NativeModules.RnXiaoAiModule);
        const nativeEventEmitter = new NativeEventEmitter(NativeModules.RnUtilsModule);
        const voiceListener = nativeEventEmitter.addListener("voiceEvent", voiceEvent);
        const keyboardListener = nativeEventEmitter.addListener("onKeyDown", (keyCode: number) => {
            if (keyCode === 300) {
                switchAudioTrack();
            }
        });
        const xiaoAiListener = xiaoAiEmitter.addListener("xiaoAiEvent", xiaoAiEvent);
        const downloadNativeEventEmitter = new NativeEventEmitter(NativeModules.DownloadSongModule);
        const downloadListener = downloadNativeEventEmitter.addListener("downloadListener", onDownloadListener);
        return () => {
            xiaoAiListener.remove();
            downloadListener.remove();
            voiceListener.remove();
            keyboardListener.remove();
        };
    }, []);
    useEffect(() => {
        if (store.getState().common.netType && store.getState().common.netType !== "none") {
            activeCode !== -99 && initWebSocket();
        }
        return () => {
            if (websocket.current) {
                websocket.current.close();
            }
            timer.current && clearTimeout(timer.current);
        };
    }, [store.getState().common.netType, activeCode]);


    // useEffect(() => {
    //     if (store.getState().common.downloadList.length) {
    //         if (!isDownload.current) {
    //             downloadFiles();
    //         }
    //     }
    // }, [store.getState().common.downloadList]);
    useEffect(() => {
        if (activeCode !== -99) {
            if (current) {
                setCurrentVideoSource(current);
            } else {
                playLoop();
            }
        }
    }, [current, activeCode]);
    useEffect(() => {
        if (websocket.current) {
            websocket.current.onmessage = onMessage;
        }
    }, [store.getState().control.playStatus, store.getState().control.selectedAudioTrack, volumeRef.current?.volume]);
    // useEffect(() => {
    //     if (loading) {
    //         opacityAnim.value = 1;
    //     } else {
    //         opacityAnim.value = withTiming(0, { duration: 500, easing: Easing.linear,reduceMotion: ReduceMotion.Never });
    //     }
    // }, [loading]);
    useEffect(() => {
        startActivityTimer();
    }, [hasDialog, isFullscreen, playStatus]);
    return <><TouchFocusHighlight
        ref={videoBtnRef}
        focusName="video"
        nextFocusLeft={routeName === "List" ? findNodeHandle(videoBtnRef.current) : undefined}
        onLayout={() => {
            dispatch(setVideoNativeTag(videoBtnRef.current?._nativeTag));
        }}
        scaleNumber={1.02}
        noBorder={isFullscreen}
        style={isFullscreen ? styles.fullscreen : {
            ...styles.videoView, ...videoStyle,
            borderRadius: moderateScale(6,1)
        }}
        onPress={videoClick}
        activeColor="#000">
        <>
            {
                activeCode !== -99 && <Player
                    ref={player}
                    onLoad={onLoad}
                    onProgress={(currentTime: number) => {
                        loadingRef.current.setLoading(currentTime <= 2.5 && currentTime > 0);
                    }}
                    name={`${current ? current.singer : loopCurrent?.singer}&_&${current ? current.music_name : loopCurrent?.music_name}`}
                    isFullscreen={isFullscreen}
                    volume={videoVolume}
                    onDisplayChanged={setIsDualScreen}
                    onDownloadComplete={videoDownloadComplete}
                    onVideoError={videoError}
                    onNext={onNext}
                    source={videoSource}
                />
            }
            {
                isFullscreen ? (
                    <>
                        {!isFullscreen &&<TitleBar />}
                        <PlayerControl ref={controlRef} onActive={startActivityTimer} onChange={handleChange} />
                    </>

                ) : ""
            }
            <Loading ref={loadingRef} isFullscreen={isFullscreen}
                     singer={current ? current.singer : loopCurrent?.singer}
                     musicName={current ? current.music_name : loopCurrent?.music_name} />
        </>
    </TouchFocusHighlight>
        <SpaceDialog ref={dialogRef} />
        <Progress ref={progressRef} />
        <Volume ref={volumeRef} />
    </>;

}

const styles = StyleSheet.create({
    videoView: {
        position: "absolute",
        zIndex: 20,
        width: "100%",
        borderWidth: 2,
        backgroundColor: "#000",
        overflow: "hidden"
    },
    fullscreen: {
        position: "absolute",
        left: 0,
        top: 0,
        width: "100%",
        height: "100%",
        zIndex: 999,
        transform: [{ scale: 1 }],
        borderColor: "transparent",
        borderRadius: 0,
        backgroundColor: "black"
    }
});
export default memo(forwardRef(VideoPlayer));

```
## /Users/thunder/mycode/rn/components/VipDialog.tsx

```
import React, { memo, useEffect, useRef, useState } from "react";
import { setVipStatus } from "../store/common.ts";
import {
    findNodeHandle,
    ScrollView,
    StyleSheet, Text,
    useWindowDimensions,
    View
} from "react-native";
import QRCode from "react-native-qrcode-svg";
import { Dialog, Icon } from "@rneui/themed";
import { useAppDispatch, useAppSelector } from "../store";
import { focus } from "@wouterds/react-native-tv-focus";
import LinearGradientText from "./LinearGradientText.tsx";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import LinearGradient from "react-native-linear-gradient";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function VipDialog(props:any) {
    const dimensions = useWindowDimensions();
    const [activePackage, setActivePackage] = useState(0);
    const [isPressed, setIsPressed] = useState(999);
    const dispatch = useAppDispatch();
    const {config, vipStatus,activeCode} = useAppSelector(state=>state.common);
    const dialogCloseRef = useRef<any>();
    const dialogRef = useRef<any>();
    const packageRefs = useRef<any>([]);
    const packageChange=(index:number)=> {
        setActivePackage(index);
    }
    useEffect(()=>{
        if(vipStatus) {
           focus(findNodeHandle(dialogRef.current));
        } else {
            setActivePackage(0);
        }
    }, [vipStatus, config]);
    return config?.vip_dialog?.length ? <Dialog overlayStyle={{width: dimensions.width- moderateScale(40,1),height: dimensions.height - moderateScale(40,1), padding: 0,backgroundColor: 'transparent',borderRadius: moderateScale(5,1), overflow: 'hidden'}} isVisible={vipStatus} onBackdropPress={()=>{
        dispatch(setVipStatus(false))
        props.onVerify(true)
    }}>
        <LinearGradient
            style={{flex: 1, flexDirection: 'column', padding:moderateScale(20,1)}}
            start={{ x : 0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <View style={styles.header}>
                <LinearGradientText
                    text="百万曲库免费下载"
                    width={(dimensions.width-moderateScale(80,1))/2}
                    height={moderateScale(25,1)}
                    size={moderateScale(20,1)}
                    x={moderateScale(80,1)}
                    y={moderateScale(18,1)}
                    x2={(dimensions.width-moderateScale(80,1))/4 + moderateScale(15,1)}
                    colors={['#FFEF9B','#FF7562']}
                />
                <LinearGradientText
                    style={{marginLeft: moderateScale(100,1)}}
                    text="戏曲 红歌 广场舞 儿歌 怀旧经典"
                    width={(dimensions.width-moderateScale(80,1))/2}
                    height={moderateScale(40,1)}
                    size={moderateScale(20)}
                    x={(dimensions.width-moderateScale(80,1))/4 + moderateScale(20)}
                    y={moderateScale(20)}
                    x2={(dimensions.width-moderateScale(80,1))/4 + moderateScale(20)}
                    colors={['#FFEF9B','#FFF0B9']}
                />
            </View>
            <View ref={dialogRef} focusable nextFocusRight={dialogCloseRef.current?._nativeTag} nextFocusDown={packageRefs.current[0]?._nativeTag} nextFocusLeft={packageRefs.current[0]?._nativeTag} nextFocusUp={dialogCloseRef.current?._nativeTag} style={{flex:1, flexDirection: 'row', marginTop: moderateScale(10,1)}}>
                <ScrollView style={styles.packageList}>
                    {
                        config.vip_dialog.map((item:any, index:number)=>(
                            <TouchFocusHighlight
                                ref={ref=>{packageRefs.current[index] = ref}}
                                key={index}
                                noBorder
                                noScale
                                nextFocusUp={index === 0 ? dialogCloseRef.current?._nativeTag : packageRefs.current[index-1]?._nativeTag}
                                nextFocusDown={index === config.vip_dialog.length - 1 ? packageRefs.current[config.vip_dialog.length - 1]?._nativeTag : packageRefs.current[index+1]?._nativeTag}
                                nextFocusRight={dialogCloseRef.current?._nativeTag}
                                nextFocusLeft={packageRefs.current[index]?._nativeTag}
                                activeColor="#FFE8AD"
                                onHandlePressOut={()=>setIsPressed(999)}
                                onHandlePressIn={()=>setIsPressed(index)}
                                onHandleFocus={()=>packageChange(index)}
                                onPress={()=>packageChange(index)}
                                style={Object.assign({},styles.packageListItem,{ backgroundColor: (activePackage === index || isPressed === index) ? '#FFE8AD' : '#464350' })}>
                                {item.top_left_badge && <LinearGradient
                                    style={styles.tag}
                                    start={{ x: 0.0, y: 0 }} end={{ x: 1, y: 1 }}
                                    locations={[0, 1]}
                                    colors={["#F73030", "#9441E6"]}
                                ><Text style={{ fontSize: moderateScale(8,1), color: "#fff" }}>{item.top_left_badge}</Text></LinearGradient>}
                                <View style={styles.price}>
                                    <View style={styles.price1}>
                                        <Text style={[styles.symbol,{color: activePackage === index || isPressed === index? '#624E07' : '#FEEBB6'}]}>¥ </Text>
                                        <Text style={[styles.price1Text,{color: activePackage === index || isPressed === index? '#624E07' : '#FEEBB6'}]}>{item.badge} </Text>
                                        <Text style={[styles.symbol,{color: activePackage === index || isPressed === index? '#624E07' : '#FEEBB6'}]}>/天</Text>
                                    </View>
                                    <View style={styles.price1}>
                                        <Text style={[styles.price2Text1,{color: activePackage === index || isPressed === index? '#624E07' : '#FEEBB6'}]}>¥{item.price}</Text>
                                        <Text style={[styles.price2Text2,{color: activePackage === index || isPressed === index? '#9d8d56' : '#AFA381'}]}>¥{item.original}</Text>
                                    </View>
                                </View>
                                <View style={styles.period}>
                                    <Text style={[styles.periodText, {color: activePackage === index || isPressed === index? '#624E07' : '#FEEBB6'}]}>{item.months}个月</Text>
                                </View>
                            </TouchFocusHighlight>
                        ))
                    }
                </ScrollView>
                <View style={styles.qrcodeBox}>
                    <View style={styles.qrcode}>
                        <QRCode
                            value={config?.vip_dialog[activePackage]?.qr}
                            color="#000"
                            backgroundColor="#fff"
                            size={moderateScale(90,1)}
                        />
                    </View>
                    <Text style={styles.qrcodeText}>{props?.expireTime ? '会员到期时间：' + props?.expireTime : '解锁VIP 无限畅嗨'}</Text>
                </View>
            </View>
        </LinearGradient>
        <TouchFocusHighlight
            ref={dialogCloseRef}
            style={styles.closeBtn}
            noBorder
            noScale
            nextFocusLeft={findNodeHandle(packageRefs.current[0])}
            nextFocusDown={findNodeHandle(packageRefs.current[0])}
            nextFocusUp={findNodeHandle(dialogCloseRef.current)}
            nextFocusRight={findNodeHandle(dialogCloseRef.current)}
            activeColor="#FFE8AD" onPress={() => {
            props.onVerify(true)
            dispatch(setVipStatus(false));
        }}>
            <Icon
                size={moderateScale(18,1)}
                name='close-outline'
                type='ionicon'
                color='#a4a4a4'
            />
        </TouchFocusHighlight>
    </Dialog>: null
}
const styles= ScaledSheet.create({
    header: {
        height: '40@s',
    },
    packageList: {
        flex: 1
    },
    tag: {
       paddingHorizontal: '5@ms1',
        paddingVertical: 2,
        alignItems: 'center',
        borderBottomRightRadius:6,
        borderTopRightRadius:6,
        justifyContent: 'center',
        position: "absolute",
        left:0,
        top:0
    },
    packageListItem: {
        backgroundColor: '#35308f',
        borderRadius: '3@ms1',
        overflow: 'hidden',
        paddingHorizontal: '40@ms1',
        paddingVertical: '10@ms',
        flexDirection: 'row',
        marginTop: '5@ms1'
    },
    price: {
        flex:1
    },
    symbol: {
      fontSize: '11@ms1',
      color : '#FEEBB6'
    },
    price1Text: {
      fontSize: '14@ms1',
      color : '#FEEBB6'
    },
    price1: {
        flexDirection: 'row',
        alignItems: "flex-end"
    },
    price2Text1: {
        fontSize: '11@ms1',
        color : '#FEEBB6'
    },
    price2Text2: {
        fontSize: '11@ms1',
        color : 'rgb(175,163,129)',
        textDecorationLine: 'line-through',
        marginLeft: '5@ms1'
    },
    period: {
        flex:1,
        alignItems: 'flex-end',
        justifyContent: 'center',
    },
    periodText: {
      color: '#FEEBB6',
      fontSize: '13@ms1'
    },
    qrcodeBox: {
        width: '160@s',
        marginLeft: '20@s',
        alignItems: 'center',
        justifyContent: 'center',
    },
    qrcode: {
        width: '100@s',
        height: '100@s',
        backgroundColor: '#fff',
        alignItems: 'center',
        justifyContent: 'center',
        borderRadius:'5@ms1',
    },
    qrcodeText: {
        color: '#FFE179',
        fontSize: '12@ms1',
        marginTop: '10@ms1',
        textAlign: 'center'
    },
    closeBtn: {position: 'absolute', right: '10@ms1', top:'10@ms1',borderRadius:moderateScale(4,1), backgroundColor:'rgba(0,0,0,0.4)', padding:moderateScale(4,1), alignItems: 'center', justifyContent: 'center'}
})

export default memo(VipDialog, (prevProps, nextProps) => prevProps?.expireTime === nextProps?.expireTime)

```
## /Users/thunder/mycode/rn/components/VoiceHelpDialog.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useRef, useState } from "react";
import LinearGradient from "react-native-linear-gradient";
import {
    findNodeHandle,
    ScrollView,
    StyleSheet,
    Text,
    TouchableHighlight,
    useTVEventHandler,
    View
} from "react-native";
import { Dialog, Divider, Icon, TabView } from "@rneui/themed";
import tabData from "../libs/tabData.ts";
import { focus } from "@wouterds/react-native-tv-focus";
import commonConfig from "../config.json";
import { setHasDialog } from "../store/common.ts";
import { useAppDispatch } from "../store";
import { moderateScale, ScaledSheet } from "react-native-size-matters";

function VoiceHelpDialog(props: any, ref: any) {
    const dispatch = useAppDispatch();
    const [isVisible, setIsVisible] = useState(false);
    const [activeTab, setActiveTab] = useState(0);
    const [activeValue, setActiveValue] = useState(0);
    const dialogTabRef = useRef<any>();
    useImperativeHandle(ref, () => ({
        show() {
            setIsVisible(true);
        },
        isVisible
    }));
    const myTVEventHandler = useCallback((evt:any) => {
        if(isVisible) {
            if(evt.eventType === 'right') {
                if(activeTab === 0) {
                    focus(findNodeHandle(dialogTabRef.current));
                }
            }
        }
    }, [isVisible,activeTab]);
    useTVEventHandler(myTVEventHandler);
    useEffect(() => {
        dispatch(setHasDialog(isVisible))
    }, [isVisible]);
    return <Dialog isVisible={isVisible} overlayStyle={styles.Overlay} onBackdropPress={()=>setIsVisible(false)}>
        <LinearGradient
            style={{flex: 1}}
            start={{ x : 0, y : 0 }} end={{ x : 1, y : 1 }}
            locations={[ 0, 0.5, 1 ]}
            colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
        >
            <TouchableHighlight style={styles.Close} underlayColor="#2089dc" onPress={() => setIsVisible(false)}>
                <Icon
                    size={moderateScale(18,1)}
                    name='close-outline'
                    type='ionicon'
                    color='#ffffff'
                />
            </TouchableHighlight>
            <View style={styles.TabNav}>
                <TouchableHighlight activeOpacity={1} underlayColor="#2089dc" style={[styles.TabNavBtn,{ backgroundColor: activeTab === 0 ? '#2089dc' : 'transparent'}]} onFocus={()=>setActiveTab(0)} onPress={()=>setActiveTab(0)}>
                    <Text style={styles.TabNavBtnText}>功能说明</Text>
                </TouchableHighlight>
                <TouchableHighlight activeOpacity={1} underlayColor="#2089dc" style={[styles.TabNavBtn,{ backgroundColor: activeTab === 1 ? '#2089dc' : 'transparent'}]} onFocus={()=>setActiveTab(1)} onPress={()=>setActiveTab(1)}>
                    <Text style={styles.TabNavBtnText}>命令词</Text>
                </TouchableHighlight>
            </View>

            <TabView value={activeTab} onChange={setActiveTab} disableTransition>
                <TabView.Item style={{ width: '100%', paddingHorizontal:moderateScale(20,1), paddingVertical: moderateScale(10,1) }}>
                    <Text style={{fontSize: moderateScale(11,1), lineHeight:moderateScale(24,1),color: 'rgba(255,255,255, 0.8)'}}>
                        Hi, 我是您的语音助手;{'\n'}
                        {commonConfig.company === 'dangbei' ?"您可以对我说‘小爱同学’唤醒语音助手；\n":""}
                        您可以对话筒说对应的语音指令;{'\n'}
                        连接网络后才能使用语音助手~。
                    </Text>
                </TabView.Item>
                <TabView.Item style={{width: '100%'}}>
                    <View style={{flexDirection: 'row', justifyContent: 'flex-start', width: '100%'}}>
                        <View style={{width:moderateScale(110,1), marginVertical:moderateScale(10,1), paddingHorizontal:moderateScale(10,1)}}>
                            <ScrollView>
                                <Divider style={{marginBottom: moderateScale(5,1), height:2}}/>
                                {
                                    tabData.map((item, index)=>(
                                        <View key={item.name}>
                                            <TouchableHighlight style={[styles.TabBtn,{ backgroundColor: activeValue ===index ? '#4894D2' : 'transparent' }]} underlayColor="#2089dc" onFocus={()=>setActiveValue(index)} onPress={()=>setActiveValue(index)}>
                                                <Text style={styles.TabBtnText}>{item.name}</Text>
                                            </TouchableHighlight>
                                            <Divider style={{marginVertical: moderateScale(5,1), height:2}}/>
                                        </View>
                                    ))
                                }
                            </ScrollView>
                        </View>
                        <View style={{flex:1, paddingVertical:moderateScale(10,1), paddingHorizontal:moderateScale(20)}}>
                            {
                                tabData[activeValue]?.text.map((item, index)=>(
                                    <Text key={index} style={styles.TabViewText}>{index+1}. {item}</Text>
                                ))
                            }
                        </View>
                    </View>
                </TabView.Item>
            </TabView>

        </LinearGradient>
    </Dialog>
}
const styles = ScaledSheet.create({
    Overlay: {
        padding: 0,
        overflow: 'hidden',
        borderRadius: '4@ms1',
        height: '80%',
        width: '400@s'
    },
    Close: {
        position: 'absolute',
        right: '10@ms1',
        top: '2@ms1',
        borderRadius:'2@ms1',
        padding:'4@ms1',
        alignItems: 'center',
        justifyContent: 'center',
        zIndex:10
    },
    TabNav: {
        borderBottomWidth: 1,
        borderStyle: "solid",
        flexDirection: 'row',
        borderColor: 'rgba(255,255,255,0.4)'
    },
    TabNavBtn: {
        alignItems: 'center',
        justifyContent: 'center',
        paddingHorizontal: '15@ms1',
        paddingVertical:'8@ms1',
    },
    TabNavBtnText: {
        color: 'rgba(255,255,255, 0.8)',
        fontSize:'12@ms1',
    },
    TabBtn: {
        paddingVertical: '10@ms',
        borderRadius:'4@ms1',
    },
    TabBtnText: {
        textAlign: 'center',
        fontSize: '12@ms1',
        color: 'rgba(255,255,255, 0.8)'
    },
    TabViewText: {
        fontSize: '12@ms1',
        color: 'rgba(255,255,255, 0.8)',
        lineHeight: '20@ms1'
    },
})
export default memo(forwardRef(VoiceHelpDialog))

```
## /Users/thunder/mycode/rn/components/VoiceSearch.tsx

```
import React, { createRef, forwardRef, memo, useEffect, useImperativeHandle, useRef, useState } from "react";
import { findNodeHandle, Image, NativeEventEmitter, NativeModules, Text, TouchableHighlight, View } from "react-native";
import LinearGradient from "react-native-linear-gradient";
import { Dialog, Icon } from "@rneui/themed";
import { FlashList } from "@shopify/flash-list";
import SongItem from "./SongItem.tsx";
import { request } from "../libs/util.ts";
import { focus } from "@wouterds/react-native-tv-focus";
import { setHasDialog, setVipStatus } from "../store/common.ts";
import { useAppDispatch, useAppSelector } from "../store";
import { company } from "../config.json";
import AsyncStorage from "@react-native-async-storage/async-storage";
import TouchFocusHighlight from "./TouchFocusHighlight.tsx";
import { moderateScale } from "react-native-size-matters";

function VoiceSearch(props: any, ref: any) {
    const [isVisible, setIsVisible] = useState(false);
    const [searchList, setSearchList] = useState<any[]>([]);
    const [total, setTotal] = useState(0);
    const searchDialogRef = useRef<any>(null);
    const prevRef = useRef<any>(null);
    const nextRef = useRef<any>(null);
    const dispatch = useAppDispatch();
    const ListItemRefs = useRef<any[]>([]);
    const page = useRef(1);
    const searchText = useRef('');
    const isVisibleRef = useRef(false);
    const onSearch = async ()=> {
        const token = await AsyncStorage.getItem('token');
        request(`${global.url}/kcloud/getmusics?token=${token}&page=${page.current}&size=5&word=${searchText.current}&language=&company=${company}`).then(res=> {
            setTotal(res.data.mediainfo.total);
            setSearchList(res.data.mediainfo.list);
        })
    }
    const onSelect = (index: number)=> {
        ListItemRefs.current[index-1]?.current?.order();
        setTimeout(()=>{
            setIsVisible(false)
        }, 1000)
    }
    const renderItem = ({ item, index }: { item: any; index: number }) => {
        return <RenderItem item={item} index={index} />
    }
    const prev =()=> {
        if(!isVisibleRef.current) {
           return
        }
        if(page.current === 1) {
           return;
        }
        page.current--;
        onSearch();
    }
    const next =()=> {
        if(!isVisibleRef.current) {
            return;
        }
        if(page.current === Math.ceil(total/5)) {
            return;
        }
        page.current++;
        onSearch();
    }
    const voiceEvent = (res: any)=> {
        switch(res.action) {
            case 'order_song':
                dispatch(setVipStatus(false));
                setIsVisible(true);
                searchText.current = res.m0 + res.m1;
                page.current = 1;
                onSearch();
                break;
            case "select_item":
                onSelect(Number(res.m0));
                break;
            case "prev_page":
                prev();
                break;
            case "next_page":
                next();
                break;
            case 'close_page':
                setIsVisible(false);
                break;
            default:
                break;
        }
    }
    useEffect(()=> {
        const nativeEventEmitter = new NativeEventEmitter(NativeModules.RnUtilsModule);
        const voiceListener = nativeEventEmitter.addListener("voiceEvent", voiceEvent);
        return ()=> {
            voiceListener.remove();
        }
    }, [])
    useEffect(()=>{
        if(isVisible) {
            focus(findNodeHandle(searchDialogRef.current));
        }
        isVisibleRef.current = isVisible;
        dispatch(setHasDialog(isVisible));
    }, [isVisible])
    class RenderItem extends React.Component<{
        item: any;
        index: number;
    }> {
        constructor(props:any) {
            super(props);
            ListItemRefs.current[props.index] = createRef();
        }
        render() {
            return <SongItem ref={ListItemRefs.current[this.props.index]} item={this.props.item} serial={true} index={this.props.index} />;
        }
    }
    useImperativeHandle(ref, () => ({
        isVisible
    }));
    return (
        <Dialog isVisible={isVisible} overlayStyle={{padding: 0,overflow: 'hidden',borderRadius: moderateScale(4,1), height: '80%', width: '70%'}} onBackdropPress={()=> setIsVisible(false)}>
            <LinearGradient
                style={{flex: 1, paddingHorizontal: moderateScale(10,1), paddingBottom: moderateScale(10,1)}}
                start={{ x : 0.0, y : 0 }} end={{ x : 1, y : 0 }}
                locations={[ 0.1, 0.7, 1 ]}
                colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
            >
                <View style={{height: moderateScale(35,1), backgroundColor: 'transparent', borderBottomWidth: 1, borderColor: 'rgba(255,255,255,0.2)', marginTop: moderateScale(5,1), marginBottom: moderateScale(5,1), borderRadius:moderateScale(3,1), flexDirection:'row', justifyContent: 'space-between'}}>
                    <Text style={{color: '#ffffff', fontSize: moderateScale(12,1), marginVertical: moderateScale(5,1)}}>搜索结果 ( {page.current} / {total} )</Text>
                    <View style={{flex:1, flexDirection:'row', justifyContent: 'flex-end',paddingRight: moderateScale(50,1)}}>
                        <TouchFocusHighlight
                            ref={prevRef}
                            noScale
                            noBorder
                            style={{
                                borderRadius:moderateScale(2,1),
                                padding:moderateScale(5,1),
                                alignItems: 'center',
                                justifyContent: 'center'}}
                            nextFocusLeft={findNodeHandle(prevRef.current)}
                            nextFocusUp={findNodeHandle(prevRef.current)}
                            nextFocusRight={findNodeHandle(nextRef.current)}
                            activeColor="#2089dc"
                            onPress={prev}>
                            <Text style={{fontSize: moderateScale(12,1), color:'#fff'}}>上一页</Text>
                        </TouchFocusHighlight>
                        <TouchFocusHighlight
                            ref={nextRef}
                            noBorder
                            noScale
                            style={{
                                marginLeft: moderateScale(10,1),
                                borderRadius:moderateScale(2,1),
                                padding:moderateScale(5,1),
                                alignItems: 'center',
                                justifyContent: 'center'}}
                            nextFocusUp={findNodeHandle(nextRef.current)}
                            nextFocusLeft={findNodeHandle(prevRef.current)}
                            nextFocusRight={findNodeHandle(searchDialogRef.current)}
                            activeColor="#2089dc"
                            onPress={next}>
                            <Text style={{fontSize: moderateScale(12,1), color:'#fff'}}>下一页</Text>
                        </TouchFocusHighlight>
                    </View>
                </View>
                <TouchableHighlight
                    ref={searchDialogRef}
                    style={{position: 'absolute', right: moderateScale(10,1), top: moderateScale(6,1),borderRadius:moderateScale(2,1), padding:moderateScale(5,1), alignItems: 'center', justifyContent: 'center'}}
                    nextFocusUp={findNodeHandle(searchDialogRef.current)}
                    nextFocusRight={findNodeHandle(searchDialogRef.current)}
                    nextFocusLeft={nextRef.current}
                    underlayColor="#2089dc"
                    onPress={()=> setIsVisible(false)}>
                    <Icon
                        size={moderateScale(18,1)}
                        name='close-outline'
                        type='ionicon'
                        color='#ffffff'
                    />
                </TouchableHighlight>
                {
                    searchList.length ? <FlashList data={searchList} renderItem={renderItem} estimatedItemSize={86} />: <View style={{flex: 1, justifyContent: 'center', alignItems: 'center'}}>
                        <Image resizeMode="stretch" style={{width:moderateScale(200), height: moderateScale(120,1), marginTop: -moderateScale(50,1)}} source={require('../assets/imgs/empty.png')}></Image>
                        <Text style={{color: '#ffffff', fontSize: moderateScale(12,1)}}>未查到相关歌曲，换个关键词试试</Text>
                    </View>
                }

            </LinearGradient>
        </Dialog>
    );
}

export default memo(forwardRef(VoiceSearch))

```
## /Users/thunder/mycode/rn/components/Volume.tsx

```
import React, { forwardRef, memo, useEffect, useImperativeHandle } from "react";
import { StyleSheet } from "react-native";
import { Icon, LinearProgress } from "@rneui/themed";
import useVolume from "../hooks/useVolume.ts";
import Animated, { useAnimatedStyle, useSharedValue, withTiming } from "react-native-reanimated";
import { RootSiblingPortal } from 'react-native-root-siblings';
import { moderateScale } from "react-native-size-matters";

export default memo(forwardRef(function Volume(props: any, ref: any) {
    const { volume, showVolume, increase, decrease, updateVolume } = useVolume();
    const transLateX = useSharedValue<number>(moderateScale(40));
    const animatedStyle = useAnimatedStyle(() => ({
        transform: [
            { translateX: transLateX.value },
            { translateY: -50 },
            { rotate: "-90deg" }
        ]
    }));
    useEffect(() => {
        if (showVolume) {
            transLateX.value = withTiming(0, { duration: 100 });
        } else {
            transLateX.value = withTiming(moderateScale(40), { duration: 100 });
        }
    }, [showVolume]);
    useImperativeHandle(ref, () => ({
        volume,
        increase,
        decrease,
        setVolume: updateVolume
    }));
    return <RootSiblingPortal>
        <Animated.View style={[styles.box, animatedStyle]}>
            <LinearProgress
                animation={{ duration: 100 }}
                style={{ height: moderateScale(5,1), width: moderateScale(60,1), borderRadius: moderateScale(5,1), marginLeft: moderateScale(3,1) }}
                value={volume}
                color="#2089dc"
                trackColor="rgba(0,0,0,0.5)"
            />
            <Icon
                style={{ transform: [{ rotate: "90deg" }] }}
                size={moderateScale(10,1)}
                name={volume <= 0 ? "volume-mute-outline" :
                    volume >= 1 ? "volume-high-outline" :
                        volume < 1 && volume > 0.6 ? "volume-medium-outline" :
                            "volume-low-outline"
                }
                type="ionicon"
                color="#fff"
            />
        </Animated.View>
    </RootSiblingPortal>;
}));
const styles = StyleSheet.create({
    box: {
        zIndex: 1000,
        flexDirection: "row-reverse",
        backgroundColor: "#bcbcbc",
        width: moderateScale(85,1),
        height: moderateScale(20),
        paddingHorizontal: moderateScale(5,1),
        justifyContent: "space-between",
        alignItems: "center",
        position: "absolute",
        right: -moderateScale(40),
        top: "50%"
    }
});

```
## /Users/thunder/mycode/rn/components/Xiaoai.tsx

```
import React, { forwardRef, memo, useEffect, useRef, useState } from "react";
import { Dimensions, Image, ImageBackground, NativeEventEmitter, NativeModules, StyleSheet, Text } from "react-native";
import { RootSiblingPortal } from "react-native-root-siblings";
import { useAppSelector } from "../store";
import { moderateScale } from "react-native-size-matters";

function Xiaoai() {
    const [xiaoaiSpeakShow, setXiaoaiSpeakShow] = useState("");
    const [asrStatus, setAsrStatus] = useState(false);
    const [isOverlayVisible,setIsOverlayVisible] = useState(false);
    const {netType} = useAppSelector(state=>state.common);
    const asrStatusTimer = useRef<any>();
    const xiaoaiSpeakShowTimer = useRef<any>();
    const doSpeakShow = (value:string)=> {
        setXiaoaiSpeakShow(value);
    }
    const onAsr = (value:string)=> {
        if(value === 'start') {
            setAsrStatus(true);
            hideAsr();
        } else {
            setAsrStatus(false);
            asrStatusTimer.current && clearTimeout(asrStatusTimer.current);
            hideXiaoai()
        }
    }
    const hideAsr = ()=> {
        asrStatusTimer.current && clearTimeout(asrStatusTimer.current);
        asrStatusTimer.current = setTimeout(()=> {
            setAsrStatus(false);
            clearTimeout(asrStatusTimer.current);
        }, 5000)
    }
    const hideXiaoai = ()=> {
        xiaoaiSpeakShowTimer.current && clearTimeout(xiaoaiSpeakShowTimer.current);
        xiaoaiSpeakShowTimer.current = setTimeout(()=> {
            setXiaoaiSpeakShow("");
            clearTimeout(xiaoaiSpeakShowTimer.current);
        }, 5000)
    }
    useEffect(()=> {
        NativeModules.RnXiaoAiModule.networkChange(netType !== 'none');
    }, [netType])
    useEffect(()=> {
        setIsOverlayVisible(!!xiaoaiSpeakShow);
        if(xiaoaiSpeakShow) {
            hideXiaoai();
        } else {
            xiaoaiSpeakShowTimer.current && clearTimeout(xiaoaiSpeakShowTimer.current);
        }
    }, [xiaoaiSpeakShow])
    useEffect(()=> {
        const xiaoAiEmitter = new NativeEventEmitter(NativeModules.RnXiaoAiModule);
        const xiaoAiSpeakListener = xiaoAiEmitter.addListener('doSpeakShow',doSpeakShow);
        const xiaoaiAsrListener = xiaoAiEmitter.addListener('onAsr',onAsr);
        return ()=>{
            xiaoAiSpeakListener.remove();
            xiaoaiAsrListener.remove();
        }
    }, [])
    return (
        <RootSiblingPortal>
            <ImageBackground resizeMode="stretch" style={{ ...styles.xiaoaiFrame, zIndex: 999, right: isOverlayVisible || asrStatus ? 0 : '-100%'}} source={require('../assets/imgs/xiaoaibg.png')}>
                <ImageBackground resizeMode="stretch" style={{minWidth: moderateScale(100,1), height: moderateScale(60,1),marginLeft: moderateScale(10,1), borderRadius: moderateScale(4,1), justifyContent: 'center', alignItems: 'center', paddingLeft: moderateScale(5,1), paddingRight: moderateScale(10,1)}} source={require('../assets/imgs/dialog.png')}>
                    <Text style={{fontSize: moderateScale(10,1), color: '#fff', width: '90%'}}>{ asrStatus ? '我在听...' : xiaoaiSpeakShow}</Text>
                </ImageBackground>
                <Image style={{width: moderateScale(53,1), height: moderateScale(60,1)}} resizeMode="stretch" source={require('../assets/imgs/ai.png')}/>
            </ImageBackground>
        </RootSiblingPortal>
    );

}
const styles = StyleSheet.create({
    xiaoaiFrame: {
        position: 'absolute',
        top: 0,
        right: 0,
        height: moderateScale(100,1),
        minWidth: moderateScale(150,1),
        maxWidth: Dimensions.get('window').width - moderateScale(55,1),
        paddingHorizontal: moderateScale(10,1),
        flexDirection: 'row',
        justifyContent: 'center',
        alignItems: 'center',
    }
})

export default memo(forwardRef(Xiaoai))

```
## /Users/thunder/mycode/rn/global.d.ts

```
declare var global: typeof MyGlobal;
declare global {
  namespace MyGlobal {
    var apiUrl: string;
  }
}

```
## /Users/thunder/mycode/rn/hooks/useCallBackState.ts

```
import {useEffect, useState, useRef} from "react";


function useCallbackState (state:any) {
  const cbRef = useRef<any>();
  const [data, setData] = useState(state);

  useEffect(() => {
    cbRef.current && cbRef?.current(data);
  }, [data]);

  return [data, function (val:any, callback:any) {
    cbRef.current = callback;
    setData(val);
  }];
}

export {useCallbackState};

```
## /Users/thunder/mycode/rn/hooks/useDownload.ts

```
import { useState } from "react";

function useDownload() {
    const [isDownload, setIsDownload] = useState(false)
    const [progress, setProgress] = useState({name: '', value: ''})

    return {isDownload, progress, setIsDownload, setProgress}
}
export default useDownload

```
## /Users/thunder/mycode/rn/hooks/usePlayer.ts

```
import { useCallback, useEffect, useState } from "react";
import { Dimensions, Keyboard, NativeModules, ViewStyle } from "react-native";
import { getRoute, navigationRef } from "../libs/RootNavigation.js";
import { moderateScale } from "react-native-size-matters";

function usePlayer(keyboardHeight: number) {
    const [isFullscreen, setIsFullscreen] = useState(false);
    const [routeName, setRouteName] = useState<string>('Home');
    const [videoStyle, setVideoStyle] = useState<ViewStyle>({});
    const fullscreenChange = useCallback((status: boolean) => {
        setIsFullscreen(status);
        if(status) {
            Keyboard.isVisible() && Keyboard.dismiss();
        }
        // 原生方法隐藏导航栏
        NativeModules.RnUtilsModule.hideNavigationBar(status);
    }, []);
    const routerListener = (e:any) => {
        setRouteName(getRoute()?.name as string)
    }
    const updateVideoStyle = useCallback(() => {
        if (routeName === "Home") {
            setVideoStyle({
                width: (Dimensions.get("window").width - moderateScale(20)*2 - moderateScale(5,1)*2) * 0.6,
                height: (Dimensions.get("window").height - (moderateScale(55,1)*2 + moderateScale(5,1))) * 0.75,
                left: (Dimensions.get("window").width - moderateScale(20)*2 - moderateScale(5,1)*2) * 0.2 + moderateScale(20) + moderateScale(5,1),
                top: moderateScale(55,1)
            });
        } else {
            setVideoStyle({
                width: (Dimensions.get("window").width - moderateScale(20)*2 - moderateScale(5,1)*2) * 0.5,
                height: (Dimensions.get("window").height - (moderateScale(55,1)*2 + moderateScale(5,1))) * 0.5,
                left:  moderateScale(20),
                top: keyboardHeight ? -keyboardHeight + 250 : moderateScale(55,1)
            });
        }

    }, [keyboardHeight, routeName]);

    useEffect(() => {
        updateVideoStyle();
    }, [keyboardHeight, routeName]);
    useEffect(()=> {
        if(navigationRef.isReady()) {
            navigationRef.addListener('state', routerListener);
        }
        return () => {
            navigationRef.removeListener('state' ,routerListener)
        }
    }, [])
    return {
        isFullscreen,
        fullscreenChange,
        routeName,
        videoStyle
    }}

export default usePlayer

```
## /Users/thunder/mycode/rn/hooks/useVolume.ts

```
import { useCallback, useEffect, useRef, useState } from "react";
import SystemSetting from "react-native-system-setting";
import { useCallbackState } from "./useCallBackState.ts";
function useVolume() {
    const [volume, setVolume] = useCallbackState(0);
    const [showVolume, setShowVolume] = useState(false);
    const timer = useRef<NodeJS.Timeout>();
    const volumeRef = useRef(volume);
    const increase = useCallback(() => {
        setVolume(volumeRef.current >= 1 ? 1 :volumeRef.current + 0.0625,(val:number)=> {
            volumeRef.current = val
            SystemSetting.setVolume(val)
        });
        setShowVolume(true)
    },[])
    const decrease = useCallback(() => {
        setVolume(volumeRef.current <= 0 ? 0 : volumeRef.current - 0.0625, (val:number)=> {
            volumeRef.current = val
            SystemSetting.setVolume(val)
        });
        setShowVolume(true)
    },[])
    const updateVolume = useCallback((value:number)=> {
        setVolume(value < 1 ? value : value / 100, (val:number)=> {
            volumeRef.current = val
            SystemSetting.setVolume(val)
        });
        setShowVolume(true)
    }, [volume])
    useEffect(()=> {
        SystemSetting.getVolume().then(volume=> {
            setVolume( Number(volume.toFixed(1)), (val:number)=> {
                volumeRef.current = val;
            })
        });
        const volumeListener = SystemSetting.addVolumeListener((data) => {
            setVolume(data.value);
            volumeRef.current = data.value;
            setShowVolume(true)
        });
        return ()=> {
            SystemSetting.removeVolumeListener(volumeListener);
        }
    },[])
    useEffect(()=> {
        if(showVolume) {
            if(timer.current) {
                clearInterval(timer.current)
            }
            timer.current = setTimeout(()=> {
                setShowVolume(false)
            }, 3000)
        }
        return ()=> {
            if(timer.current) {
                clearInterval(timer.current)
            }
        }
    },[volume, showVolume])


    return {volume, showVolume,updateVolume, increase, decrease}
}

export default useVolume

```
## /Users/thunder/mycode/rn/index.d.ts

```
declare module 'md5';
declare module 'lodash';
declare module "*.svg" {
  import React from "react";
  import { SvgProps } from "react-native-svg";
  const content: React.FC<SvgProps>;
  export default content;
}

interface SingerProps {
  onShowList: (name: string, id: number|string) => void;
  searchText?: string;
}
interface RankProps {
  activeCategory: any,
  type?: string,
  searchText?: string,
}
interface SongProps {
  searchText?: string
}
interface SongItemProps {
  item: any,
  hideBtn?: boolean,
  index: number,
  isOrder?: boolean,
  serial?: true,
  showDelBtn?: boolean,
  onDelPress?: () => void,
}
interface CardProps {
  title: string,
  type: string,
  source:  ImageSourcePropType,
  style?: ViewStyle,
  textStyle?: TextStyle,
  onHandlePress: (type: string, name: string) => void,
  nextFocusDown?: number | undefined | null;

  /**
   * Designates the next view to receive focus when the user navigates forward. See the Android documentation.
   *
   * @platform android
   */
  nextFocusForward?: number | undefined | null;

  /**
   * Designates the next view to receive focus when the user navigates left. See the Android documentation.
   *
   * @platform android
   */
  nextFocusLeft?: number | undefined | null;

  /**
   * Designates the next view to receive focus when the user navigates right. See the Android documentation.
   *
   * @platform android
   */
  nextFocusRight?: number | undefined | null;

  /**
   * Designates the next view to receive focus when the user navigates up. See the Android documentation.
   *
   * @platform android
   */
  nextFocusUp?: number | undefined | null;
}
interface OrientationMethods {
  [key: string]: () => void;
}

```
## /Users/thunder/mycode/rn/index.js

```
/**
 * @format
 */

import {AppRegistry} from 'react-native';
import App from './App';
import {name as appName} from './app.json';

global.apiUrl = 'https://mc.ktv.com.cn/karaoke_v3/api';
global.apiSdkUrl = 'https://mc.ktv.com.cn/karaoke_sdk';
global.url = 'https://mc.ktv.com.cn';

AppRegistry.registerComponent(appName, () => App);

```
## /Users/thunder/mycode/rn/jest.config.js

```
module.exports = {
  preset: 'react-native',
};

```
## /Users/thunder/mycode/rn/libs/AnalyticsUtil.js

```
/**
 * Created by wangfei on 17/8/30.
 */
var { NativeModules } = require('react-native');
module.exports = NativeModules.UMAnalyticsModule;
```
## /Users/thunder/mycode/rn/libs/EventContext.js

```
import React, { createContext, useContext, useEffect } from "react";
import { NativeEventEmitter, NativeModules } from "react-native";
import SystemSetting from "react-native-system-setting";
import NetInfo from "@react-native-community/netinfo";

const EventContext = createContext();

export const useEvent = () => {
  return useContext(EventContext);
};
class EventEmitter {
  constructor() {
    this.handlers = {};
  }

  on(event, handler) {
    this.handlers[event] = this.handlers[event] || [];
    this.handlers[event].push(handler);
  }

  emit(event, data) {
    if (this.handlers[event]) {
      this.handlers[event].forEach(handler => handler(data));
    }
  }
  off(event) {
      delete this.handlers[event];
  }
}
const eventEmitter = new EventEmitter();
export const EventProvider = ({ children }) => {

  const voiceEvent = (res) => {
    eventEmitter.emit('voiceEvent', res);
  }
  useEffect(() => {
    const nativeEventEmitter = new NativeEventEmitter(NativeModules.RnUtilsModule);
    const downloadNativeEventEmitter = new NativeEventEmitter(NativeModules.DownloadSongModule);
    const voiceListener=nativeEventEmitter.addListener('voiceEvent', voiceEvent);
    const keyboardListener=nativeEventEmitter.addListener('onKeyDown', (keyCode) => {
      eventEmitter.emit('onKeyDown', keyCode);
    })
    const sdCardListener=nativeEventEmitter.addListener('sdCardChange', (res) => {
      eventEmitter.emit('sdCardChange', res);
    })
    const volumeListener = SystemSetting.addVolumeListener((data) => {
      eventEmitter.emit('volumeChange', data);
    });
    const unsubscribe= NetInfo.addEventListener((state) => {
      eventEmitter.emit('networkChange', state);
    });
    const downloadListener=downloadNativeEventEmitter.addListener('downloadListener', (res) => {
      eventEmitter.emit('downloadListener', res);
    })
    return ()=> {
      voiceListener?.remove();
      keyboardListener?.remove();
      sdCardListener?.remove();
      // downloadListener?.remove();
      SystemSetting.removeVolumeListener(volumeListener);
      unsubscribe();
    }
  })
  return (
    <EventContext.Provider value={{ eventEmitter }}>
  {children}
  </EventContext.Provider>
);
};

```
## /Users/thunder/mycode/rn/libs/RootNavigation.js

```
import { createNavigationContainerRef } from '@react-navigation/native';

export const navigationRef = createNavigationContainerRef();

export function getRoute() {
    if (navigationRef.isReady()) {
       return  navigationRef.getCurrentRoute();
    }
    return null
}
export function navigate(name, params) {
    if (navigationRef.isReady()) {
        navigationRef.navigate(name, params);
    }
}
export function back() {
    if (navigationRef.isReady()) {
        navigationRef.canGoBack() && navigationRef.goBack();
    }
}

```
## /Users/thunder/mycode/rn/libs/components.ts

```
import { HostComponent, requireNativeComponent, ViewProps } from "react-native";
import type {
  DirectEventHandler
} from 'react-native/Libraries/Types/CodegenTypes';

interface HandInputDrawingPad extends ViewProps{
  onChange:(e:any)=>void
}
export type Source = {
  uri?: string;
  songId?: string;
  songName?: string;
  path?: string;
  resolution?: string;
  isDownload?: boolean;
  Music_ZTrack?: number;
};
interface RCTVideo extends ViewProps{
  paused?: boolean;
  source?: Source;
  selectedAudioTrack?: number;
  volume?: number;
  title:string;
  name:string;
  qrcodeUrl:string;
  onVideoLoad?: DirectEventHandler<{
    duration: number;
    currentTime: number;
    audioTracks: number;
  }>;
  onVideoPlaybackStateChanged?: DirectEventHandler<{
      isPlaying: boolean;
  }>;
  onVideoDownloadComplete?: DirectEventHandler<{
    filePath: string;
  }>;
  onVideoProgress?: DirectEventHandler<{
    currentTime: number;
    duration: number;
  }>;
  onVideoError?: DirectEventHandler<{
    what: number;
    extra: number;
  }>;
  onVolumeChange?: DirectEventHandler<{
    volume: number;
  }>;
  onAudioFocusChanged?: DirectEventHandler<{
    hasAudioFocus: boolean;
  }>;
  onVideoEnd?: DirectEventHandler<{}>;
  onAudioTracks?: DirectEventHandler<{
    audioTracks: number;
  }>;
  onDisplayChange?: DirectEventHandler<{
    dualScreen:boolean
  }>;
}
export const HandInputDrawingPad:HostComponent<HandInputDrawingPad> = requireNativeComponent('HandInputDrawingPad');
export const RCTVideo:HostComponent<RCTVideo> = requireNativeComponent('RCTVideo');

```
## /Users/thunder/mycode/rn/libs/tabData.ts

```
export default [
  {
    name: '点歌',
    value: 100,
    text:[
      "按歌手 + 歌名点歌：\n【点个/点首/来一首/我要唱/我想唱/帮我点】+【歌手名】的【歌曲名】\n例如：“我想唱周华健的朋友”",
      "按歌名点歌：\n【点个/点首/来一首/我要唱/我想唱/帮我点】+【歌名】\n例如：“来一首朋友”"
    ]

  },
  {
    name: '播放控制',
    value: 101,
    text:[
      "暂停播放\n“暂停、停止播放、暂停播放”",
      "继续播放\n“播放、继续播放、恢复播放”",
      "切下一首歌\n“下一首、切歌、下一曲、下首、下曲”",
      "重唱\n“重播、重唱、再唱一次”"
    ]
  },
  {
    name: '音乐音量加',
    value: 102,
    text:[
      "您可以通过这些命令来增加音量：\n“声音大一点、音量大一点、音乐大一点、音量调大点、声音调大点、音量调大一点、声音调大一点、大声一点、大声点、大点声、音量大一些、音乐大一些、音乐再大一些、音量再大一些、音乐再大一点”"
    ]
  },
  {
    name: '音乐音量减',
    value: 103,
    text:[
      "您可以通过这些命令来降低音量：\n“声音小一点、音量小一点、音乐小一点、音量调小点、声音调小点、小声一点、音量小点、音乐小点、小声点、小点声、音量调小一点、声音调小一点、音量小一些、音量再小一些、音乐小一些、音乐再小一些、音乐再小一点”"
    ]
  },
  {
    name: '设置任意音量',
    value: 104,
    text:[
      "设置音量为任意数值，您可以这么说:\n【设置音量为/音量调到】+【0~100的数字】\n例如:“设置音量为三十五”、“音量调到四十”"
    ]
  },
  {
    name: '静音',
    value: 105,
    text:[
      "如果要关闭声音，您可以这样说：\n“静音、安静”"
    ]
  },
  {
    name: '打开声音',
    value: 106,
    text:[
      "如果要恢复声音，您可以这样说：\n“还原声音、放声音、声音还原、放音”"
    ]
  },
  {
    name: '原伴唱',
    value: 107,
    text:[
      "视频切到原唱\n“原唱”",
      "视频切到伴唱\n“伴唱”"
    ]
  }
]

```
## /Users/thunder/mycode/rn/libs/util.ts

```
import MD5 from "md5";
import RNFS from "react-native-fs";
import { typeORMDriver } from "react-native-quick-sqlite";
import { DataSource, IsNull, ILike, Not, FindManyOptions, MoreThan } from "typeorm";
import { ListModel } from "../model/ListModel";
import { NativeModules, ToastAndroid } from "react-native";
import DeviceInfo from "react-native-device-info";

export const letters: (string)[] = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"];
export const figures: (string)[] = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0"];
let datasource: DataSource;
export const getHashPath = async (id: string, status?: boolean) => {
    let rootPath = RNFS.ExternalDirectoryPath + "/download/";
    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
    if (exPath.length) {
        const packageName = DeviceInfo.getBundleId();
        rootPath = exPath[0] + `/Android/data/${packageName}/files/download/`;
        try {
            if (!await RNFS.exists(rootPath)) {
                await RNFS.mkdir(rootPath);
            }
        } catch (e) {
            rootPath = RNFS.ExternalDirectoryPath + "/download/";
        }
    }
    const hash = MD5(id);
    const path = rootPath + hash.substring(0, 6) +
        "/" +
        hash.substring(6, 12) +
        "/" +
        hash.substring(12, 16) +
        "/";
    if (status) return path;
    return path + id + ".ts";
};
export const initSqlite = async () => {
    datasource = new DataSource({
        type: "react-native",
        database: "songmanagerdb",
        location: RNFS.ExternalDirectoryPath + "/sqlite/",
        driver: typeORMDriver,
        entities: [ListModel],
        synchronize: true
    });
    if (!datasource.isInitialized) await datasource.initialize();
};
export const isExist = async (id: number) => {
    const listRepository = datasource.getRepository(ListModel);
    return await listRepository.findOneBy({
        songid: id
    });
};

export async function updateList() {
    if (!datasource.isInitialized) await datasource.initialize();
    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
    const listRepository = datasource.getRepository(ListModel);
    const list = await listRepository.find();
    for (let i = 0; i < list.length; i++) {
        if (!await RNFS.exists(list[i].path as string)) {
            await listRepository.update(Number(list[i].id), { local: 0 });
        } else {
            await listRepository.update(Number(list[i].id), { local: exPath.length ? 1 : 2 });
        }
    }
}

export async function addSong(params: any) {
    if (!datasource.isInitialized) await datasource.initialize();
    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
    const listRepository = datasource.getRepository(ListModel);
    let listModel = await listRepository.findOneBy({
        songid: params.songid
    });
    if (listModel) {
        await listRepository.update(listModel.id as number, { local: exPath.length ? 1 : 2, path: params.path });
        return;
    }
    const initial = await NativeModules.RnUtilsModule.toPinyinInitials(params.music_name + params.singer);
    await listRepository.createQueryBuilder().insert().into(ListModel).values([
        {
            songid: params.songid,
            music_name: params.music_name,
            singer: params.singer,
            path: params.path,
            mp4: params.mp4,
            Music_ZTrack: params.Music_ZTrack,
            initial,
            isActive: params.isActive,
            local: params.local ? params.local : (exPath.length ? 1 : 2)
        }
    ]).execute();
}

export async function delSong(id: number) {
    if (!datasource.isInitialized) await datasource.initialize();
    const listRepository = datasource.getRepository(ListModel);
    const model = await listRepository.findOneBy({
        songid: id
    });
    await listRepository.remove(model as ListModel);
}

export async function getList(page: number, size: number, text?: string) {
    if (!datasource.isInitialized) await datasource.initialize();
    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
    const listRepository = datasource.getRepository(ListModel);
    const options: FindManyOptions = {
        order: {
            id: "ASC"
        },
        skip: (page - 1) * size,
        take: size
    };

    if (text) {
        options.where = [
            {
                id: Not(IsNull()),
                isActive: true,
                music_name: ILike(`%${text}%`),
                local: exPath.length ? MoreThan(0) : 2
            },
            {
                id: Not(IsNull()),
                isActive: true,
                singer: ILike(`%${text}%`),
                local: exPath.length ? MoreThan(0) : 2
            },
            {
                id: Not(IsNull()),
                isActive: true,
                initial: ILike(`%${text}%`),
                local: exPath.length ? MoreThan(0) : 2
            }
        ];
    } else {
        options.where = {
            id: Not(IsNull()),
            isActive: true,
            local: exPath.length ? MoreThan(0) : 2
        };
    }
    return await listRepository.find(options);
}

export async function request(input: RequestInfo, options?: RequestInit): Promise<any> {
    try {
        let response = await fetch(
            input, options
        );
        return await response.json();
    } catch (error) {
        ToastAndroid.show("当前无网络连接，连接网络后重试", ToastAndroid.SHORT);
        return {
            code: -1,
            msg:error
        }
    }
}

```
## /Users/thunder/mycode/rn/metro.config.js

```
const {getDefaultConfig, mergeConfig} = require('@react-native/metro-config');

const defaultConfig = getDefaultConfig(__dirname);
const { assetExts, sourceExts } = defaultConfig.resolver;

/**
 * Metro configuration
 * https://facebook.github.io/metro/docs/configuration
 *
 * @type {import('metro-config').MetroConfig}
 */
const config = {
  transformer: {
    babelTransformerPath: require.resolve("react-native-svg-transformer")
  },
  resolver: {
    assetExts: assetExts.filter((ext) => ext !== "svg"),
    sourceExts: [...sourceExts, "svg"]
  }
};

module.exports = mergeConfig(defaultConfig, config);

```
## /Users/thunder/mycode/rn/model/ListModel.ts

```
import 'reflect-metadata';
import {Entity, Column, PrimaryColumn} from 'typeorm/browser';
import {BaseEntity} from 'typeorm';
@Entity('List')
export class ListModel extends BaseEntity {
  @PrimaryColumn('int')
  id?: number;
  @Column('int')
  songid?: number;

  @Column('text')
  music_name?: string;

  @Column('text')
  path?: string;

  @Column({nullable: true, type: 'text'})
  singer?: string;

  @Column({nullable: true, type: 'text'})
  pinyin?: string;
  @Column({nullable: true, type: 'text'})
  initial?: string;
  @Column({nullable: true, type: 'text'})
  mp4?: string;
  @Column({nullable: true, type: 'text'})
  Music_ZTrack?: string;
  @Column("boolean")
  isActive?: boolean;
  @Column('int')
  local?: number;
}

```
## /Users/thunder/mycode/rn/native.d.ts

```
import { TouchableHighlight, TouchableHighlightProps } from "react-native";
declare module 'react-native' {
  export interface TouchableHighlightProps {
    nextFocusDown?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates forward. See the Android documentation.
     *
     * @platform android
     */
    nextFocusForward?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates left. See the Android documentation.
     *
     * @platform android
     */
    nextFocusLeft?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates right. See the Android documentation.
     *
     * @platform android
     */
    nextFocusRight?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates up. See the Android documentation.
     *
     * @platform android
     */
    nextFocusUp?: number | undefined | null;
    focusable?: boolean
  }
  export interface TouchableHighlightProps {
    nextFocusDown?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates forward. See the Android documentation.
     *
     * @platform android
     */
    nextFocusForward?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates left. See the Android documentation.
     *
     * @platform android
     */
    nextFocusLeft?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates right. See the Android documentation.
     *
     * @platform android
     */
    nextFocusRight?: number | undefined | null;

    /**
     * Designates the next view to receive focus when the user navigates up. See the Android documentation.
     *
     * @platform android
     */
    nextFocusUp?: number | undefined | null;
    focusable?: boolean
  }
}
declare module '@rneui/themed' {
  export interface TabItemProps extends TouchableHighlightProps {}
}

```
## /Users/thunder/mycode/rn/pages/Footer.tsx

```
import React, { forwardRef, memo,  useEffect, useImperativeHandle, useRef, useState } from "react";
import TouchFocusHighlight from "../components/TouchFocusHighlight.tsx";
import { findNodeHandle, NativeModules, Platform, StyleSheet, Text, ToastAndroid, View } from "react-native";
import {
    setActiveCode,
    setConfig,
    setIsActive, setNetType,
    setOrderList
} from "../store/common.ts";
import { Badge, Icon } from "@rneui/themed";
import Popover, { PopoverPlacement } from "react-native-popover-view";
import LinearGradient from "react-native-linear-gradient";
import DeviceInfo from "react-native-device-info";
import store, { useAppDispatch, useAppSelector } from "../store";
import { focus } from "@wouterds/react-native-tv-focus";
import RNFS from "react-native-fs";
import commonConfig from "../config.json";
import SplashScreen from "react-native-splash-screen";
import { isExist, request } from "../libs/util.ts";
import UnActiveDialog from "../components/UnActiveDialog.tsx";
import LicenseDialog from "../components/LicenseDialog.tsx";
import UpdateDialog from "../components/UpdateDialog.tsx";
import VipDialog from "../components/VipDialog.tsx";
import QrcodeDialog from "../components/QrcodeDialog.tsx";
import Xiaoai from "../components/Xiaoai.tsx";
import { RootSiblingPortal } from "react-native-root-siblings";
const packageName = DeviceInfo.getBundleId();
import NetInfo from "@react-native-community/netinfo";
import AsyncStorage from "@react-native-async-storage/async-storage";
import { getRoute, navigationRef } from "../libs/RootNavigation.js";
import { ScaledSheet,moderateScale,s,vs } from 'react-native-size-matters';
let licensePath: string = "";
// @ts-ignore
if (Platform.Version >= 29) {
    licensePath = `${RNFS.ExternalDirectoryPath}/license`;
} else {
    licensePath = `${RNFS.ExternalStorageDirectoryPath}/protect_s/${packageName}/license`;

}

function Footer(props: any, ref: any) {
    const [routeName, setRouteName] = useState<string>('Home');
    const [expireTime, setExpireTime] = useState<string>("");
    const [updateUrl, setUpdateUrl] = useState<string>("");
    const [settingStatus, setSettingStatus] = useState(false);
    const [license, setLicense] = useState<string>("");
    const dispatch = useAppDispatch();
    const {orderList} = useAppSelector((state) => state.common);
    const {playStatus, selectedAudioTrack, isPlaying} = useAppSelector((state) => state.control);
    const orderBtnRef = useRef<any>();
    const nextBtnRef = useRef<any>();
    const trackBtnRef = useRef<any>();
    const playBtnRef = useRef<any>();
    const resetBtnRef = useRef<any>();
    const volumePBtnRef = useRef<any>();
    const volumeSBtnRef = useRef<any>();
    const setBtnRef = useRef<any>();
    const backBtnRef = useRef<any>();
    const voiceBtnRef = useRef<any>();
    const checkUpdateRef = useRef<any>();
    const licenseDialogRef = useRef<any>();
    const updateDialogRef = useRef<any>();
    const macAddress = useRef('');
    const token = useRef('');
    const initLicense = async () => {
        macAddress.current = await NativeModules.RnUtilsModule.getMac();
        if (!await RNFS.exists(`${licensePath}/LICENSE_CODE`)) {
            if(commonConfig.isInputLicenseMode) {
                dispatch(setIsActive({
                    status: false,
                    errMsg: ""
                }));
                dispatch(setActiveCode(-99));
                licenseDialogRef.current?.show();
            } else {
                getLicense();
            }

            await RNFS.mkdir(licensePath);
            SplashScreen.hide();
        } else {
            const res = await RNFS.readFile(`${licensePath}/LICENSE_CODE`);
            if (res) {
                await verify(res);
            }
        }
    };
    const confirmLicense = async (license: string) => {
        if (store.getState().common.netType !== "none") {
            const res = await request(`${global.url}/karaoke_v3/mac_key/check?key=${license}&macid=${macAddress.current}&company=${commonConfig.company}&app_name=${commonConfig.platform}`);
            if (res.errcode === 100001) {
                licenseDialogRef.current?.focus();
                ToastAndroid.show(res.errmsg, ToastAndroid.SHORT);
            } else {
                verify(license);
                RNFS.writeFile(`${licensePath}/LICENSE_CODE`, license, "utf8");
            }
        } else {
            licenseDialogRef.current?.focus();
            ToastAndroid.show("连接网络后重试", ToastAndroid.SHORT);
        }
    };
    const checkUpdate = async (lic?: string) => {
        if(store.getState().common.netType !== 'none') {
            const vn = DeviceInfo.getVersion().slice(0, DeviceInfo.getVersion().indexOf("-"));
            const res = await request(`${global.apiSdkUrl}/vod_update?token=${token.current}&company=${commonConfig.company}&app_name=${commonConfig.platform}&vn=${vn}&license=${typeof lic === 'string' ? lic : license}`);
            if(res) {
                updateDialogRef?.current?.show();
                setUpdateUrl(res);
            } else {
                if(typeof lic !== 'string') {
                    ToastAndroid.show("当前已是最新版本", ToastAndroid.SHORT);
                }
            }
        } else {
            ToastAndroid.show("当前无网络连接，连接网络后重试", ToastAndroid.SHORT);
        }
    };
    const verify = async (lic?: string | boolean) => {
        if (typeof lic === "string") {
            setLicense(lic);
            NativeModules.RnUtilsModule.initPlayerSdk(lic);
        }
        if (store.getState().common.netType !== "none") {
            let url = `${global.apiSdkUrl}/${typeof lic === "string" ? "vod_token_by_macid" : "vod_status"}?${typeof lic === "string" ? "license=" + lic : "token=" + token.current}&macid=${macAddress.current}&company=${commonConfig.company}&app_name=${commonConfig.platform}`;
            if(!commonConfig.isInputLicenseMode) {
                url = `${global.apiSdkUrl}/${typeof lic === "string" ? "vod_token" : "vod_status"}?${typeof lic === "string" ? "license=" + lic : "token=" + token.current}&company=${commonConfig.company}&app_name=${commonConfig.platform}`
            }
            const result = await request(url);
            if(!result.code) {
                if (result.errcode === 100001) {
                    dispatch(setIsActive({
                        status: false,
                        errMsg: result.errmsg
                    }));
                    dispatch(setActiveCode(-99));
                } else {
                    if (licenseDialogRef.current?.isVisible) {
                        licenseDialogRef.current?.hide();
                    }
                    if (typeof lic === "string") {
                        await AsyncStorage.setItem("token", result.token);
                        token.current = result.token;
                        updateOrderList();
                        await getConfig();
                        if(result.hot_update) {
                            checkUpdate(lic);
                        }
                    }
                    dispatch(setIsActive({
                        status: true,
                        errMsg: ""
                    }));
                    dispatch(setActiveCode(result.status));
                    setExpireTime(result.expire_time);
                }

            }
        } else {
            dispatch(setActiveCode(2));
        }
        SplashScreen.hide();
        NativeModules.RnUtilsModule.initComplete();

    };
    const getConfig = async () => {
        if (store.getState().common.netType === "none") return;
        const config = await request(`${global.apiSdkUrl}/vod_conf?token=${token.current}&company=${commonConfig.company}&app_name=${commonConfig.platform}`);
        dispatch(setConfig(config));
    };
    const getOrderList = () => {
        if (store.getState().common.netType === "none") return;
        request(global.apiUrl + "/plist/" + token.current).then(async res => {
            dispatch(setOrderList(res));
            // if(isDownloadMode) {
            //     const arr: any = [];
            //     if (res.length) {
            //         for (let i = 0; i < res.length; i++) {
            //             let item = res[i];
            //             const exists = await isExist(res[res.length -1].songid);
            //             if(!exists || exists.local === 0) {
            //                 if(!arr.find((val: any) => val?.songid === item.songid)) {
            //                     arr.push(item);
            //                 }
            //             }
            //         }
            //         dispatch(setDownloadList(arr));
            //     }
            // }
            // @ts-ignore
            // res.length && dispatch(fetchGetCurrent(true));
        });

    };
    const updateOrderList = async () => {
        if (orderList.length) {
            await request(`${global.apiUrl}/plist/update?token=${token.current}`, {
                method: "POST",
                body: JSON.stringify({
                    "plist": orderList
                })
            });
        }
        getOrderList();
    };
    const getLicense = async () => {
        if(store.getState().common.netType !== 'none') {
            const res = await request(`${global.url}/karaoke_v3/lic?company=${commonConfig.company}&app_name=${commonConfig.platform}`);
            if(res.errcode === 100001) {
                dispatch(setIsActive({
                    status: false,
                    errMsg: res.errmsg
                }));
            } else {
                verify(res.lic);
                RNFS.writeFile(`${licensePath}/LICENSE_CODE`, res.lic, "utf8");

            }
        }
    }
    const routerListener = (e:any) => {
        setRouteName(getRoute()?.name as string)
    }
    useEffect(()=> {
        if(navigationRef.isReady()) {
            navigationRef.addListener('state', routerListener);
        }
        const unsubscribe= NetInfo.addEventListener((state) => {
            if (!store.getState().common.netType) {
                dispatch(setNetType(state.type));
            } else {
                if (store.getState().common.netType !== state.type) {
                    if (state.type !== "none") {
                        initLicense();
                    }
                    dispatch(setNetType(state.type));
                }
            }
        });
        return () => {
            unsubscribe();
            navigationRef.removeListener('state' ,routerListener)
        }
    }, [])
    useImperativeHandle(ref, () => ({
        initLicense,
        settingStatus,
    }))
    useEffect(()=> {
        if(settingStatus) {
            setTimeout(()=> {
                focus(findNodeHandle(checkUpdateRef.current));
            }, 500)
        }
    }, [settingStatus])
    return <View style={styles.Footer}>
        <TouchFocusHighlight
            ref={orderBtnRef}
            focusName="orderBtn"
            noBorder
            noScale
            nextFocusRight={findNodeHandle(nextBtnRef.current)}
            nextFocusLeft={findNodeHandle(voiceBtnRef.current)}
            nextFocusDown={findNodeHandle(orderBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('order')}>
            <>
                <Text style={styles.Icons}>{"\ue632"}</Text>
                <Text style={styles.ControlText}>已点</Text>
                <Badge
                    badgeStyle={{ width: moderateScale(10,1), height: moderateScale(10,1), borderRadius: moderateScale(10,1) }}
                    textStyle={{ fontSize: moderateScale(6,1) }}
                    status="error"
                    value={orderList.length}
                    containerStyle={{ position: "absolute", top: -5, right: -5 }}
                />
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={nextBtnRef}
            noBorder
            noScale
            focusName="nextBtn"
            nextFocusLeft={findNodeHandle(orderBtnRef.current)}
            nextFocusRight={findNodeHandle(trackBtnRef.current)}
            nextFocusDown={findNodeHandle(nextBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('next')}>
            <>
                <Text style={styles.Icons}>{"\ue645"}</Text>
                <Text style={styles.ControlText}>切歌</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={trackBtnRef}
            focusName="trackBtn"
            noBorder
            noScale
            nextFocusLeft={findNodeHandle(nextBtnRef.current)}
            nextFocusRight={findNodeHandle(playBtnRef.current)}
            nextFocusDown={findNodeHandle(trackBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('track')}>
            <>
                <Text style={styles.Icons}>{!selectedAudioTrack ? "\ue63a" : "\ue610"}</Text>
                <Text style={styles.ControlText}>{!selectedAudioTrack ? "原唱" : "伴唱"}</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={playBtnRef}
            noBorder
            noScale
            focusName="playBtn"
            nextFocusLeft={findNodeHandle(trackBtnRef.current)}
            nextFocusRight={findNodeHandle(resetBtnRef.current)}
            nextFocusDown={findNodeHandle(playBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('play')}>
            <>
                <Text style={styles.Icons}>{playStatus && isPlaying ? "\ue641" : "\ue646"}</Text>
                <Text style={styles.ControlText}>{playStatus && isPlaying ? "暂停" : "播放"}</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={resetBtnRef}
            noBorder
            noScale
            focusName="resetBtn"
            nextFocusLeft={findNodeHandle(playBtnRef.current)}
            nextFocusRight={findNodeHandle(volumePBtnRef.current)}
            nextFocusDown={findNodeHandle(resetBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('reset')}>
            <>
                <Text style={styles.Icons}>{"\ue637"}</Text>
                <Text style={styles.ControlText}>重唱</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={volumePBtnRef}
            noBorder
            noScale
            focusName="volumeP"
            nextFocusLeft={findNodeHandle(resetBtnRef.current)}
            nextFocusRight={findNodeHandle(volumeSBtnRef.current)}
            nextFocusDown={findNodeHandle(volumePBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('volumeP')}>
            <>
                <Text style={styles.Icons}>{"\ue626"}</Text>
                <Text style={styles.ControlText}>音量</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={volumeSBtnRef}
            noBorder
            noScale
            focusName="volumeS"
            nextFocusLeft={findNodeHandle(volumePBtnRef.current)}
            nextFocusRight={findNodeHandle(setBtnRef.current)}
            nextFocusDown={findNodeHandle(volumeSBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('volumeS')}>
            <>
                <Text style={styles.Icons}>{"\ue636"}</Text>
                <Text style={styles.ControlText}>音量</Text>
            </>
        </TouchFocusHighlight>

        <TouchFocusHighlight
            ref={setBtnRef}
            noBorder
            noScale
            focusName="setBtn"
            nextFocusLeft={findNodeHandle(volumeSBtnRef.current)}
            nextFocusRight={findNodeHandle(voiceBtnRef.current)}
            nextFocusDown={findNodeHandle(setBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={(event) => {
                setSettingStatus(!settingStatus);
            }}>
            <>
                <Icon
                    size={moderateScale(11,1)}
                    name="settings-outline"
                    type="ionicon"
                    color="#ffffff"
                />
                <Text style={styles.ControlText}>设置</Text>
            </>
        </TouchFocusHighlight>
        <Popover
            from={setBtnRef}
            popoverStyle={{ borderRadius: 8, backgroundColor: "#4551e3" }}
            placement={PopoverPlacement.TOP}
            backgroundStyle={{ backgroundColor: "transparent" }}
            offset={moderateScale(15,1)}
            isVisible={settingStatus}
            onRequestClose={() => setSettingStatus(false)}>
            <LinearGradient
                style={{ width: s(200), height: vs(130), padding: moderateScale(10,1), borderRadius: moderateScale(4,1) }}
                start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                locations={[0.1, 0.5, 1]}
                colors={[ '#416BD9',  '#8d7949','#416BD9' ]}
            >
                <View style={{ flexDirection: "column" }}>
                    <Text style={{
                        color: "#fff",
                        fontSize: moderateScale(11,1),
                    }}>License：{license}</Text>
                    <View>
                        <Text style={{
                            marginTop: moderateScale(5,1),
                            color: "#fff",
                            fontSize: moderateScale(11,1)
                        }}>版本号：{DeviceInfo.getVersion()}</Text>
                        <TouchFocusHighlight
                            ref={checkUpdateRef}
                            focusName="checkUpdate"
                            noBorder
                            noScale
                            nextFocusLeft={findNodeHandle(checkUpdateRef.current)}
                            nextFocusRight={findNodeHandle(checkUpdateRef.current)}
                            nextFocusUp={findNodeHandle(checkUpdateRef.current)}
                            nextFocusDown={findNodeHandle(checkUpdateRef.current)}
                            style={{ paddingHorizontal:moderateScale(5,1),paddingVertical: moderateScale(4,1), alignItems: "center", borderRadius: 4, justifyContent: "center", backgroundColor: "#3B3D63", marginTop: moderateScale(5,1) }}
                            activeColor="#2089dc"
                            onPress={() => checkUpdate()}>
                            <Text style={{fontSize: moderateScale(10,1), color: "#fff"}}>检查更新</Text>
                        </TouchFocusHighlight>
                    </View>
                </View>
            </LinearGradient>
        </Popover>
        <TouchFocusHighlight
            ref={voiceBtnRef}
            noBorder
            noScale
            focusName="voiceBtn"
            nextFocusLeft={findNodeHandle(setBtnRef.current)}
            nextFocusRight={findNodeHandle(backBtnRef.current)}
            nextFocusDown={findNodeHandle(voiceBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=> props.onChange('voiceHelp')}>
            <>
                <Icon
                    size={moderateScale(11,1)}
                    name="chatbox-ellipses-outline"
                    type="ionicon"
                    color="#ffffff"
                />
                <Text style={styles.ControlText}>语音助手</Text>
            </>
        </TouchFocusHighlight>
        <TouchFocusHighlight
            ref={backBtnRef}
            noBorder
            noScale
            focusName="backBtn"
            nextFocusLeft={findNodeHandle(voiceBtnRef.current)}
            nextFocusRight={findNodeHandle(orderBtnRef.current)}
            nextFocusDown={findNodeHandle(backBtnRef.current)}
            style={styles.ControlBtn}
            activeColor="#2089dc"
            onPress={()=>props.onChange('back')}>
            <>
                <Text style={styles.Icons}>{"\ue612"}</Text>
                <Text style={styles.ControlText}>{routeName === "List" ? "返回" : "退出"}</Text>
            </>
        </TouchFocusHighlight>
        <RootSiblingPortal>
            <>
                <UnActiveDialog onPress={() => licenseDialogRef.current.show(license)} />
                <LicenseDialog ref={licenseDialogRef} onConfirm={confirmLicense} />
                <UpdateDialog ref={updateDialogRef} url={updateUrl} />
                <VipDialog expireTime={expireTime} onVerify={verify} />
                <QrcodeDialog onVerify={verify} />
                <Xiaoai/>
            </>
        </RootSiblingPortal>
    </View>
}
const styles = ScaledSheet.create({
    Footer: {
        height: '50@ms1',
        flexDirection: "row",
        alignItems: "center",
        justifyContent: "center"
    },
    Icons: {
        fontSize: '13@ms1',
        color: "#fff",
        fontFamily: "iconfont",

    },
    ControlBtn: {
        flexDirection: "row",
        margin: '3@ms1',
        backgroundColor: "#3B3D63",
        alignItems: "center",
        padding: '10@ms0.2',
        paddingVertical: '4@ms1',
        borderRadius: '5@ms0.6',
        marginTop: -moderateScale(2.5,1)
    },
    ControlText: {
        fontSize: '11@ms1',
        color: "#fff"
    }
})
export default memo(forwardRef(Footer), (prevProps, nextProps) =>
    prevProps.license === nextProps.license)

```
## /Users/thunder/mycode/rn/pages/Header.tsx

```
import React, { memo, useCallback } from "react";
import { StyleSheet, Text, View } from "react-native";
import LinearGradient from "react-native-linear-gradient";
import { Badge } from "@rneui/themed";
import { useAppDispatch, useAppSelector } from "../store";
import { setVipStatus } from "../store/common.ts";
import TouchFocusHighlight from "../components/TouchFocusHighlight.tsx";
import { ScaledSheet, moderateScale } from "react-native-size-matters";
import Svg, { Path,G } from "react-native-svg";
const Logo = () => {
    return <Svg fill="none"  width={moderateScale(69, 1)}
         height={moderateScale(17, 1)} viewBox="0 0 138 34">
        <G>
            <G>
                <G>
                    <Path d="M41.28469921264649,16.489630325630607C33.01929921264649,9.627060325630605,22.494729212646483,10.068150325630604,14.055599212646484,17.099970325630604C22.300479212646486,23.665050325630606,32.97849921264648,23.547050325630607,41.28469921264649,16.489630325630607ZM27.560199212646484,12.837800325630605C29.625299212646482,12.781380325630606,31.342799212646483,14.412390325630605,31.398999212646483,16.484500325630606C31.455199212646484,18.556600325630605,29.829799212646485,20.279940325630605,27.764699212646484,20.336360325630608C25.699699212646486,20.392770325630607,23.982179212646486,18.761760325630604,23.925949212646486,16.689650325630605C23.869719212646487,14.617550325630605,25.495199212646483,12.894220325630606,27.560199212646484,12.837800325630605C27.560199212646484,12.837800325630605,27.560199212646484,12.837800325630605,27.560199212646484,12.837800325630605Z"
                          fill="#FFFFFF" fill-opacity="1"/>
                </G>
                <G>
                    <Path d="M23.1898,25.229473238228262C9.45004,21.84947323822826,5.18192,18.028373238228262,14.6485,11.637673238228261C24.621,5.4265232382282615,39.6131,3.5288032382282615,49.1052,4.251993238228262C36.3366,-2.2310267617717385,15.267,-0.9949467617717385,5.74419,5.985583238228261C0.883128,9.647673238228261,-1.49884,14.674073238228262,1.01092,20.22877323822826C4.80878,27.15287323822826,16.5551,27.440073238228262,23.1898,25.229473238228262Z"
                          fill="#FFFFFF" fill-opacity="1"/>
                </G>
                <G>
                    <Path d="M53.721049515533444,13.781635040749013C49.92324951553345,6.8575230407490135,38.176949515533444,6.570301040749014,31.54214951553345,8.780885040749013C45.28194951553345,12.160875040749014,49.550049515533445,15.981965040749014,40.08354951553345,22.372695040749015C30.11094951553345,28.583895040749013,15.118849515533448,30.481595040749013,5.626749515533447,29.758395040749015C18.395349515533447,36.23629504074901,39.465049515533444,35.00529504074902,48.982649515533446,28.019695040749014C53.843749515533446,24.357595040749015,56.225749515533444,19.331195040749016,53.715949515533445,13.781635040749013C53.715949515533445,13.781635040749013,53.721049515533444,13.781635040749013,53.721049515533444,13.781635040749013Z"
                          fill="#FFFFFF" fill-opacity="1"/>
                </G>
            </G>
            <G>
                <G>
                    <Path d="M97.24542879638672,5.000749999999886C97.24542879638672,5.000749999999886,97.24542879638672,13.576399999999886,97.24542879638672,13.576399999999886C97.24542879638672,13.576399999999886,93.12042879638672,13.576399999999886,93.12042879638672,13.576399999999886C93.12042879638672,13.576399999999886,93.12042879638672,8.421769999999887,93.12042879638672,8.421769999999887C93.12042879638672,8.421769999999887,82.85132879638672,8.421769999999887,82.85132879638672,8.421769999999887C82.85132879638672,8.421769999999887,82.85132879638672,17.935999999999886,82.85132879638672,17.935999999999886C82.85132879638672,17.935999999999886,78.46572879638671,17.935999999999886,78.46572879638671,17.935999999999886C78.46572879638671,17.935999999999886,78.46572879638671,8.426899999999886,78.46572879638671,8.426899999999886C78.46572879638671,8.426899999999886,68.26819879638671,8.426899999999886,68.26819879638671,8.426899999999886C68.26819879638671,8.426899999999886,68.26819879638671,13.581499999999886,68.26819879638671,13.581499999999886C68.26819879638671,13.581499999999886,64.33232879638672,13.581499999999886,64.33232879638672,13.581499999999886C64.33232879638672,13.581499999999886,64.33232879638672,5.000749999999886,64.33232879638672,5.000749999999886C64.33232879638672,5.000749999999886,78.46572879638671,5.000749999999886,78.46572879638671,5.000749999999886C78.46572879638671,5.000749999999886,78.46572879638671,3.4979599999998863,78.46572879638671,3.4979599999998863C78.46572879638671,3.4979599999998863,66.84719879638672,3.4979599999998863,66.84719879638672,3.4979599999998863C66.84719879638672,3.4979599999998863,66.84719879638672,-1.1368683772161603e-13,66.84719879638672,-1.1368683772161603e-13C66.84719879638672,-1.1368683772161603e-13,94.54652879638672,-1.1368683772161603e-13,94.54652879638672,-1.1368683772161603e-13C94.54652879638672,-1.1368683772161603e-13,94.54652879638672,3.4979599999998863,94.54652879638672,3.4979599999998863C94.54652879638672,3.4979599999998863,82.85132879638672,3.4979599999998863,82.85132879638672,3.4979599999998863C82.85132879638672,3.4979599999998863,82.85132879638672,5.000749999999886,82.85132879638672,5.000749999999886C82.85132879638672,5.000749999999886,97.24542879638672,5.000749999999886,97.24542879638672,5.000749999999886C97.24542879638672,5.000749999999886,97.24542879638672,5.000749999999886,97.24542879638672,5.000749999999886ZM67.67014879638671,18.618199999999888C67.67014879638671,18.618199999999888,93.98422879638672,18.618199999999888,93.98422879638672,18.618199999999888C93.98422879638672,18.618199999999888,93.98422879638672,33.697299999999885,93.98422879638672,33.697299999999885C93.98422879638672,33.697299999999885,89.48612879638672,33.697299999999885,89.48612879638672,33.697299999999885C89.48612879638672,33.697299999999885,89.48612879638672,32.83059999999988,89.48612879638672,32.83059999999988C89.48612879638672,32.83059999999988,71.94338879638671,32.83059999999988,71.94338879638671,32.83059999999988C71.94338879638671,32.83059999999988,71.94338879638671,33.994799999999884,71.94338879638671,33.994799999999884C71.94338879638671,33.994799999999884,67.67014879638671,33.994799999999884,67.67014879638671,33.994799999999884C67.67014879638671,33.994799999999884,67.67014879638671,18.612999999999886,67.67014879638671,18.612999999999886C67.67014879638671,18.612999999999886,67.67014879638671,18.618199999999888,67.67014879638671,18.618199999999888ZM68.68222879638672,14.104699999999886C68.68222879638672,14.104699999999886,77.30532879638672,14.104699999999886,77.30532879638672,14.104699999999886C77.30532879638672,14.104699999999886,77.30532879638672,17.002499999999888,77.30532879638672,17.002499999999888C77.30532879638672,17.002499999999888,68.68222879638672,17.002499999999888,68.68222879638672,17.002499999999888C68.68222879638672,17.002499999999888,68.68222879638672,14.104699999999886,68.68222879638672,14.104699999999886C68.68222879638672,14.104699999999886,68.68222879638672,14.104699999999886,68.68222879638672,14.104699999999886ZM77.26452879638671,9.852759999999886C77.26452879638671,9.852759999999886,77.26452879638671,12.750599999999887,77.26452879638671,12.750599999999887C77.26452879638671,12.750599999999887,69.50518879638672,12.750599999999887,69.50518879638672,12.750599999999887C69.50518879638672,12.750599999999887,69.50518879638672,9.852759999999886,69.50518879638672,9.852759999999886C69.50518879638672,9.852759999999886,77.26452879638671,9.852759999999886,77.26452879638671,9.852759999999886C77.26452879638671,9.852759999999886,77.26452879638671,9.852759999999886,77.26452879638671,9.852759999999886ZM71.94338879638671,22.003299999999886C71.94338879638671,22.003299999999886,71.94338879638671,24.070299999999886,71.94338879638671,24.070299999999886C71.94338879638671,24.070299999999886,78.46572879638671,24.070299999999886,78.46572879638671,24.070299999999886C78.46572879638671,24.070299999999886,78.46572879638671,22.003299999999886,78.46572879638671,22.003299999999886C78.46572879638671,22.003299999999886,71.94338879638671,22.003299999999886,71.94338879638671,22.003299999999886ZM78.46572879638671,29.450599999999888C78.46572879638671,29.450599999999888,78.46572879638671,27.342499999999887,78.46572879638671,27.342499999999887C78.46572879638671,27.342499999999887,71.94338879638671,27.342499999999887,71.94338879638671,27.342499999999887C71.94338879638671,27.342499999999887,71.94338879638671,29.450599999999888,71.94338879638671,29.450599999999888C71.94338879638671,29.450599999999888,78.46572879638671,29.450599999999888,78.46572879638671,29.450599999999888ZM89.48612879638672,22.003299999999886C89.48612879638672,22.003299999999886,82.85132879638672,22.003299999999886,82.85132879638672,22.003299999999886C82.85132879638672,22.003299999999886,82.85132879638672,24.070299999999886,82.85132879638672,24.070299999999886C82.85132879638672,24.070299999999886,89.48612879638672,24.070299999999886,89.48612879638672,24.070299999999886C89.48612879638672,24.070299999999886,89.48612879638672,22.003299999999886,89.48612879638672,22.003299999999886ZM89.48612879638672,29.450599999999888C89.48612879638672,29.450599999999888,89.48612879638672,27.342499999999887,89.48612879638672,27.342499999999887C89.48612879638672,27.342499999999887,82.85132879638672,27.342499999999887,82.85132879638672,27.342499999999887C82.85132879638672,27.342499999999887,82.85132879638672,29.450599999999888,82.85132879638672,29.450599999999888C82.85132879638672,29.450599999999888,89.48612879638672,29.450599999999888,89.48612879638672,29.450599999999888ZM91.84762879638672,9.857879999999886C91.84762879638672,9.857879999999886,91.84762879638672,12.755799999999887,91.84762879638672,12.755799999999887C91.84762879638672,12.755799999999887,84.01172879638672,12.755799999999887,84.01172879638672,12.755799999999887C84.01172879638672,12.755799999999887,84.01172879638672,9.857879999999886,84.01172879638672,9.857879999999886C84.01172879638672,9.857879999999886,91.84762879638672,9.857879999999886,91.84762879638672,9.857879999999886ZM84.01172879638672,14.109799999999886C84.01172879638672,14.109799999999886,92.74732879638671,14.109799999999886,92.74732879638671,14.109799999999886C92.74732879638671,14.109799999999886,92.74732879638671,17.007699999999886,92.74732879638671,17.007699999999886C92.74732879638671,17.007699999999886,84.01172879638672,17.007699999999886,84.01172879638672,17.007699999999886C84.01172879638672,17.007699999999886,84.01172879638672,14.109799999999886,84.01172879638672,14.109799999999886Z"
                          fill="#FFFFFF" fill-opacity="1"/>
                </G>
                <G>
                    <Path d="M120.04833435668945,5.8316841937636195C118.95953435668946,8.61671419376362,117.68683435668945,11.43762419376362,116.18913435668945,14.10472419376362C116.18913435668945,14.10472419376362,135.90423435668944,14.10472419376362,135.90423435668944,14.10472419376362C135.90423435668944,14.10472419376362,135.90423435668944,33.85122419376362,135.90423435668944,33.85122419376362C135.90423435668944,33.85122419376362,131.10453435668944,33.85122419376362,131.10453435668944,33.85122419376362C131.10453435668944,33.85122419376362,131.10453435668944,31.74322419376362,131.10453435668944,31.74322419376362C131.10453435668944,31.74322419376362,116.11243435668945,31.74322419376362,116.11243435668945,31.74322419376362C116.11243435668945,31.74322419376362,116.11243435668945,34.00002419376362,116.11243435668945,34.00002419376362C116.11243435668945,34.00002419376362,111.57853435668946,34.00002419376362,111.57853435668946,34.00002419376362C111.57853435668946,34.00002419376362,111.57853435668946,20.60822419376362,111.57853435668946,20.60822419376362C110.03996435668945,22.41362419376362,108.39406435668946,23.957424193763618,106.51813435668946,25.31152419376362C105.80763435668945,24.296024193763618,104.30484335668946,22.68032419376362,103.36943435668945,21.849424193763618C108.80298435668945,18.12582419376362,112.73885435668946,11.806924193763619,114.87543435668945,5.826554193763619C114.87543435668945,5.826554193763619,105.09201435668945,5.826554193763619,105.09201435668945,5.826554193763619C105.09201435668945,5.826554193763619,105.09201435668945,1.4310241937636192,105.09201435668945,1.4310241937636192C105.09201435668945,1.4310241937636192,138.00003435668947,1.4310241937636192,138.00003435668947,1.4310241937636192C138.00003435668947,1.4310241937636192,138.00003435668947,5.8316841937636195,138.00003435668947,5.8316841937636195C138.00003435668947,5.8316841937636195,120.04833435668945,5.8316841937636195,120.04833435668945,5.8316841937636195C120.04833435668945,5.8316841937636195,120.04833435668945,5.8316841937636195,120.04833435668945,5.8316841937636195ZM131.10453435668944,18.39252419376362C131.10453435668944,18.39252419376362,116.11243435668945,18.39252419376362,116.11243435668945,18.39252419376362C116.11243435668945,18.39252419376362,116.11243435668945,27.419524193763618,116.11243435668945,27.419524193763618C116.11243435668945,27.419524193763618,131.10453435668944,27.419524193763618,131.10453435668944,27.419524193763618C131.10453435668944,27.419524193763618,131.10453435668944,18.39252419376362,131.10453435668944,18.39252419376362Z"
                          fill="#FFFFFF" fill-opacity="1"/>
                </G>
            </G>
        </G>
    </Svg>
}
function Header() {
    const dispatch = useAppDispatch();
    const {videoNativeTag} = useAppSelector(state => state.control);
    const { current, orderList, vipStatus } = useAppSelector(state => state.common);
    const showVip = useCallback(() => {
        requestAnimationFrame(() => {
            dispatch(setVipStatus(true));
        });
    }, []);
    return <View style={styles.header}>
        <View style={{ flexDirection: "row", alignItems: "center", overflow: "hidden", flex: 1, marginBottom: -moderateScale(2.5,1) }}>
            <Logo />
            <View style={{ flex: 1 }}>
                {current && <Text style={{
                    color: "#fff",
                    fontSize: moderateScale(11, 1),
                    marginHorizontal: moderateScale(10, 1)
                }}>正在播放： {(current.singer || "") + "   " + current.music_name} 下一曲：{orderList.length > 1 ? (orderList[1].singer || "") + "  " + orderList[1].music_name : "未点歌"} </Text>}
            </View>
        </View>
        <TouchFocusHighlight
            activeOpacity={1}
            nextFocusLeft={videoNativeTag}
            focusName="vipBtn"
            onPress={showVip}
            style={styles.vipButton}>
            <LinearGradient start={{ x: 0, y: 0.5 }}
                            end={{ x: 1, y: 0.5 }}
                            locations={[0.1, 1]}
                            colors={["#D1B268", "#F9420A"]}
                            style={{
                                width: "100%",
                                height: "100%",
                                paddingHorizontal:moderateScale(10, 1),
                                borderRadius: moderateScale(15, 1),
                                alignItems: "center",
                                justifyContent: "center"
                            }}>
                <Text style={{ fontSize: moderateScale(11, 1), color: "#fff", fontWeight: "bold" }}>VIP
                    会员中心</Text>
                <Badge
                    status="error"
                    badgeStyle={{ width: moderateScale(6, 1), height: moderateScale(6, 1), borderRadius: moderateScale(6, 1) }}
                    containerStyle={{ position: "absolute", top: 0, right: 0 }}
                />
            </LinearGradient>
        </TouchFocusHighlight>
    </View>
}
const styles = ScaledSheet.create({
    header: {
        height: '50@ms1',
        flexDirection: "row",
        justifyContent: "space-between",
        alignItems: "center",
        paddingHorizontal: '20@ms',
    },
    vipButton: {
        height: '25@ms1',
        alignItems: "center",
        justifyContent: "center",
        borderRadius: '25@ms1',
        marginBottom: -moderateScale(2.5,1)
    },
})
export default memo(Header)

```
## /Users/thunder/mycode/rn/pages/Home.tsx

```
import React, { memo, useEffect, useRef, useState } from "react";
import { findNodeHandle, ImageBackground, StyleSheet, Text, View } from "react-native";
import AnalyticsUtil from "../libs/AnalyticsUtil";
import Card from "../components/Card";
import Carousel from "react-native-reanimated-carousel";
import { company, isDownloadMode, platform } from "../config.json";
import { request } from "../libs/util.ts";
import { ReduceMotion } from "react-native-reanimated";
import TouchFocusHighlight from "../components/TouchFocusHighlight.tsx";
import { moderateScale, ScaledSheet } from "react-native-size-matters";
import { LinearGradient } from "react-native-linear-gradient";
import { ListItem } from "@rneui/themed";
import { navigationRef } from "../libs/RootNavigation.js";
function Home(props: any) {
    // const [layout, setLayout] = useState({ width: 0, height: 0 });
    // const [swiperData, setSwiperData] = useState<any[]>([0]);
    // const [activeIndex, setActiveIndex] = useState(0);
    // const [isFocus, setIsFocus] = useState(false);
    const songCardRef = useRef<any>(null);
    const singerCardRef = useRef<any>(null);
    const rankCardRef = useRef<any>(null);
    const localCardRef = useRef<any>(null);
    const zongyiRef = useRef<any>(null);
    const qinggeRef = useRef<any>(null);
    // const bannerCardRef = useRef<any>([]);
    // const carouselRef = useRef<any>(null);
    const goList = (type: string, name: string, topicId?: number) => {
        requestAnimationFrame(() => {
            AnalyticsUtil.onEventWithMap(type + "_page", { page: name });
            // props.onChange("List", type, name, id);
            if(type === "categoryId") {
                props.navigation.navigate("List", { type, name, categoryId: topicId, home:true });
            } else {
                props.navigation.navigate("List", { type, name, topicId });
            }
        });
    };
    // const getBanner = () => {
    //     request(`${global.url}/kcloud/banner?company=${company}&app_name=${platform}`).then(res => {
    //         res.length && setSwiperData(res);
    //     });
    // };
    // const onFocus = (index: number) => {
    //     const currentIndex = carouselRef.current.getCurrentIndex();
    //     carouselRef.current.scrollTo({ count: index - currentIndex, animated: true });
    //     setIsFocus(true);
    // };
    // useEffect(() => {
    //     getBanner();
    // }, []);
    return <View style={styles.Wrapper}>
        <View style={styles.Left}>
            <Card ref={songCardRef} title="歌名" textStyle={{position: "absolute", bottom: moderateScale(10,1), width: "100%", textAlign: "center"}} nextFocusLeft={findNodeHandle(songCardRef.current)} type="song"
                  source={require("../assets/imgs/geming.png")} onHandlePress={goList} style={{flex: 0.75}} />
            <Card ref={singerCardRef} title="歌星" nextFocusLeft={findNodeHandle(singerCardRef.current)}
                  type="singer" source={require("../assets/imgs/geshou.png")} onHandlePress={goList} style={{flex: 0.25, marginTop: moderateScale(5,1)}} />
        </View>
        <View style={styles.Center}>
            <View style={styles.VideoPlayer} />
            <View style={styles.CenterList}>
                <Card ref={rankCardRef} title="排行榜" nextFocusLeft={findNodeHandle(singerCardRef.current)} type="rank"
                      source={require("../assets/imgs/rank.png")} onHandlePress={goList} />
                <Card title="分类" type="category" source={require("../assets/imgs/category.png")}
                      onHandlePress={goList} />
                {
                    isDownloadMode? <Card ref={localCardRef} title={company === 'dangbei' ? "历史":"本地"} type="local"
                                          source={require("../assets/imgs/new.png")} onHandlePress={goList} />:
                        <Card title="热歌榜" type="topic" source={require("../assets/imgs/collect.png")}
                              onHandlePress={() => goList("topic", "热歌榜", 400061)} />
                }
            </View>
        </View>
        <View style={styles.right}>
            <TouchFocusHighlight
                ref={zongyiRef}
                nextFocusRight={findNodeHandle(zongyiRef.current)}
                style={styles.rightItem}
                onPress={() => goList("categoryId", "综艺榜", 13)}>
                <LinearGradient
                    style={{flex:0.25, justifyContent: "center", alignItems: "center"}}
                    start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                    locations={[0, 1]}
                    colors={["#37d7e5", "#49bce5"]}
                >
                    <Text style={styles.rightItemText}>综</Text>
                    <Text style={styles.rightItemText}>艺</Text>
                    <Text style={styles.rightItemText}>榜</Text>
                </LinearGradient>
                <LinearGradient
                    style={{flex:0.75, flexDirection: "column", justifyContent: "center"}}
                    start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                    locations={[0, 1]}
                    colors={["#208afa", "#5093e0"]}
                >
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>1</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>他说(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>张碧晨</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>2</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>年轮(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>汪苏泷</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>3</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>星河叹(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>黄龄</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>

                </LinearGradient>
            </TouchFocusHighlight>
            <TouchFocusHighlight
                ref={qinggeRef}
                nextFocusRight={findNodeHandle(qinggeRef.current)}
                style={styles.rightItem}
                onPress={() => goList("categoryId", "情歌榜", 10)}>
                <LinearGradient
                    style={{flex:0.25,justifyContent: "center", alignItems: "center"}}
                    start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                    angle={45}
                    locations={[0, 1]}
                    colors={["#F63395", "#E98AB4"]}
                >
                    <Text style={styles.rightItemText}>情</Text>
                    <Text style={styles.rightItemText}>歌</Text>
                    <Text style={styles.rightItemText}>榜</Text>
                </LinearGradient>
                <LinearGradient
                    style={{flex:0.75,flexDirection: "column", justifyContent: "center"}}
                    start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                    angle={45}
                    locations={[0, 1]}
                    colors={["#D22A4E", "#e75775"]}
                >
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>1</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>偏爱(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>张芸京</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>2</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>选择(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>林子祥/叶倩文</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>
                    <ListItem containerStyle={styles.listItem}>
                        <Text style={styles.listItemNumber}>3</Text>
                        <ListItem.Content>
                            <ListItem.Title style={styles.listItemTitle}>小酒窝(HD)</ListItem.Title>
                            <ListItem.Subtitle style={styles.listItemSubTitle}>林俊杰/蔡卓妍</ListItem.Subtitle>
                        </ListItem.Content>
                    </ListItem>
                </LinearGradient>
            </TouchFocusHighlight>
        </View>
        {/*<View style={{ flex: 0.2 }}*/}
        {/*      onLayout={(e) => setLayout({ width: e.nativeEvent.layout.width, height: e.nativeEvent.layout.height })}>*/}
        {/*    {*/}
        {/*        layout.height > 0 && <Carousel*/}
        {/*            ref={carouselRef}*/}
        {/*            width={layout.width}*/}
        {/*            height={layout.height}*/}
        {/*            loop*/}
        {/*            enabled={swiperData.length > 1} // Default is true, just for demo*/}
        {/*            style={{ width: "100%" }}*/}
        {/*            autoPlay={swiperData.length > 1 && !isFocus}*/}
        {/*            autoPlayInterval={6000}*/}
        {/*            data={swiperData}*/}
        {/*            withAnimation={{ type: "timing", config: { reduceMotion: ReduceMotion.Never } }}*/}
        {/*            pagingEnabled={true}*/}
        {/*            onSnapToItem={setActiveIndex}*/}
        {/*            renderItem={({ item, index }) => <TouchFocusHighlight ref={ref => bannerCardRef.current[index] = ref}*/}
        {/*                                                                  noScale*/}
        {/*                                                                  onHandleFocus={() => onFocus(index)}*/}
        {/*                                                                  onHandleBlur={() => setIsFocus(false)}*/}
        {/*                                                                  style={{*/}
        {/*                                                                      flex: 1,*/}
        {/*                                                                      borderRadius: moderateScale(6,1),*/}
        {/*                                                                      overflow: "hidden"*/}
        {/*                                                                  }}*/}
        {/*                                                                  nextFocusLeft={index === 0 ? undefined : findNodeHandle(bannerCardRef.current?.[index - 1])}*/}
        {/*                                                                  nextFocusRight={index === swiperData.length - 1 ? findNodeHandle(bannerCardRef.current?.[index]) : findNodeHandle(bannerCardRef.current?.[index + 1])}*/}
        {/*                                                                  onPress={() => goList(item.is_category ? "banner" : "topic", item.name, item.topicId)}>*/}
        {/*                {item.img &&*/}
        {/*                    <ImageBackground source={{ uri: item.img }} resizeMode="stretch" style={styles.ListItemImage}>*/}
        {/*                    </ImageBackground>}*/}
        {/*            </TouchFocusHighlight>}*/}
        {/*        />*/}
        {/*    }*/}
        {/*    <Text style={styles.showText}> {(activeIndex + 1) + "/" + swiperData.length}</Text>*/}
        {/*</View>*/}
    </View>;
}

const styles = ScaledSheet.create({
    Wrapper: {
        flex: 1,
        flexDirection: "row",
        paddingHorizontal: '20@ms',
        paddingVertical: '5@ms'
    },
    Left: {
        flex: 0.2,
        flexDirection: "column"
    },
    right: {
        flex: 0.2,
        flexDirection: "column",
        gap: '5@ms1'
    },
    rightItem: {
        borderRadius: "6@ms1",
        flex: 1,
        overflow: "hidden",
        flexDirection: "row",
    },
    rightItemText: {
        fontSize: '14@ms1',
        color: "#fff",
        fontWeight: "bold",
    },
    LeftList: {
        flexDirection: "column",
        flex: 0.75,
        gap: '5@ms1'
    },
    CenterList: {
        flexDirection: "row",
        flex: 0.25,
        gap: '5@ms1',
        marginTop: '5@ms1'
    },
    Center: {
        flex: 0.6,
        flexDirection: "column",
        marginHorizontal: '5@ms1'
    },
    VideoPlayer: {
        flex: 0.75,
        backgroundColor: "#000",
        borderRadius: '6@ms1'
    },
    showText: {
        color: "#fff",
        fontSize: '13@ms1',
        textAlign: "center",
        position: "absolute",
        bottom: 2,
        left: 2,
        right: 2,
        paddingVertical: '3@ms1',
        borderBottomLeftRadius: '5@ms1',
        borderBottomRightRadius: '5@ms1',
        backgroundColor: "rgba(0,0,0,0.5)"
    },
    ListItemImage: {
        flex: 1,
        justifyContent: "center"
    },
    listItem: {
        backgroundColor: 'transparent',
        paddingVertical: '4@ms1',
        paddingLeft: '5@ms1',
        paddingRight:0
    },
    listItemNumber: {
        color: "#fff",
        fontSize: '15@ms1',
    },
    listItemTitle: {
        color: "#fff",
        fontSize: '10@ms1',
    },
    listItemSubTitle: {
        color: "rgba(255,255,255,0.8)",
        fontSize: '7@ms1',
    }
});
export default memo(Home);

```
## /Users/thunder/mycode/rn/pages/List.tsx

```
import React, { forwardRef, memo, useCallback, useEffect, useImperativeHandle, useMemo, useRef, useState } from "react";
import {
    StyleSheet,
    Text,
    View,
    NativeModules
} from "react-native";
import { Icon } from "@rneui/themed";
import Singer from "../components/Singer";
import Rank from "../components/Rank";
import Song from "../components/Song";
import Local from "../components/Local";
import {  request } from "../libs/util";
import DocumentPicker from "react-native-document-picker";
import { addSong } from "../libs/util";
import RNFS from "react-native-fs";
import AnalyticsUtil from "../libs/AnalyticsUtil";
import Search from "../components/Search.tsx";
import Category from "../components/Category.tsx";
import TouchFocusHighlight from "../components/TouchFocusHighlight.tsx";
import {isDownloadMode} from "../config.json";
import {debounce} from "lodash";
import CategoryList from "../components/CategoryList.tsx";
import { moderateScale, ScaledSheet } from "react-native-size-matters";
// @ts-ignore
const topsNav = [
    require(`../assets/imgs/top_1.png`),
    require(`../assets/imgs/top_2.png`),
    require(`../assets/imgs/top_3.png`),
    require(`../assets/imgs/top_4.png`),
    require(`../assets/imgs/top_5.png`),
    require(`../assets/imgs/top_6.png`),
    require(`../assets/imgs/top_7.png`),
    require(`../assets/imgs/top_8.png`)
];

export interface ListMethods {
    goBack: () => void;
    blur: () => void;
}

function List({route, navigation, keyboardHeight,onChange}: any, ref: any) {
    const [searchText, setSearchText] = useState("");
    const [activeCategory, setActiveCategory] = useState<any>(null);
    const [category, setCategory] = useState<any>([]);
    const localRef = useRef<any>();
    const searchRef = useRef<any>();
    const getCategory = () => {
        let url = global.url;
        if (route.params.type === "category") {
            url += "/vodc/song/topics";
        } else if (route.params.type === "rank") {
            url += "/apollo/module/modulelist?id=2";
        } else if (route.params.type === "banner") {
            url += `/vodc/topic/songlist?topicId=${route.params.topicId}`;
        } else {
            return;
        }
        request(url).then(res => {
            if (route.params.type === "rank") {
                res.data.list.forEach((item: any, index: number) => {
                    item.bgImg = topsNav[index];
                });
            }
            const list = route.params.type === "rank" ? res.data.list : res.data;
            setCategory(list);
            !activeCategory && setActiveCategory(list[0]);
        });
    };

    const goBack = () => {
        if(route?.params?.categoryId && !route?.params?.home){
            navigation.navigate("List", { type: "category", name:"分类" });
        } else if(route.params?.singerId){
            searchRef.current?.updateSearch("del");
            navigation.navigate('List', { type: 'singer', name: '歌星'})
        } else {
            navigation.goBack();
        }
    };
    const onShowList = useCallback((name: string, id: string | number) => {
        searchRef.current?.updateSearch("del");
        setTimeout(() => {
            navigation.navigate('List', { type: "song", name:`歌星 & ${name}`, singerId: id });
        })
    }, []);
    const selectFile = async () => {
        const list: any = await DocumentPicker.pickDirectory();
        if (list.length) {
            await addSongs(list);
            localRef.current?.reset();
        }

    };
    const addSongs = async (list: any) => {
        for (let i = 0; i < list.length; i++) {
            const item = list[i];
            if (item.type.search("video") > -1) {
                const param = item.name.substring(0, item.name.lastIndexOf(".")).split("_");
                let path;
                if (item.uri.split(":")[0] === "primary") {
                    path = RNFS.ExternalStorageDirectoryPath + "/" + item.uri.split(":")[1];
                } else {
                    const exPath = await NativeModules.RnUtilsModule.getSDCardPath();
                    if (exPath.length === 1) {
                        path = exPath[0] + "/" + item.uri.split(":")[1];
                    } else {
                        if (item.uri.split(":")[0].search("0000") === 0) {
                            path = exPath[1] + "/" + item.uri.split(":")[1];
                        } else {
                            path = exPath[0] + "/" + item.uri.split(":")[1];
                        }
                    }

                }
                if (param.length >= 3) {
                    await addSong({
                        songid: param[0],
                        music_name: param[1],
                        singer: param[2],
                        path,
                        Music_ZTrack: 1,
                        isActive: true,
                        mp4: "",
                        local: param[3] || 3
                    });
                }
            }
        }
    };
    const RenderedComponent  = useMemo(() => {
        switch (route.params.type) {
            case "singer":
                return <Singer searchText={searchText} onShowList={onShowList} />
            case "song":
                return <Song searchText={searchText} />;
            case "categoryId":
                return <Song searchText={searchText} />;
            case "local":
                return isDownloadMode ? <Local ref={localRef} searchText={searchText} /> : <Rank searchText={searchText} activeCategory={{ moduleName: '热歌榜', moduleId: 400061 }} />
            case 'topic':
                return <Rank searchText={searchText} activeCategory={{ moduleName: route.params.name, moduleId: route.params.topicId }} />
            case 'category':
                return activeCategory?.name && <CategoryList topicId={activeCategory?.id} name={activeCategory?.name} />
            default:
                return <Rank activeCategory={activeCategory} type={route.params.type} />
        }
    },[searchText,route.params?.singerId,activeCategory,route.params.type]);
    useImperativeHandle(ref, (): ListMethods => {
        return {
            goBack,
            blur: () => {
                searchRef.current?.blur();
            }
        };
    });
    useEffect(() => {
        AnalyticsUtil.onPageStart(route.params.name);
        getCategory();
        return () => {
            AnalyticsUtil.onPageEnd(route.params.name);
        };
    }, [route.params.type]);
    return <View style={styles.container}>
        <View style={styles.player}>
            <View style={styles.videoPlayer} />
            <View style={{flex:0.5, marginTop: moderateScale(5,1)}}>
                {route.params.type === "rank" || route.params.type === "category" || route.params.type === "banner" ?
                    <Category category={category} activeCategory={activeCategory} onChange={debounce((category:any) => setActiveCategory(category), 300)} /> : <Search ref={searchRef} onSearch={debounce((text:string) => setSearchText(text), 300)} />
                }
            </View>
        </View>
        <View style={[styles.list, {top: -keyboardHeight/2}]}>
            <View style={styles.listTitle}>
                <TouchFocusHighlight
                    focusName="list-backBtn"
                    noBorder
                    noScale
                    style={{
                        flexDirection: "row",
                        alignItems: "center",
                        borderRadius: moderateScale(2,1),
                        padding: moderateScale(4,1),
                    }}
                    activeColor="#2089dc"
                    onPress={goBack}>
                    <>
                        <Icon
                            size={moderateScale(20)}
                            name="chevron-back-outline"
                            type="ionicon"
                            color="#ffffff"
                        />
                        <Text style={styles.titleText}>{route.params.name}</Text>
                        {(route.params.type === "rank" || route.params.type === "category" || route.params.type === "banner") && <Text
                            style={styles.titleText}>& {activeCategory?.name || activeCategory?.moduleName}</Text>}
                    </>
                </TouchFocusHighlight>
                {/*{ props.type === 'local' && <Button onPress={selectFile}>导入本地文件</Button> }*/}
            </View>
            <View style={keyboardHeight ? {minHeight: keyboardHeight/2 + moderateScale(90,1)}: {flex:1}}>
                {RenderedComponent}
            </View>
        </View>
    </View>;
}

const styles = ScaledSheet.create({
    container: {
        flex: 1,
        flexDirection: "row",
        paddingHorizontal: '20@ms',
        paddingVertical: '5@ms1',
    },
    player: {
        flex: 0.5,
        flexDirection: "column"
    },
    videoPlayer: {
        flex: 0.5,
        backgroundColor: "#000",
        borderRadius: '6@ms1'
    },
    selectButton: {
        flexDirection: "column",
        marginRight: '5@ms1',
        paddingTop: '20@ms',
        flex: 0.1
    },
    list: {
        flex: 0.5,
        marginLeft: '10@ms1'
    },
    listTitle: {
        padding: '5@ms1',
        borderBottomWidth: 1,
        borderStyle: "solid",
        borderColor: "rgba(255,255,255,0.4)",
        flexDirection: "row",
        alignItems: "center",
        justifyContent: "space-between",
        marginBottom: '5@ms1'
    },
    titleText: {
        fontSize: '13@ms1',
        color: "white",
        marginLeft: '3@ms1'
    }
});
export default memo(forwardRef(List));

```
## /Users/thunder/mycode/rn/pages/Main.tsx

```
import React, { useEffect, useRef, useState, useCallback, memo } from "react";
import Home from "./Home";
import List, { ListMethods } from "./List";
import {
    BackHandler, Platform, NativeModules,
    StyleSheet,
    Keyboard, KeyboardAvoidingView, NativeEventEmitter, ToastAndroid
} from "react-native";
import RNExitApp from "react-native-exit-app";
import LinearGradient from "react-native-linear-gradient";
import { requestMultiple } from "react-native-permissions";
import RNFS from "react-native-fs";
import VideoPlayer, { VideoPlayerMethods } from "../components/VideoPlayer";
import {
    initSqlite,updateList
} from "../libs/util";
import DeviceInfo from "react-native-device-info";
import store from "../store";
import commonConfig from "../config.json";
import VoiceSearch from "../components/VoiceSearch.tsx";
import OrderedDialog from "../components/OrderedDialog.tsx";
import VoiceHelpDialog from "../components/VoiceHelpDialog.tsx";
import ExitDialog from "../components/ExitDialog.tsx";
import Footer from "./Footer.tsx";
import Header from "./Header.tsx";
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import { navigationRef, getRoute } from '../libs/RootNavigation';
import {debounce} from 'lodash'
const Stack = createNativeStackNavigator();
const { isFullScreenMode, isDownloadMode } = commonConfig;
const packageName = DeviceInfo.getBundleId();
let licensePath: string = "";
// @ts-ignore
if (Platform.Version >= 29) {
    licensePath = `${RNFS.ExternalDirectoryPath}/license`;
} else {
    licensePath = `${RNFS.ExternalStorageDirectoryPath}/protect_s/${packageName}/license`;

}

function Main(props: any) {
    const [keyboardHeight, setKeyboardHeight] = useState(0);
    const listRef = useRef<ListMethods>();
    const videoPlayer = useRef<VideoPlayerMethods>();

    const orderDialogRef = useRef<any>();
    const exitDialogRef = useRef<any>();
    const voiceHelpDialogRef = useRef<any>();
    const voiceSearchRef = useRef<any>();
    const footerRef = useRef<any>();
    let lastBackPressed = Date.now();
    const backAction = useCallback(() => {
        if (isFullScreenMode) {
            if (lastBackPressed && lastBackPressed + 2000 >= Date.now()) {
                RNExitApp.exitApp();
            }
            lastBackPressed = Date.now();
            ToastAndroid.show("再按一次退出应用", ToastAndroid.SHORT);
            return true;
        } else {
            const route = getRoute();
            if (videoPlayer?.current?.isFullscreen) {
                videoPlayer.current?.exit();
                return true;
            }
            if (route?.name === "List") {
                listRef.current?.goBack();
            } else {
                exitDialogRef.current?.show();
            }
        }

        return true;
    }, [footerRef.current?.settingStatus, videoPlayer?.current?.isFullscreen]);
    const requestPermission = async () => {
        try {

            const PermissionsAndroid = await requestMultiple([
                // @ts-ignore
                "android.permission.ACCESS_WIFI_STATE",
                // @ts-ignore
                "android.permission.ACCESS_NETWORK_STATE",
                "android.permission.READ_EXTERNAL_STORAGE",
                "android.permission.READ_MEDIA_IMAGES",
                "android.permission.READ_MEDIA_AUDIO",
                "android.permission.READ_MEDIA_VIDEO",
                // @ts-ignore
                "android.permission.INTERNET",
                "android.permission.WRITE_EXTERNAL_STORAGE",
                // "android.permission.READ_PHONE_STATE",
                // @ts-ignore
                "android.permission.MANAGE_EXTERNAL_STORAGE",
                'android.permission.RECORD_AUDIO'
            ]);
            if(PermissionsAndroid['android.permission.RECORD_AUDIO'] === 'granted') {
                NativeModules.RnXiaoAiModule.initMiAi(commonConfig.company);
            }
            await init();
            // console.log('Permission status:', status);
        } catch (error) {
            console.error("Error requesting permission:", error);
        }
    };
    const init = async () => {
        await initSqlite();
        await NativeModules.RnUtilsModule.moveFile("handwrite", "PC_HSDic.dat");
        await footerRef.current?.initLicense();
    };
    // 无操作时播放页面到全屏
    const startActivityTimer = () => {
        videoPlayer.current?.startActivityTimer();
    };

    // 检查版本更新
    const handleChange = (type: string) => {
        requestAnimationFrame(() => {
            switch (type) {
                case "order":
                    orderDialogRef.current?.show();
                    break;
                case "next":
                    videoPlayer.current?.onNext();
                    break;
                case 'track':
                    videoPlayer.current?.switchAudioTrack();
                    break;
                case 'play':
                    if (!store.getState().control.isPlaying) {
                        videoPlayer.current?.togglePlay(true);
                    } else {
                        videoPlayer.current?.togglePlay(!store.getState().control.playStatus);
                    }
                    break;
                case 'reset':
                    videoPlayer.current?.toggleRest();
                    break;
                case 'volumeP':
                    videoPlayer.current?.toggleVolume(true);
                    break;
                case 'volumeS':
                    videoPlayer.current?.toggleVolume(false);
                    break;
                case 'back':
                    backAction();
                    break;
                case 'voiceHelp':
                    voiceHelpDialogRef.current?.show();
                    break;
            }
        });

    }
    useEffect(() => {
        // 调用该函数以请求权限
        requestPermission();
        const nativeEventEmitter = new NativeEventEmitter(NativeModules.RnUtilsModule);
        const sdCardListener = nativeEventEmitter.addListener("sdCardChange", (res: any) => {
            updateList();
        });
        const keyboardDidShowListener = Keyboard.addListener("keyboardDidShow", (event) => {
            setKeyboardHeight(event.endCoordinates.height);
        });
        const keyboardDidHideListener = Keyboard.addListener("keyboardDidHide", () => {
            setKeyboardHeight(0);
            listRef.current?.blur();
        });
        return () => {
            keyboardDidShowListener.remove();
            keyboardDidHideListener.remove();
            sdCardListener.remove();
        };
    }, []);
    useEffect(() => {
        const backHandle = BackHandler.addEventListener("hardwareBackPress", backAction);
        return () => {
            backHandle.remove();
        };
    }, [backAction]);
    return <>
            {
                !isFullScreenMode ?
                    <>
                        <LinearGradient
                            onTouchEnd={debounce(startActivityTimer, 300)}
                            style={styles.Container}
                            start={{ x: 0, y: 0 }} end={{ x: 1, y: 1 }}
                            locations={[0, 0.5, 1]}
                            colors={["#1a3148", "#483122", "#1a3148"]}
                        >
                            <Header />
                            <KeyboardAvoidingView style={{flex:1}} behavior="height">
                                <NavigationContainer ref={navigationRef}>
                                    <Stack.Navigator screenOptions={{
                                        animation: "fade",
                                    }} initialRouteName="Home">
                                        <Stack.Screen options={{headerShown: false, contentStyle: {backgroundColor: "transparent"}}} name="Home" component={Home} />
                                        <Stack.Screen options={{headerShown: false,contentStyle: {backgroundColor: "transparent"}}} name="List" children={(props: any) => (<List {...props} keyboardHeight={keyboardHeight} ref={listRef} />)} />
                                    </Stack.Navigator>
                                </NavigationContainer>
                            </ KeyboardAvoidingView>
                            <Footer ref={footerRef} onChange={handleChange} />
                        </LinearGradient>
                    </>
                    : ""
            }
        <VideoPlayer
            ref={videoPlayer}
            // routeName={route?.path}
            keyboardHeight={keyboardHeight}
            onShowOrder={()=>handleChange('order')}
            onBack={backAction} />
        <OrderedDialog ref={orderDialogRef} />
        <ExitDialog ref={exitDialogRef} />
        <VoiceHelpDialog ref={voiceHelpDialogRef} />
        <VoiceSearch ref={voiceSearchRef} />
    </>;
}

const styles = StyleSheet.create({
    Container: {
        flex: 1,
        flexDirection: "column"
    },



});
export default memo(Main);

```
## /Users/thunder/mycode/rn/store/common.ts

```
import { createAsyncThunk, createSlice } from "@reduxjs/toolkit";
import { request, isExist } from "../libs/util";


export const fetchGetCurrent = createAsyncThunk("common/fetchGetCurrent", async (status: boolean, {
    getState,
    dispatch
}) => {
    const state: any = getState();
    const orderList = state.common.orderList;
    if (orderList.length) {
        const item = orderList[0];
        const exists = await isExist(item.songid);
        if (exists && exists.local !== 0) {
            dispatch(setCurrent({
                ...exists
            }));
        } else {
            dispatch(setCurrent({
                ...item
            }));
        }

    } else {
        dispatch(setCurrent(null));
    }
});

export interface CommonState {
    current: any;
    orderList: any[];
    downloadList: any[];
    netType: string;
    activeCode: number;
    qrcodeStatus: boolean;
    dialogTitle: string;
    isActive: boolean;
    errMsg: string;
    vipStatus: boolean;
    config: any;
    hasDialog: boolean;
}

export const controlSlice = createSlice({
    name: "common",
    initialState: <CommonState>{
        current: null,
        orderList: [],
        downloadList: [],
        netType: "",
        activeCode: -99,
        qrcodeStatus: false,
        dialogTitle: "",
        isActive: true,
        errMsg: "当前设备无license文件",
        vipStatus: false,
        config: {},
        hasDialog: false
    },
    reducers: {

        setOrderList: (state, { payload }) => {
            state.orderList = payload;
        },
        setCurrent: (state, { payload }) => {
            state.current = payload;
        },
        setDownloadList: (state, { payload }) => {
            state.downloadList = payload;
        },
        updateDownloadList: (state, { payload }) => {
            if (payload) {
                state.downloadList.splice(state.downloadList.findIndex((item: any) => item.songid === payload.songid), 1);
            } else {
                state.downloadList.shift();
            }
        },
        setNetType: (state, { payload }) => {
            state.netType = payload;
        },
        setActiveCode(state, { payload }) {
            state.activeCode = payload;
        },
        setQrcodeStatus(state, { payload }) {
            state.qrcodeStatus = payload;
            state.hasDialog = payload;
        },
        setDialogTitle(state, { payload }) {
            state.dialogTitle = payload;
        },
        setIsActive(state, { payload }) {
            state.isActive = payload.status;
            state.errMsg = payload.errMsg;
        },
        setVipStatus(state, { payload }) {
            state.vipStatus = payload;
            state.hasDialog = payload;
        },
        setConfig(state, { payload }) {
            state.config = payload;
        },
        addSong(state, { payload }) {
            state.orderList.push(payload);
        },
        delSong(state, { payload }) {
            state.orderList.splice(payload, 1);
        },
        topSong(state, { payload }) {
            const tmp = state.orderList.splice(payload, 1);
            state.orderList.splice(1, 0, tmp[0]);
        },
        updateOrderList(state, { payload }) {
            state.orderList.forEach(item => {
                if (item.songid === payload.songid) {
                    item.path = payload.path;
                }
            });
        },
        setHasDialog(state, { payload }) {
            state.hasDialog = payload;
        }
    },
    // extraReducers中针对异步action, 监听它的状态
    extraReducers: (builder) => {
        // Add reducers for additional action types here, and handle loading state as needed
        builder.addCase(fetchGetCurrent.fulfilled, (state, action) => {
            // Add user to the state array
        });
    }

});
export const {
    setOrderList,
    setCurrent,
    setDownloadList,
    updateDownloadList,
    setNetType,
    setActiveCode,
    setQrcodeStatus,
    setDialogTitle,
    setIsActive,
    setVipStatus,
    setConfig,
    addSong,
    delSong,
    topSong,
    updateOrderList,
    setHasDialog
} = controlSlice.actions;
export default controlSlice.reducer;

```
## /Users/thunder/mycode/rn/store/control.ts

```
import { createSlice } from "@reduxjs/toolkit";
import commonConfig from "../config.json";
import store from "./index.ts";
import { findNodeHandle, NativeModules } from "react-native";
import { setVipStatus } from "./common.ts";

interface ControlState {
    selectedAudioTrack: boolean
    playStatus: boolean
    videoNativeTag: number,
    isPlaying: boolean
}

export const controlSlice = createSlice({
    name: "control",
    initialState: <ControlState>{
        selectedAudioTrack: true,
        playStatus: false,
        videoNativeTag: 0,
        isPlaying: false
    },
    reducers: {
        setSelectedAudioTrack(state, { payload }) {
            state.selectedAudioTrack = payload;
        },
        setPlayStatus(state, { payload }) {
            state.playStatus = payload;
        },
        setVideoNativeTag(state, { payload }) {
            state.videoNativeTag = payload;
        },
        setIsPlaying(state, { payload }) {
            state.isPlaying = payload;
        }
    }
});
// 每个 case reducer 函数会生成对应的 Action creators
export const {
    setSelectedAudioTrack,
    setPlayStatus,
    setVideoNativeTag,
    setIsPlaying
} = controlSlice.actions;

export default controlSlice.reducer;

```
## /Users/thunder/mycode/rn/store/index.ts

```
import { configureStore } from "@reduxjs/toolkit";
import controlReducer from "./control";
import commonReducer from "./common";
import { TypedUseSelectorHook, useSelector, useDispatch } from "react-redux";

const store = configureStore({
    reducer: {
        control: controlReducer,
        common: commonReducer
    },
    middleware: getDefaultMiddleware => getDefaultMiddleware({
        //关闭redux序列化检测
        serializableCheck: false
    })
});
export type RootState = ReturnType<typeof store.getState>;
type AppDispatch = typeof store.dispatch
export const useAppSelector: TypedUseSelectorHook<RootState> = useSelector;
export const useAppDispatch: () => AppDispatch = useDispatch;
export default store;

```
## /Users/thunder/mycode/rn/store/selectors.ts

```
import {createSelector} from "@reduxjs/toolkit";
import { RootState } from "./index.ts";

const vipStatusData = (state: RootState) => state.common.vipStatus;

export const selectVipStatusData = createSelector(
    [vipStatusData],
    (data) => {
        console.log(data,1111)
        return ()=>data;
    }
);

```
