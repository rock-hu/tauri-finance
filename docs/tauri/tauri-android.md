# android   

## Android Studio
- Android SDK Platform
- Android SDK Platform-Tools
- NDK (Side by side)
- Android SDK Build-Tools
- Android SDK Command-line Tools

## tauri android init   

```
npm run tauri android init

> tauri-finance@0.1.0 tauri
> tauri android init

        Info ANDROID_HOME not set, trying to locate Android SDK...
        Info Using installed Android SDK: /home/rock/Android/Sdk
        Info Using installed NDK: /home/rock/Android/Sdk/ndk/29.0.14206865
        Info Installing Android Rust targets...
        Info Installing target aarch64-linux-android
info: downloading component 'rust-std' for 'aarch64-linux-android'
Generating Android Studio project...
        Info "/home/rock/workspace/tauri-finance/src-tauri" relative to "/home/rock/workspace/tauri-finance/src-tauri/gen/android/tauri_finance" is "../../../"
victory: Project generated successfully!
    Make cool apps! 🌻 🐕 🎉
```

```bash
rustup target add aarch64-linux-android armv7-linux-androideabi i686-linux-android x86_64-linux-android
```

## tauri android dev        

```bash

```

## references   
| item                    | link(s)                                        |
| ----------------------- | ---------------------------------------------- |
| Prerequisites - Android | https://tauri.app/start/prerequisites/#android |