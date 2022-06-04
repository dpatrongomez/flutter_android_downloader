# Flutter Android Downloader

[![Pub](https://img.shields.io/pub/v/flutter_android_downloader.svg?style=flat-square)](https://pub.dartlang.org/packages/flutter_android_downloader)


flutter_android_downloader 一 A plug-in that calls the Android system download manager

## Add dependencies

```yaml
dependencies:
  flutter_android_downloader: ^1.0.0
```

## Create download

```dart
int downloadId = FlutterAndroidDownloader.download("url", "path", "fileName","originName","headers");
```

> Parameter Description

| Parameter | Type | Legend |
| :-----| :-----| :-----|
| url | String | Download link |
| path | String | Download path, Android10 and above are downloaded to the Download folder of the built-in storage directory by default |
| fileName | String | Saved file name |
| originName | String | Download source name |
| headers | Map<String,String> | Request header, optional parameters |

## Monitor download callback information
```dart
FlutterAndroidDownloader.listen((id) {
  print("success $id");
  // to do something
});
```

## Complete usage example

```dart
FlutterAndroidDownloader.listen((id) {
  print("success $id");
});

void download() async {
    int id = await FlutterAndroidDownloader.download(
        "https://qd.myapp.com/myapp/qqteam/AndroidQQ/mobileqq_android.apk",
        "/ABC",
        "qq.apk",
        "QQ",
        {}
    );
    print("ID => $id");
}

```
